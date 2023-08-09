# Summary

This script/module contains functions for retrieving information about racing teams and their drivers from a PostgreSQL database using predefined SQL queries stored in a separate `queries` module.

## get_all_teams()

### Summary

This function retrieves all teams from the database.

### Inputs

None

### Parameters

None

### Outputs

This function returns a list of `Team` objects representing all teams found in the database.

### Functionality

1. It retrieves the `GET_ALL_TEAMS` SQL query string from the `queries` module.
2. It executes this SQL query on the database and fetches all returned rows.
3. For each returned row, it converts the tuple into a `Team` object and adds it to the output list.

## get_a_team()

### Summary

This function retrieves a specific team from the database.

### Inputs

`team_id` - The UUID of the team to be retrieved.

### Parameters

`team_id` - The UUID of the team to be retrieved.

### Outputs

This function returns a single `Team` object that represents the team with the provided `team_id`. If the `team_id` doesn't exist in the database, this function will return `None`.

### Functionality

1. It retrieves the `GET_A_TEAM` SQL query string from the `queries` module.
2. It executes this SQL query on the database with the `team_id` as the parameter and fetches the returned row.
3. It converts the returned tuple into a `Team` object and returns it.

## get_drivers_of_team()

### Summary

This function retrieves all drivers associated with a specific team.

### Inputs

`team_id` - The UUID of the team.

### Parameters

`team_id` - The UUID of the team.

### Outputs 

This function returns a list of `Driver` objects representing all drivers associated with the team with the provided `team_id`.

### Functionality

1. It retrieves the `GET_DRIVERS_OF_TEAM` SQL query string from the `queries` module.
2. It executes this SQL query on the database with the `team_id` as a parameter and fetches all returned rows.
3. For each returned row, it converts the tuple into a `Driver` object and adds it to the return list.