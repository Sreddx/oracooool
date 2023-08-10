# Markdown Documentation for the Flask Chatbot Blueprint

## Summary
This is an Flask blueprint for a chatbot operator, part of a larger web application to provide Formula 1 information and predictions, allowing users to interact with the chatbot and retrieve their messages.

## Inputs

The input to these routes are primarily HTTP Requests:

1. `GET /`: for checking the status of the bot.
2. `POST /send_prompt`: for sending a prompt message to the bot, with a JSON payload containing the "prompt".
3. `GET /get_messages`: for getting a list of messages that have been exchanged with the bot.

The `message_to_prompt` function also receives a JSON payload with the key "prompt".

## Parameters

Various parameters are used throughout the code:

1. `openai.api_key`: API key for OpenAI's GPT-3 model.
2. `engine`: Name of the model used for generating responses. 
3. `prompt`: The message from the user which is handed over to GPT-3 model to get an AI-generated response.
4. `temperature`: Controls randomness in the AI's responses. Higher values result in more random outputs.
5. `max_tokens`: The maximum length of the model's response.
6. `frequency_penalty`: Controls how much the model should avoid using low-frequency words.
7. `presence_penalty`: Controls how much the model should consider the existing context while formulating a response.

## Outputs

The outputs from these routes are HTTP Responses:

1. `GET /`: Response from the OpenAI Model's `retrieve` function, formatted with a 200 status code indicating successful operation.
2. `POST /send_prompt`: Response from the `openai.Completion.create` method, structured in JSON with a 200 status code.
3. `GET /get_messages`: A response containing all messages from a user, structured in JSON with a 200 status code.

## Functionality

The provided code can be broken down into following parts:

1. **check_bot_status**: This function retrieves the status of the OpenAI model `"text-davinci-003"` and returns it to the user. If an error occurs, it returns the error message with a 500 status code.
2. **message_to_prompt**: This function takes in a prompt from the user, passes it to the OpenAI model for generating a response, and returns the response. In case of an error, it returns the error message.
3. **get_messages**: This function retrieves all the messages exchanged by a user with the bot, and returns them. If an error happens, it returns the error message.