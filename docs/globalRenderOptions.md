# globalRenderOptions

`globalRenderOptions` is an object that is passed into every template rendered by TweetDeck. This can be used to implement custom flags
and functions.

## Contents

Current (default) contents of the global render options:

* **`asset`:** a function to return an asset via `TD.assets.get(value)` _(perfect example for custom functions)_
* **`decider`:** all currently available deciders from `TD.decider.getAllWithOverlay()`
* **`featureFlag`:** new TweetDeck features, looks like they are based on [experiments](https://github.com/DeckHack/discoveries/blob/master/docs/experiments.md)
* **`isTouchDevice`:** TweetDeck determines if we are using a touch-enabled device
* **`styledScrollbar`:** Determines if TweetDeck should show a styled or regular scrollbar

Functions can be used in templates like this: 

```mustache
{{#asset}}/web/assets/emoji/1f004.png{{/asset}}
```

`/web/assets/emoji/1f004.png` is the value given to the function and will be inserted in whatever function is returned by the specific key
in `globalRenderOptions`

----

Flags can be used like this:

```mustache
{{#isTouchDevice}}I'm a touch device{{/isTouchDevice}}
```

...where "I'm a touch device" only will be shown if `isTouchDevice` is true.

## Extending

Extending the global render options is an easy task. Just add another key to the object and either give it a boolean value to turn it into
a flag, or give it a function that returns another function, passing the value of the template call into it.

Example for functions (`asset`):

```js
// ...
asset: function() {
    return function(e) {
        return TD.assets.get(e)
    }
}
// ...
```
_Templating in TweetDeck is based on Twitters [hogan.js](https://github.com/twitter/hogan.js), so you'll be able to find more information
there!_

As always the notice that you should do this as early as possible, so stuff might not interfere with this or not be applied at all.
