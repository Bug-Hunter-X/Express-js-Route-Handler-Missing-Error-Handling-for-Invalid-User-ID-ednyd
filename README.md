# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer without checking for errors. This can result in unexpected behavior or crashes if the `id` parameter is not a valid integer.

The `bug.js` file contains the buggy code, and `bugSolution.js` provides a corrected version with proper error handling.

## Bug

The primary issue is the lack of input validation for `req.params.id`.  If a non-numeric string is provided, `parseInt(userId)` will return `NaN`, leading to a potential crash or unexpected behavior depending on how the application handles this scenario.

## Solution

The `bugSolution.js` file demonstrates how to fix this bug.  It adds validation to ensure `userId` is a number before attempting to find the user.  Additionally, it handles the case where the user is not found, returning a proper 404 response.