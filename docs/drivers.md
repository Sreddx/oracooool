# get_all_drivers Function Documentation

## Summary
The `get_all_drivers` function is used to retrieve all records from the 'drivers' table in a Postgres database and map the results to a list of Driver objects.

## Inputs
This function does not take any inputs.

## Parameters
There is no parameter for this function since it is meant to retrieve all the data from the drivers' table.

## Outputs
The function returns a list of `Driver` objects. Each `Driver` object represents a single record in the 'drivers' table. Each attribute of the `Driver` object corresponds to a field in the table.

## Functionality
The `get_all_drivers` function performs the following steps:

1.  Defines a query named `q` to get all driver records from the database. The SQL query is obtained from `queries.GET_ALL_DRIVERS`.

2.  Creates an empty tuple named `data`.

3.  Opens a database connection and creates a cursor object named `cur` using `db_cursor()`. The connection is managed as a context, ensuring that it gets properly closed at the end.

4.  Execute the SQL query `q` with `data` passed as parameters. This is done by calling the `execute` method of the cursor object `cur`.

5.  Retrieves all the records returned from the database query as a list of tuples using the `fetchall` method of the cursor object `cur`. This result is stored in the variable `result`.

6.  Converts each tuple in `result` to a `Driver` object by using a list comprehension and the `tuple_to_driver` utility function from the `db.utils` module. The list of `Driver` objects is returned by the function.