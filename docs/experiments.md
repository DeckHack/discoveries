# Experiments

Experiments are another way to toggle features in the TweetDeck source code. They are either entirely hardcoded or pulled from the TweetDeck API. Recent ones seem to be hardcoded.

Experiments could have been "prototypes" of what became [deciders](./deciders.md), each experiment key has an ID at the end, these could might internal issues/PR numbers.

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

This is a bit tricky, for whatever reason you have to pass all experiments at once when overriding one of them, if you don't do that, all other experiments will be gone.

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

You can disable an experiment by passing an object with all the experiments but the one you want to disable. If you don't pass everything, all non-supplied experiments will have their value set to `''`, be warned!.

## Notice

As for every feature toggle, you have to do this as soon as `TD` gets available, so templates are not broken or other side effects may occur. Some of the experiments might work if changed later on.
