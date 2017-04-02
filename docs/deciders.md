# Deciders

Deciders are flags to enable/disable specific features inside TweetDeck. Said features are usually near production-ready.

## Location

You can get all deciders using `TD.decider.getAll()`.

The returned object includes all deciders as keys and their status as boolean value. Like this

```js
{
  "abuse_emergency_filter_info": true,
  "account_settings_join_team_flow": true,
  "account_settings_redesign": true,
  "action_favorited_retweet": true,
  /* ... more keys ... */
  "windows_migration_logged_in_2": true,
  "windows_migration_logged_out_2": true,
  "windows_migration_warning_2": true,
}
```

## Override

You can override deciders in several ways.

The first one, courtesy of [@NO_BOOT_DEVICE](https://twitter.com/NO_BOOT_DEVICE), consists of wrapping one of `TD.decider` methods to specifically modify specific keys when getting the deciders from TweetDeck's backend.

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

The other, simpler, uses the `decider_overlay` in `TD.config` (probably used for debugging purposes).

```js
TD.config.decider_overlay = {
  "hearts_and_likes2": true,
  "dm_rounded_avatars": false,
  "simplified_replies": false
};
```

## Notice

To avoid any issues (broke templates/features), the deciders should be changed as soon as `TD` is defined.