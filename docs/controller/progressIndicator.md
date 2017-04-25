# progressIndicator

This controller is managing messages for tasks, shown as the small black boxes in the bottom right.

## Table of Contents

* [Methods](#methods)
  * [addMessage](#addmessage)
  * [addTask](#addtask)
  * [changeMessage](#changemessage)
  * [deleteTask](#deletetask)
  * [taskComplete](#taskcomplete)
  * [taskFailed](#taskfailed)
* [Usage](#usage)

## Methods

### _addMessage_

**Parameters:**  
* String `message`

**Description:**  
Creates a temporary progress indicator showing `message`. It also returns the message ID which can be
used in combination with other methods, but due to its short lifetime is not of much use.

### _addTask_

**Parameters:**  
* String `message`

**Description:**  
Creates a progress indicator showing `message`. It also returns the message ID which can be used in
combination with other methods.

### _changeMessage_

**Parameters:**  
* String `id`
* String `newMessage`

**Description:**  
Changes the shown message of the progress indicator with the ID `id` to `newMessage`.

### _deleteTask_

**Parameters:**  
* String `id`

**Description:**  
Removes the progress indicator with ID `id`

### _taskComplete_

**Parameters:**  
* String `id`
* String `successMessage` _(optional)_

**Description:**  
This marks the task with the ID `id` as completed. If no `successMessage` is supplied, the current task message will be used.
Both the old message and new message will have `Success: ` prepended to them. The task will also be hidden after a short time interval.

### _taskFailed_

**Parameters:**  
* String `id`
* String `failureMessage` _(optional)_

**Description:**  
This marks the task with the ID `id` as failed. If no `failureMessage` is supplied, the current task message will be used.
Both the old message and new message will have `Failed: ` prepended to them. The task will also be hidden after a short time interval.

## Usage

This is a short example of how the progress indicator could be utilized

```js
// We create a new task and save its message ID to a variable
var task = TD.controller.progressIndicator.addTask("This is my new task!")

// We change our message
TD.controller.progressIndicator.changeMessage(task, "Something new happens in this task!")

// We mark our task as completed and supply a success message
TD.controller.progressIndicator.taskComplete(task, "My task worked fine!")
```
