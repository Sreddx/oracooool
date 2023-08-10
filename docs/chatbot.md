# Summary
The `chatbot` blueprint is a Flask route that handles requests related to a chatbot feature in a web application. It allows users to check the status of the chatbot model, send a message to the chatbot for a response, and retrieve previously sent chatbot messages.

# Inputs
- None

# Parameters
- None

# Outputs
- Check Bot Status: Returns the status of the chatbot model.
- Message to Prompt: Returns the response from the chatbot model based on the provided prompt.
- Get Messages: Returns all previous chatbot messages for the authenticated user.

# Functionality
The `chatbot` blueprint consists of several routes:

1. `check_bot_status()`: A GET route that retrieves the status of the chatbot model. It sends a request to the OpenAI API to retrieve the current status of the "text-davinci-003" model.

2. `message_to_prompt()`: A POST route that sends a prompt to the chatbot model and receives a response. It expects a JSON body with a "prompt" key containing the user's message. It sends a request to the OpenAI API to generate a completion based on the provided prompt using the "text-davinci-003" model. The generated response is returned as a JSON response.

3. `get_messages()`: A GET route that retrieves all previous chatbot messages for the authenticated user. It requires JWT authentication and retrieves the user's ID from the JWT token. It sends a request to the database to retrieve all messages associated with the user's ID. The response containing the messages is returned as a JSON response.