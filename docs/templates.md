# Templates

TweetDeck is using [mustaches](https://github.com/janl/mustache.js) as a template engine (or a close derivative of it)

## Location

TweetDeck templates are located in following objects:

* `window.TD_mustaches`
* `window.TD.mustaches` (this probably just mirrors from the above one)

These objects include all templates and you can access their contents with simply calling their keys:

```js
TD_mustaches['account_settings_account_summary.mustache']
```

## Overriding Templates

It's not possible to completely override templates like this:

```js
TD_mustaches[...] = "new template"
```

Instead you have to do it like this:

```js
TD_mustaches[...] = TD_mustaches[...].replace("</div>", "</div> new template")
```

## Notice

Templates should be overwritten as soon as ´TD_mustaches` is defined, as you can end up mixing
things together if the template you are changing is streamed or often changed content.
