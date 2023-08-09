# Documentation

## Summary

This code represents two functions: `create_an_account` and `get_user_by_username`, responsible for creating and fetching user account details in a database, respectively.

## Inputs

For `create_an_account` function, following inputs are used: 

- `name`: The full name of the user, as a string.
- `username`: The unique username as a string that the user will use to log into their account.
- `password`: The user's password, as a string.

For `get_user_by_username` function, following input is used: 

- `username`: The unique username as a string to fetch user details.

## Parameters

The `password` parameter in `create_an_account` is hashed using pbkdf2_sha256 to ensure secure storage of the user's password.

Each function uses SQL queries defined and stored in `queries` module where `CREATE_AN_ACCOUNT` insert the new user into the database, and `GET_USER_BY_USERNAME` retrieves the user details based on their username.

## Outputs

Both functions return an instance of `User` class that represents a user in the application.

For `create_an_account` function, it creates a new user in the database with the given name, username and password and returns the created user.

For `get_user_by_username` function, it fetches the user with the given username from the database and returns its details.

## Functionality

Both functions utilize `db_cursor` as context managers establishing connection to the database, where it is used to execute queries and fetch results.

For `create_an_account`, the user-supplied password is hashed, a new user is created in the database with provided information (name, username and hashed password). If the account is successfully created, the function returns this new user.

As for `get_user_by_username`, it fetches the user data from the database with the specified username. If such a user exists, this function returns user information.

Both functions use `fetchone()` method to get a single response from the database and `tuple_to_user` utility function to convert the returned tuple into an instance of the `User` class.