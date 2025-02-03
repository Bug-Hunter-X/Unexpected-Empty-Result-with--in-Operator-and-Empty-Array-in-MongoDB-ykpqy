# Unexpected Empty Result with $in Operator and Empty Array in MongoDB

This repository demonstrates a common yet subtle error when using the `$in` operator in MongoDB queries with an empty array.  The issue arises when querying a field that might or might not exist, expecting an empty array to act as a wildcard (returning documents where the field is either absent or an empty array).  However, this is not the behavior;  an empty array results in no documents being returned.

## Reproduction

The `bug.js` file contains code demonstrating the erroneous query.  The query attempts to find documents where the `field` is in an empty array.  This consistently returns an empty result set, regardless of the contents of the collection.  The solution file demonstrates how to correctly handle such cases.