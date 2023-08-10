# ChatComponent Documentation

## Summary 

The `ChatComponent` is a functional component in React which manages and represents the chat interface of a web application to interact with "Oracooool" - a Formula 1 virtual assistant.

## Inputs 

- User input: The user input is taken from the `MessageInput` component provided by Chatscope. This input is further processed and pushed into an array of messages maintained in the component state.

## Parameters 

The `ChatComponent` leverages state parameters managed with React's `useState` hook:

- `messages`: This state variable maintains an array of messages. Each message is an object containing the text (`message`), the time when the message was sent (`sentTime`), and the sender (`sender`).

- `isTyping`: A state variable that handles the typing indicator's visibility for the assistant in the chat application.

The `handleSend` and `processMessageToChatGPT` methods use the following parameters:

- `message`: The text a user writes in the chat's input field.

- `prompt`: The user's message that's sent to the chatbot for processing.

## Outputs 

There are two primary outputs returned by the `ChatComponent`:

- An array of `Message` components representing a conversation with the virtual assistant.

- A `TypingIndicator` component that's displayed when the `isTyping` status is `true`.

## Functionality 

Two functions in this component manages the chat system:

- `handleSend`: It's the callback for the `MessageInput` component's `onSend` prop. It structures the user input as a message and adds it to the `messages` array. It also sets `isTyping` to `true` and starts the processing of the user's message using the `processMessageToChatGPT` function.

- `processMessageToChatGPT`: This function sends the user's message to a chatbot API hosted at `"http://0.0.0.0:5001/chatbot/send_prompt"` for processing. The response from the chatbot API is structured as a message and added to the `messages` array, afterwards `isTyping` is set to `false` to hide the typing indication.

### Rendering

The `return` section of `ChatComponent` organises and renders the chat UI using components and styles from the Chatscope library. The rendered output includes a chat container, a list of messages (including any typing indicators), and an input field for the user to type their message.