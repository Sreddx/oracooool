# Summary
This web application functionalities feature a group-based feature that allows authenticated users to get groups, join or remove groups, create a new group, get users in a group and get all users. 

# Inputs:
The application accepts various HTTP methods, namely POST and GET, through which JSON payloads or URL parameters are passed. The user inputs are the information from the user’s JWT token and the group handling requests and endpoints.

1. **User JWT token**: The users' identity is fetched using the JWT token provided by the user in the cookies.
2. **Group ID (str)**: An identifier for unique groups. This is used in several endpoints such as '/group_id/people', '/group_id/join' and '/group_id/remove'.
3. **'name' and 'description' (str)**: These are used when creating a new group through the '/' POST request.

# Parameters:
Each function decorator defined corresponds to an HTTP endpoint. Endpoint details and the respective parameters they handle are as follows:

1. **@groups.route("/", methods=["GET"])**: This route doesn't accept any parameter, it lists the groups available to the currently authenticated user.
2. **@groups.route("/<group_id>/people", methods=["GET"])**: Accepts a group_id as a URL parameter, returns all users in the specified group.
3. **@groups.route("/<group_id>/join", methods=["POST"])**: Accepts a group_id, this endpoint allows a user to join a specified group.
4. **@groups.route("/<group_id>/remove", methods=["POST"])**: Accepts a group_id, this endpoint allows a user to leave a specified group.
5. **@groups.route("/", methods=["POST"])**: Accepts JSON payload that includes 'name' and 'description'. This route is used to create a new group.
6. **@groups.route("/allusers", methods=["GET"])**: This route doesn't accept any parameter, it lists all users in the application.

# Outputs:
All functionalities output a JSON response with varying details based on the functionality's boundary:

1. **User Object**: A JSON object containing a user's details.
2. **Group Object**: A JSON object containing a group's details.
3. **Errors**: If there is any error (like incorrect inputs or server problems), a JSON object containing the error description is returned.

# Functionality:

The application user-based access control leveraging blueprints and route decorators from Flask and JSON-web-tokens for user authentication. This offers handy group manipulations. Data parsing, validation, and exception handling are performed for each endpoint. The database function module `db.func.groups` is used to perform the necessary data handling for the groups. In case of exceptions, appropriate HTTP response codes and error messages are bundled into a response payload.