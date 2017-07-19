# Filter

Filters are used to hide content in columns. `TD.vo.Filter` is the base class for many other filter types.

## Table of Contents

* [Constants](#constants)
  * [Enumerators](#enumerators)
  * [Properties](#properties)
* [Methods](#methods)
  * [pass](#pass)
  * [getDisplayType](#getdisplaytype)
  * [_getFilterTarget](#_getfiltertarget)
  * [_testString](#_teststring)
  * [_testNumber](#_testnumber)
  * [_testBoolean](#_testboolean)
  * [toBackendState](#tobackendstate)
  * [fromBackendState](#frombackendstate)

## Constants

### Enumerators

| Name | Description |
|------|-------------|
| `PHRASE` | "Words and phrases" filter type |
| `SENDER` | "Sender" (User) filter type |
| `SOURCE` | "Source" filter type |
| `FOLLOWERS` | "Followers" filter type _(unused)_ |
| `IS_RETWEET` | "is Retweet" filter type |
| `IS_MENTION` | "is Mention" filter type |
| `IS_FAVORITE` | "is Favorite" (Like) filter type |
| `IS_FOLLOW` | "is Follow" filter type |
| `IS_ACTION_ON_RETWEET` | "is action on Retweet" (Liked/Retweeted your RT) filter type |
| `IS_QUOTED` | "is Quoted" filter type |
| `HAS_IMAGE` | "has image" filter type |
| `HAS_VIDEO` | "has video" filter type |
| `HAS_GIF` | "has GIF" filter type |
| `HAS_VINE` | "has Vine" filter type |
| `HAS_MEDIA` | "has media" filter type |
| `HAS_LINK` | "has link" filter type |
| `IS_FROM_VERIFIED` | "is from verified" filter type |
| `CHIRP_TYPE` | "chirp_type" filter |
| `LOCATION` | "Location" filter type |
| `SINCE_TIME` | "since time" filter type |
| `UNTIL_TIME` | "until time" filter type |

### Properties

| Name | Description |
|------|-------------|
| `id` | Local ID of the filter |
| `value` | Value of the filter (what will be checked against in `type`) |
| `type` | Type of the filter, one of [Enumerators](#enumerators) |
| `positive` | Negate checks of filters (???) _(unused)_ |
| `exact` | If the target needs to match the filter exactly |
| `fuzzy` | Fuzzy matching (?), **actually** only prepends `@` before checks |
| `range` | Used in Number checks |
| `filter_target` | Returns the target tweet or actual tweet |

## Methods

### _pass_

**Parameters:**  
* `tweet` TwitterStatus

**Description:**  
Passes specific parts of `tweet` to tester functions, depending on `type`

### _getDisplayType_

**Parameters:**  
_None_

**Description:**  
Get a display type description for the `type` of the current filter

### _\_getFilterTarget_

**Parameters:**  
* `tweet` TwitterStatus

**Description:**  
Returns `tweet` or the `tweet`s target status, depending on `filter_target`

### _\_testString_

**Parameters:**  
* `text` String

**Description:**  
Matches `text` against `value` of the filter

### _\_testNumber_

**Parameters:**  
* `num` Number

**Description:**  
Matches `num` against `value` of the filter, or if `num` is in `range` (if specified)

### _\_testBoolean_

**Parameters:**  
* `bool` Boolean

**Description:**  
Matches `bool` against `value`

### _toBackendState_

**Returns:**  
* `object` Object
  * `type`
  * `value`
  * `positive`
  * `exact`
  * `fuzzy`
  * `range`

**Description:**  
Returns a object which is ready to be pushed into the TweetDeck backend

### _fromBackendState_

**Parameters:**  
* `data` Object

**Description:**  
Gets passed `data` from backend and fills in corresponding properties
