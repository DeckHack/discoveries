# Assets

All kinds of files TweetDeck is loading.

## Location

All assets are located at `https://ton.twimg.com/tweetdeck-web`. To always properly access them, the newly generated files are mapped to
hashless filenames in the following objects:

* `TD_assetsOverlay`
* `TD.assetsOverlay` (is an exact copy of the first one)

You can simply get the asset URL with calling a key:

```js
TD_assetsOverlay["/web/assets/emoji/1f004.png"]
// => "https://ton.twimg.com/tweetdeck-web/web/assets/emoji/1f004.a194c76fd9.png"

TD.assetsOverlay["/web/assets/emoji/1f004.png"]
// => "https://ton.twimg.com/tweetdeck-web/web/assets/emoji/1f004.a194c76fd9.png"
```

...or, if you want to, you can access assets the _TweetDeck-way_:

```js
TD.assets.get("/web/assets/emoji/1f004.png")

// => "https://ton.twimg.com/tweetdeck-web/web/assets/emoji/1f004.a194c76fd9.png"
```

## Overriding Assets

Due to the `Content-Security-Policy` headers of TweetDeck it's not easily possible to override assets to external sources, 
basically impossible unless you remove the headers locally with the use of an extension (for example).

The only other thing you could do here is switching assets out with each other, but we leave that up to you!
