## What is it?

The HeatSuite module is a class of functions that are specific to the needs of the HeatSuite application. When creating customs tasks or added features to HeatSuite, I suggest we continue to use this class for consistency.

To initiate the class, declare it before any use:

```js
const modHS = require('HSModule');
```

## Functions

### `saveDataToFile(task, fileID, data)`

**Description:** saves data to a file, and updates the cache with the last time the task was complete.

**Parameters:**
+ `task` *(String)* – task ID that is defined in the [Task's](watchapp-tasks.md) object.
+ `fileID` *(String)* – The file name identifier that will be added to the HeatSuite filename scheme: `htst_fileID_DDMMYYYY`
+ `data` *(Object)* - An object containing keys corresponding to the column headers and corresponding data as their values.

**Returns:**  
*boolean* – returns true if successful

### `parseBLEData(buffer, schema)`

**Description:** parses and returns BLE data based on the schema provided.

**Parameters:**
+ `buffer` *(Array)* – byte array of data received over bluetooth.
+ `schema` *(Object)* – The expected data schema from the bluetooth characteristic

**Returns:**  
*Object* – returns an object with the schema populated
