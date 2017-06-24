# filterManager

This controller is managing filters, which hide content in columns or conversations based on different criteria

## Table of Contents

* [Methods](#methods)
  * [addFilter](#addfilter)
  * [getAll](#getall)
  * [hasFilterApplied](#hasfilterapplied)
  * [init](#init)
  * [pass](#pass)
  * [reapplyAllFilters](#reapplyallfilters)
  * [removeFilter](#removefilter)
  * [validateFilter](#validatefilter)
* [Usage](#usage)

## Methods

### _addFilter_

**Parameters:**  
* String `type`
* String `value`
* Boolean `positive` (optional)

**Description:**  
Creates a new `TD.vo.Filter` with given parameters.

### _getAll_

**Parameters:**  
_None_

**Description:**  
Returns all filters.

### _hasFilterApplied_

**Parameters:**  
* String `type`
* String `value`

**Description:**  
Returns if the given `value` would have any filter applied. `type` also needs to match the filter type.

### _init_

**Parameters:**  
None

**Description:**  
Initialization function for the filter manager. Fetches all filters from the backend.

### _pass_

**Parameters:**
* TwitterStatus `tweet`
* ??? (optional)

**Description:**  
Returns if the given `tweet` passes any of the existing filters.

### _reapplyAllFilters_

**Parameters:**  
_None_

**Description:**  
Reloads all timelines.

### _removeFilter_

**Parameters:**  
* Filter `filter`

**Description:**  
Removes given filter.

### _validateFilter_

**Parameters:**  
* String `type`
* String `value`

**Description:**  
Validates if `value` is a proper filter of `type`.

## Usage

This is a short example how the filter manager could be utilized

```js
// We create a new filter and save a reference to a variable
var filter = TD.controller.filterManager.addFilter("phrase", "#hashtag")

// Just to get sure, we reapply all filters
TD.controller.filterManager.reapplyAllFilters()

// We check if our filter exists
TD.controller.filterManager.hasFilterApplied("phrase", "#hashtag")

// We validate our filter (checks as if we add a new one)
// This returns false as a filter for #hashtag already exists
TD.controller.filterManager.validateFilter("phrase", "#hashtag")

// In the end, we delete our filter
TD.controller.filterManager.removeFilter(filter)
```
