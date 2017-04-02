# columnManager

What this controller is doing should be pretty self-explanatory coming from it's name. It manages the different columns inside TweetDeck.

## Table of Contents

* [Constants](#constants)
* [Methods](#methods)
  * [add](#add)
  * [addMany](#addmany)
  * [addColumnToUI](#addcolumntoui)
  * [checkColumns](#checkcolumns)
  * [createColumn](#createcolumn)
  * [deleteColumn](#deleteColumn)  
  * [findChirpByAccountKey](#findchirpbyaccountkey)
  * [get](#get)
  * [getAll](#getall)
  * [getAllOrdered](#getallordered)
  * [getByApiid](#getbyapiid)
  * [getColumnsByAccountKey](#getcolumnsbyaccountkey)
  * [getStreamingState](#getstreamingstate)
  * [isStreaming](#isstreaming)
  * [makeColumn](#makecolumn)
  * [makeColumnFor](#makecolumnfor)
  * [makeDefaultColumns](#makedefaultcolumns)
  * [makeOtherColumnAndFeeds](#makeothercolumnandfeeds)
  * [move](#move)
  * [refreshColumnTitles](#refreshcolumntitles)
  * [removeFromAppLayer](#removefromapplayer)
  * [updateTitlesAndIconClasses](#updatetitlesandiconclasses)
* [Handlers](#handlers)
  * [handleMakeOrRefreshScheduledColumn](#handlemakeorrefreshscheduledcolumn)
  * [handleUiNeedsColumnOrder](#handleuineedscolumnorder)
  * [handleUiNeedsColumns](#handleuineedscolumns)
* [Senders](#senders)
  * [sendColumnOrder](#sendcolumnorder)
  * [sendColumns](#sendcolumns)
  * [showColumn](#showcolumn)
  
## Constants

| Name | Type | Value | Description |
|------|------|-------|-------------|
| `CUSTOMTIMELINES` | String | `customtimelines` | Definition of `customtimelines` column type |
| `DATAMINR` | String | `dataminr` | Definition of `dataminr` column type |
| `DISPLAY_ORDER` | Array | Objects | Display order of column types inside the column creation dialog |
| `DISPLAY_ORDER_PROFILE` | Array | Objects | Display order of column types inside profile views |
| `DISPLAY_ORDER_SINGLETON` | Array | Objects | Display order of columns provided by TweetDeck |
| `FAVORITES` | String | `favorites` | Definition of `favorites` column type |
| `FOLLOWERS` | String | `followers` | Definition of `followers` column type |
| `HELP_TEXT` | Object | Object | Help texts for the different column types |
| `HOME` | String | `home` | Definition of the `home` column type |
| `INBOX` | String | `privateMe` | Definition of the `inbox` column type (messages for all accounts) |
| `INTERACTIONS` | String | `interactions` | Definition of the `interactions` column type |
| `LISTS` | String | `lists` | Definition of the `lists` column type |
| `LIVEVIDEO` | String | `livevideo` | Definition of the `livevideo` column type |
| `ME` | String | `me` | Definition of the `me` column type (mentions for all accounts) |
| `MENTIONS` | String | `mentions` | Definition of the `mentions` column type |
| `MENU_ATTRIBUTION` | Object | Object | Includes `(all accounts)` attribution texts for `me` and `privateMe` |
| `MENU_TITLE` | Object | Object | Includes titles for all different column types |
| `MESSAGES` | String | `messages` | Definition of the `messages` column type |
| `MODAL_TITLE` | Object | Object | Includes titles for the column creation modal |
| `NETWORKACTIVITY` | String | `networkactivity` | Definition of the `networkactivity` column type |
| `NON_SELF_FEED_TYPE` | Object | Object | Includes column types that have no account bound to them |
| `SCHEDULED` | String | `scheduled` | Definition of the `scheduled` column type |
| `SEARCH` | String | `search` | Definition of the `search` column type |
| `SELF_ACCOUNTS_ONLY` | Object | Object | Includes column types that only work with accounts bound to them |
| `SELF_FEED_TYPE` | Object | Object | Defines feed types for columns with accounts |
| `STREAMING_FULL` | String | `streaming_full` | Definition of the `streaming_full` stream status |
| `STREAMING_NONE` | String | `streaming_none` | Definition of the `streaming_none` stream status |
| `STREAMING_PARTIAL` | String | `streaming_partial` | Definition of the `streaming_partial` stream status |
| `TIMELINE` | String | `timeline` | Definition of the `timeline` column type |
| `TRENDS` | String | `trends` | Definition of the `trends` column type |
| `TWEETS` | String | `tweets` | Definition of the `tweets` column type |
| `TWITTER_GENERIC` | Object | Object | Definition of generic column types |

## Objects

| Name | Description |
|------|-------------|
| `_aColumnIndex` | Contains all columns |
| `_columnOrder` | Contains all columns in order |
| `columnTypeToIconClass` | Contains mappings from column types to column icons |

## Methods

### _add_
  
**Parameters:**
* `TD.vo.Column`
  
**Description:**  
Adds a new column to `_aColumnIndex`
  
### _addMany_

**Parameters:**
* `TD.vo.Column[]`
  
**Description:**  
Adds new columns to `_aColumnIndex`

### _addColumnToUI_

**Parameters:**  
* `TD.vo.Column`

**Description:**  
Adds a column to the UI

### _checkColumns_

**Parameters:**  
_None_

**Description:**  
Checks if there are columns, and if not, it adds the default columns

### _createColumn_

**Parameters:**
* `sColumn` (?)
* `Feed` (?)

**Description:**
Creates and returns a `TD.vo.Column`

### _deleteColumn_

**Parameters:**
* Column key

**Description:**  
Deletes a column

### _findChirpByAccountKey_

_TODO_

### _get_

**Parameters:**  
* Column key

**Description:**  
Returns the column with the specified column key

### _getAll_

**Parameters:**  
_None_

**Description:**  
Returns all columns

### _getAllOrdered_

**Parameters:**  
_None_

**Description:**  
Returns all columns in order

### _getByApiid_

_TODO_

### _getColumnsByAccountKey_

**Parameters:**  
* Account key

**Description:**  
Returns all columns that match the specified account key

### _getStreamingState_

**Parameters:**  
* Column key

**Description:**  
Returns the streaming state of the specified column

### _isStreaming_

**Parameters:** 
* Column key

**Description:**  
Returns a boolean value if the specified column is streaming or not

### _makeColumn_

_TODO_

### _makeColumnFor_

**Parameters:**  
* `settings` Object

**Description:**  
Creates a column with the specified options from the `settings` object

### _makeDefaultColumns_

**Parameters:**
* Account key

**Description:**  
Creates a _Home_, _Interactions_, _Messages_ and _Activity_ column for the specified account key

### _makeOtherColumnAndFeeds_

_TODO_

### _move_

**Parameters:**  
* Column key
* Action (?)
  * The `move` code compares this to either match `left` or `right`
  
**Description:**
Moves the specified column

### _refreshColumnTitles_

**Parameters:**  
_None_

**Description:**  
Refreshes the column titles

### _removeFromAppLayer_

**Parameters:**  
* Column key

**Description:**  
Cancels column subscriptions and feeds

### _updateTitlesAndIconClasses_

**Parameters:**  
_None_

**Description:**  
Refreshes column titles, attributions and icons

## Handlers

### _handleMakeOrRefreshScheduledColumn_

**Trigger:**  
`uiNeedsScheduledColumnVisible`

**Description:**  
Refreshes or adds new scheduled columns

### _handleUiNeedsColumnOrder_

**Trigger:**  
`uiNeedsColumnOrder`

**Description:**  
Sends the column order to the frontend

### _handleUiNeedsColumns_

**Trigger:**  
`uiNeedsColumns`

**Description:**  
Sends columns to frontend

## Senders

### _sendColumnOrder_

**Emitter:**  
`dataColumnOrder`

**Payload:**

```js
{
  columnOrder: TD.controller.columnManager._columnOrder
}
```

### _sendColumns_

**Emitter:**  
`dataColumns`

**Payload:**

```js
{
  columns: TD.controller.columnManager.getAllOrdered()
}
```

### _showColumn_

**Parameters:**  
* Column key

**Emitter:**  
`uiColumnFocus`

**Payload:**

```js
{
  columnKey: (parameter)
}
```
