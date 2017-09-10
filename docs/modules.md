# Modules

As every other modern web application, TweetDeck is moving to use Webpack and seperate modules instead of a global 
namespace that is accessible for everyone.

Everything Webpack related, including the modules and their cache reside in a global window object called `WebpackJsonp`
and we can use small utilities to properly access and work with everything it exposes.

## Webcrack

Webcrack is a small script written by [no-boot-device](https://github.com/no-boot-device) and transforms `WebpackJsonp` into
`wc`, giving us functions to get all modules, get modules by their ID and search through the module caches by providing exported
keys.

You can find the script and usage details [here](https://gist.github.com/no-boot-device/cb63762000e606e50690911cac1bcead)

### Usage with TweetDeck

So, how do we use it with TweetDeck now? Pretty simple.

Use your favorite browsers devtools and read through `bundle.{cool file hash}.js`, finding eventually interesting bits of code that
could be modules.

#### Identifying modules

Usually, you can identify modules by their code being wrapped in an anonymous function and usually at the end `export`ing something. Usage
of a module can be identified if somewhere in the code there is a variable referencing something like so:

```js
var s = n(8)
```

As variable and function names mostly differ through every Webpack build they do not matter, but `n(8)` is interesting, as we can suspect
it loads the module with ID 8.

If we have Webcrack included on our page we can now use `wc.get({module id})` to get everything that is exported from this module.

##### Example: Notification Toasts

Speaking about module number 8, let's try out everything by an actual TweetDeck example.

As people have noticed, TweetDeck moved away from `progressIndicator` to new notification toasts shown in the top right of the interface.
With this change they also started modularizing the new toasts.

So, we want to fire notifications now too..., but how do we achieve this?

```js
// Getting module 8, our suspect for containing notification functions
var notifications = wc.get(8)
// => {showErrorNotification: ƒ, showNotification: ƒ, ...
```

**Success!** We now have all functions related to notification toasts in `notifications`. Using your browser console, 
now type `notifications.showNotification` (without brackets at the end) to get the functions code for investigation.

With a bit reading through it, we can make out that the functions only take one parameter, which is an object having
following keys:

* `title`
* `message`
* `timeoutDelayMs`

Having everything we need now, let's try it out!

```js
notifications.showNotification({ title: "Hello there!", message: "This is a notification", timeoutDelayMs: 3000 })
```

It works, we should see a notification pop up just fine.

#### Searching through the module cache

With above example, we could now easily just implement this into our userscript and be fine, right?

Not really, as mentioned before Webpack randomizes variable names and probably also the module IDs can change over different builds.

There's a way to circumvent these issues, and that works by finding a module by its exports instead of their IDs, using another 
function provided by Webcrack, `findCache`.

Going back to our example from before, the notification toasts, using `findCache` would work like this:

```js
// We know notifications have a function `showNotification` which is exported, so let's search for it!
var cache = wc.findCache("showNotification")
// => [ { exports: { ... }, id: 8, ... } ]

// We got an array with the "search results", we simply pick the first (and only) one and set its exports to our 
// notifications variable
var notifications = cache[0].exports

// ... Use notifications like before

// Alternatively, you can also write this in a single line
var notifications = wc.findCache("showNotification")[0].exports
```

