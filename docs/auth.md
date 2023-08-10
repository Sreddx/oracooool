## Summary
This code provides the backend functionality for the authentication and user account management in a web application. It includes routes for creating user accounts, logging in, and logging out.

## Inputs
The inputs for the `/auth/account` route are the user's name, username, and password. The inputs for the `/auth/login` route are the username and password.

## Parameters
There are no additional parameters in this code.

## Outputs
The outputs for the `/auth/account` route are the created user object and an access token. The outputs for the `/auth/login` route are the logged-in user object and an access token. The output for the `/auth/logout` route is a message confirming the user has been logged out.

## Functionality
The `create_account()` function handles the creation of user accounts. It validates the input data, creates a new user account using the provided information, and returns the created user object along with an access token. The access token is stored as a cookie in the response.

The `login()` function handles the user login process. It validates the input data, retrieves the user object based on the provided username, and verifies the password. If the credentials are valid, it returns the logged-in user object along with an access token stored as a cookie in the response.

The `logout()` function handles the user logout process. It clears the access token cookie from the response and returns a message confirming the user has been logged out.