## Summary
This code contains two functions: `retrieve_all_messages_by_user` and `upload_message` to manage messages from users and a chatbot in a PostgreSQL database.

## Inputs
The input to both functions is the `user_id` parameter, which is used to either select or upload messages for a specific user. The `user_id` is a unique identifier (UUID) for users. 
In `upload_message`, we also have two additional inputs `content` and `by_user`. `content` is the text message that is going to be uploaded and `by_user` is a boolean parameter indicating whether the message is created by the user or by the chatbot.

## Parameters
Each function takes three parameters:
1. `user_id: uuid.UUID` (`retrieve_all_messages_by_user` and `upload_message`): A unique user identifier.
2. `content: str` (`upload_message`): The text message to upload to the database.
3. `by_user: bool` (`upload_message`): A flag indicating if the message is by the user or by the chatbot.

## Outputs
1. `retrieve_all_messages_by_user` returns all messages from a specific user if any exist, if no messages are found a 'No messages found for this user' string is returned.
2. `upload_message` does not return any value, but the state of the database changes as a new record is inserted.

## Functionality
1. `retrieve_all_messages_by_user`: This function queries the PostgreSQL database `messages` table for all messages by a user using the provided `user_id`. If any records are found, it fetches (all) messages and returns them. If no records are retrieved, it returns a string informing that no messages were found.

2. `upload_message`: This function inserts a new message into the PostgreSQL database `messages` table, the message is associated with a `user_id` and also records whether the message is by the user or by the chatbot with the `by_user` parameter. It commits this change to the database to persist the message. The function doesn’t return any value.