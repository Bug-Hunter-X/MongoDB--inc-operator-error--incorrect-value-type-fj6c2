# MongoDB $inc Operator Error: Incorrect Value Type

This repository demonstrates a common error when using the `$inc` operator in MongoDB update operations.  The `$inc` operator is designed to increment a numerical field, but if you provide a string value instead of a numerical value, the operation will silently fail without throwing an error. 

## Bug
The bug is in `bug.js`. It shows how an incorrect string is passed to the `$inc` operator.  The expected behavior is to increment the field by 1, but this code does not result in the intended outcome.

## Solution
The solution (`bugSolution.js`) demonstrates the correct usage of `$inc`. The provided value is a number, thus resulting in the field being correctly incremented. 

## How to reproduce
1. Clone this repository.
2. Make sure you have MongoDB and a MongoDB driver installed for Node.js.
3. Create a collection named `myCollection` and insert a document `{ _id: 1, field: 0 }`. 
4. Execute the code in `bug.js` and observe the result.
5. Execute the code in `bugSolution.js` and observe the result.

## Lessons Learned
* Always verify the data types when performing update operations in MongoDB.
* Pay close attention to the expected data types of operators like `$inc` to prevent unexpected behavior and silent failures.
* Proper error handling can assist in identifying issues.