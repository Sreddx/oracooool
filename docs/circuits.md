# Summary

The function `get_all_circuits` is designed to fetch all the circuit entries in the database and convert each retrieved entry into a Circuit object.

# Inputs

There are no inputs to this function.

# Parameters

This function does not accept any parameters.

# Outputs

This function will return a list of Circuit objects. Each Circuit object represents a single circuit entry in the database. If an exception happens during the operation (such as a database connection issue), the function will instead return an empty list.

# Functionality

The `get_all_circuits` function starts by preparing the query to retrieve all circuits and setting up an empty tuple for the data. Then it opens a connection with the database, and with the cursor, it executes the query.

The results of the query (a list of tuples - each representing a circuit entry in the database) are then fetched, and the connection to the database is closed.

The function then proceeds to convert each tuple in the result set into a Circuit object via the `tuple_to_circuit` function. This conversion is necessary because the data fetched from the database are raw tuples and need to be converted into a more convenient and easier-to-use object format. The `tuple_to_circuit` function takes care of this conversion.

If an exception occurs during any part of this operation, the function will catch it (so the rest of the software is not affected), print the error message to the console, and safely return an empty list.