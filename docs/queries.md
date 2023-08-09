# Documentation for SQL Queries Operator

## Summary
The SQL Queries Operator is a module that contains various SQL query strings to interact with a database that stores information about racing drivers, teams, users, groups and racing circuits. Also included are queries for predicting race results and updating user points based on these predictions.

## Inputs
The inputs for each query vary depending on the requirement of the SQL statement. They could be values to be inserted into the database, IDs to select records, or variables to be compared and manipulated within the queries.

## Parameters
The parameters for this operator are the variables (%s) present inside the SQL queries. These constitutes IDs for the select operations, values for insertion, and the conditions for updating, deletion and other operations. 

- IDs are typically used in 'SELECT', 'DELETE', 'UPDATE' operations to choose specific records from the database. 
- The values to be inserted are parameters in the 'INSERT' queries and represent data like names, usernames, password, description, owner etc. for creating new records. 
- Conditions in the 'UPDATE' operations also consist of parameters which define how the existing data will be modified.

## Outputs
The outputs are the results of these SQL query strings when they are executed. The type of output widely varies according to the SQL query. It can be the data selected from tables(`SELECT`), the number of rows affected(`UPDATE`, `DELETE`), the record that was inserted(`INSERT`), etc.

## Functionality
The list of functionality provided by this operator includes:
- **get_all_drivers:** This query retrieves all records from the 'drivers' table.
- **get_all_teams:** This query fetches all records from the 'teams' table.
- **get_a_team:** Selects a team record from the 'teams' table where the ID matches the provided parameter.
- **get_drivers_of_team:** Collects all drivers of a particular team by joining 'drivers' and 'teams' tables and filtering with the team's ID.
- **create_an_account:** Inserts a new user record into the 'users' table.
- **get_user_by_username:** Selects a user record from users table where the username matches the provided parameter.
- **get_my_groups:** Gets all groups a user belongs to by joining 'user_belongs_to_group' and 'groups' tables and filtering with the user's ID.
- **create_a_group:** Inserts a new group record into the 'groups' table.
- **add_user_to_group:** Inserts a new record into 'user_belongs_to_group'.
- **remove_user_from_group:** Deletes a record from the 'user_belongs_to_group' table based on the user and group ID.
- **get_all_users_from_group:** Collects all users from a particular group by joining 'users' and 'user_belongs_to_group' tables and filtering with the group's ID.
- **get_all_circuits:** Retrieves all records from the 'circuits' table.
- **predict_circuit:** Predicts the race results for a particular circuit by joining 'next_results' and 'drivers' table and filtering with the circuit's ID.
- **get_all_users_ordered_by_points:** Lists all users ordered descendingly by their points.
- **save_preds:** Inserts a new prediction made by a user for a particular circuit and year into 'predictions'.
- **update_user_points:** Updates a user's points by adding a specific number to the existing points.
- **get_prediction_from_user:** Fetches a prediction made by a user for a given circuit. 
Each of this functionality is self contained and can be used independently based on the requirements.