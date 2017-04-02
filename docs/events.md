# Events

As pretty much any "big" web application, TweetDeck makes heavy use of events to function. Almost every action performed by the user triggers an event to which other parts of the UI will react to.

## Getting the list of events

Most of the events are jQuery events so we can easily list them by using some jQuery hackery in the Chrome console:

```js
_.uniq([
  ...Object.keys(jQuery._data(document,'events')), ...Object.keys(jQuery._data(document.querySelector('.js-app'),'events'))
])
```

Or, in a more detailed format

```js
// Events bound to the document object (most of them)
const docEvents = Object.keys(jQuery._data(document,'events'));
// Events bound to the `.js-app` element
const appEvents = Object.keys(jQuery._data(document.querySelector('.js-app'),'events'))

// We simply de-duplicate the lists of events because we don't need duplicates
_.uniq([
  ...docEvents,
  ...appEvents
]);
```

## Description of the events

You can find a list of events and their description on the [dedicated file](./events-list.md)