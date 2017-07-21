# scheduler

Manages scheduling and execution of tasks

## Table of Contents

* [Constants](#constants)
* [Methods](#methods)
  * [init](#init)
  * [removePeriodicTask](#removeperiodictask)
  * [restartPeriodicTask](#restartperiodictask)
  * [schedulePeriodicTask](#scheduleperiodictask)
  * [tick](#tick)
  * [updatePeriodicTask](#updateperiodictask)
  * [_fireTask](#_firetask)
  * [_handleTick](#_handletick)

## Constants

| Name | Type | Value | Description |
|------|------|-------|-------------|
| `QUERY_INTERVAL` | Integer | `1000` | Time (ms) interval for ticks |
| `SLEEP_THRESHOLD` | Integer | `60000` | Time (ms) threshold to execute tasks after app has been asleep/inactive for |
| `_jQueryCleanupTaskId` | String | specific to local | ID of the task that manages cleanup of jQuery fragments |
| `_lastTickTime` | Integer | specific to local | Time (ms) value of the last passed tick |
| `_tasks` | Object | - | Object containing all tasks that are run periodically |

## Methods

### _init_

**Description:**  
Sets the `_lastTickTime` to current unix time, adds the jQuery cleanup task and sets `_jQueryCleanupTaskId`

### _removePeriodicTask_

**Parameters:**  
* `taskID` String

**Description:**  
Removes the task with ID `taskID`

### _restartPeriodicTask_

**Parameters:**  
* `taskID` String

**Description:**  
Restarts the task with ID `taskID`

### _schedulePeriodicTask_

**Parameters:**  
* `interval` Integer
* `func` Function
* ??? (optional)

**Description:**  
Creates a task that is executes `func` with the set `interval`

### _tick_

**Description:**  
This function initializes the interval for the scheduler

### _updatePeriodicTask_

**Parameters:**  
* `taskID` String
* `interval` Integer
* `func` Function

**Description:**  
Update task with the ID `taskID` to have a new `interval` and/or `func`

### _\_fireTask_

**Parameters:**  
* `task` Object

**Description:**  
Executes the callback function of specified `task`

### _\_handleTick_

**Description:**  
Handles ticks and executes callback functions if required
