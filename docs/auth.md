# Documentation

## Summary
This operator is responsible for handling user account activities, it provides the necessary functionalities required for user account creation, logging in, and logging out in the context of a Flask web application that focuses on Formula 1 information and user predictions.

## Inputs
The primary inputs come from HTTP requests made to the Flask server running this operator. These inputs are primarily from JSON payloads included in `POST` requests made by users.

1. **Create Account (`/auth/account`)**: The request JSON should include `name`, `username`, and `password` properties for creating a new user account.
2. **Login (`/auth/login`)**: The request JSON should contain `username` and `password` properties for existing users to log in.
3. **Logout (`/auth/logout`)**: This endpoint does not require any input as it simply invalidates the user session.

## Parameters
The following query parameters are used in this operator:

1. **username**: String that represents the user's unique username.
2. **password**: String that represents the user's password.
3. **name**: String that is used when creating a new account, represents the user's full name.

## Outputs
The outputs for each of the functions in this operator are mainly HTTP responses with JSON payloads and HTTP status codes:

1. **Create Account (`/auth/account`)**: If successful, the HTTP response includes JSON with a 'user' key whose value includes user account details.
2. **Login (`/auth/login`)**: If successful, the HTTP response includes JSON with a 'user' key whose value is user account details.
3. **Logout (`/auth/logout`)**: If successful, the HTTP response includes a 'logged out' message.

## Functionality
This operator consists of three Flask routes: `/auth/account` for creating new user accounts, `/auth/login` for user login, and `/auth/logout` for logging users out.

- **Create Account**: Checks if the request is JSON and whether the provided parameters meet certain conditions for account creation. The entered data is then verified, a new user is created using the `create_an_account` function, and finally, an access token for the user is generated and sent in the response.

- **Login**: Similar steps are followed but in this case, it gets the user by the provided username using `get_user_by_username` function and verifies the password. If the credentials are valid, an access token is generated for the user and sent in the response.

- **Logout**: This is a relatively simple route that invalidates the authentication credentials of the user by calling `unset_jwt_cookies`. This disallows the user from making any authenticated requests until they log back in.
  
All these routes have error handling that catches any exceptions and returns an error message and HTTP error status code as required.