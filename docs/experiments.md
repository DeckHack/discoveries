# Experiments

Experiments are another way to toggle features in the TweetDeck source code. They are either entirely hardcoded 
or pulled from the TweetDeck API. Recent ones seem to be hardcoded.

It seems that experiments might be pre-staged deciders, the experiment keys include IDs at the end, so these
might be internal issues/PRs.

## Location

The experiments are stored somewhere in `TD.controller.stats`. You can check for the value of an experiment with executing
`TD.controller.stats.getExperimentBucket("experiment_key")` in your console.

To find all experiments used, you have to search through the bundled source code.

Here are all experiments in the source code as of writing (1.4.2017)

| Key                                      | Value                            | Description                        |
|------------------------------------------|----------------------------------|------------------------------------|
| `tweetdeck_notifications_streaming_5807` | `no_streaming`                   | Disables streaming                 |
| `tweetdeck_simplified_search_flow_5499`  | `no_temp_editable_header_search` | Open new columns for search        |
| `tweetdeck_editable_search_headers_5431` | `editable_search_headers`        | Editable search headers            |
| `tweetdeck_engagement_icons_3569`        | - (already implemented)          | Tweet actions are slightly hidden  |
| `thamshere_test_3281`                    | -                                | Test                               |

## Overriding Experiments

This is a bit tricky, as (for whatever reason) you always have to supply all experiments on overriding them, if you don't, 
all other experiments that are already set will be gone.

You can set a experiment the following way:

```js
TD.controller.stats.setExperiments({
    config: {
        experiment_key: {
            value: 'experiment_value'
        }
    }
});
```

You can unset an experiment by supplying everything that is not the value from the above table. If you only set one experiment,
all others will default to `""`. So if you want to get sure that only this one feature you want to change is changed, you
also have to supply all other experiments and their default values.

## Notice

As for every feature toggle, you have to do this as soon as `TD` gets available, so templates are not broken or other side effects
may occur. Some of the experiments might work if changed later on.
