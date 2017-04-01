# Deciders

Deciders are switches inside the TweetDeck code to enable/disable features for testing or in the end production stages.

## Location

You can get all deciders using `TD.decider.getAll()`

The returned object includes all deciders as keys and their status as boolean value.

## Override

A snippet to override deciders provided by [@NO_BOOT_DEVICE](https://twitter.com/NO_BOOT_DEVICE)

```js
window.decider_override = {
  "hearts_and_likes2": true,   // revert likes to favorites
  "dm_rounded_avatars": false, // make avatars in dms nonround
  "simplified_replies": false  // remove "Replying to" replacing mentions
};

TD.decider.updateFromBackend = _.wrap(TD.decider.updateFromBackend, (function(func, dict) {
  for (var a in window.decider_override) { dict[a] = window.decider_override[a]; }
  return func(dict);
}));

TD.decider.updateForGuestId();
```

Another, simpler way to change deciders is creating a `TD.config.decider_overlay` with the deciders that should be changed

```js
TD.config.decider_overlay = {
  "hearts_and_likes2": true,
  "dm_rounded_avatars": false,
  "simplified_replies": false
};
```

## Notice

To prevent broken templates (or no changes at all), the deciders should be changed as soon as the `TD` object becomes available.
