# Summary

This code operator provides a functionality for creating and retrieving user predictions related to a circuit in a racing model, as well as updating points for correct predictions.

## `create_prediction`

### Inputs

- `user_id`: A UUID identifying the user making the prediction
- `circuit_id`: A UUID identifying the circuit the user is making a prediction for
- `preds`: A list of dictionaries, each representing a prediction, where each dictionary contains a 'position' and 'driver'

### Functionality

This operator serves to allow a user to make a prediction for a specific circuit and saves this prediction into the database. Each prediction consists of a 'position' and 'driver'. The user's points are then updated based on the number of correct predictions that match the system's prediction model. For each match, the user's points are increased by 10. If the user scores points, this operator also updates the points in the database.

### Outputs

This function does not return any output except in the case of an exceptions where the error is printed.

## `get_prediction`

### Inputs

- `user_id`: A UUID identifying the user
- `circuit_id`: A UUID identifying the circuit

### Functionality

This operator retrieves a user's prediction for a specific circuit from the database. The user's prediction is then converted from tuple form into a `Prediction` object. In case of an error during the process, the error is printed.

### Outputs

Outputs a `Prediction` object representing a user's prediction for a given circuit.