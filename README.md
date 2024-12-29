# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling when dealing with user input.  Specifically, the `/users/:id` route attempts to access a user by their ID. However, if the ID is not a valid number, the code crashes without any informative error message to the client.

## Bug
The `bug.js` file contains the erroneous code. It attempts to parse the `userId` from the request parameters as an integer but fails to handle situations where the `userId` is not a number, leading to a potential server crash or unexpected behavior.

## Solution
The `bugSolution.js` file provides a corrected version of the route handler.  It includes `isNaN()` check to validate if the `userId` is a valid number. If not, it gracefully sends a 400 Bad Request response to the client.