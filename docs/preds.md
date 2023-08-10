## Summary

This Flask application provides an API for a web application that allows users to make and retrieve predictions for Formula 1 races. Users can make predictions by sending a POST request to the "/preds" endpoint with their user id, circuit id, and a list of predictions. They can also retrieve predictions by sending a GET request to the "/preds/<user_id>/<circuit_id>" endpoint with the corresponding user id and circuit id.

## Inputs

- JSON data: The POST request should include a JSON payload with the following fields:
  - "circuit": The id of the circuit for which the prediction is being made.
  - "preds": A list of three predictions.
- Path parameters: The GET request should include the user id and circuit id as path parameters.

## Parameters

- None

## Outputs

- JSON response: The API returns JSON responses with the following fields:
  - For the "/preds" endpoint:
    - "msg": A success message if the prediction was created successfully.
    - "err": An error message if there was an issue with the request or server.
  - For the "/preds/<user_id>/<circuit_id>" endpoint:
    - "prediction": The prediction object retrieved from the database.
    - "err": An error message if there was an issue with the request or server.

## Functionality

The Flask application defines two routes: "/preds" for creating predictions and "/preds/<user_id>/<circuit_id>" for retrieving predictions.

### Create Prediction ("/preds" endpoint)

- Method: POST
- Required authentication: JWT token in the "cookies" location
- Steps:
  1. Check if the request has the "Content-Type" header set to "application/json". If not, return a "missing 'application/json' header" error response.
  2. Get the JSON payload from the request.
  3. Extract the user id from the JWT token.
  4. Extract the circuit id from the payload.
  5. Extract the list of predictions from the payload.
  6. Check if the length of the predictions list is not equal to 3. If not, return an "invalid data" error response.
  7. Create a prediction in the database using the user id, circuit id, and predictions list.
  8. Return a "done" success response.

### Get Prediction ("/preds/<user_id>/<circuit_id>" endpoint)

- Method: GET
- Required authentication: JWT token in the "cookies" location
- Steps:
  1. Validate the user id and circuit id path parameters.
  2. Parse the user id and circuit id values.
  3. Retrieve the prediction from the database using the user id and circuit id.
  4. Return the prediction object in a success response.

Both endpoints handle authentication errors, JSON header errors, and server errors by returning appropriate error responses.