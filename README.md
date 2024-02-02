ANSWER 1:
Board Table:

Fields: board_id, board_name, created_at, etc.
List Table:

Fields: list_id, board_id (foreign key), list_name, position, etc.
Card Table:

Fields: card_id, list_id (foreign key), card_title, description, due_date, position, etc.
User Table:

Fields: user_id, username, email, password_hash, etc.
UserBoard Table (for M:M relationship between users and boards):

Fields: user_id (foreign key), board_id (foreign key).
For API endpoints:

Boards Endpoints:

/api/boards (GET, POST)
/api/boards/{board_id} (GET, PUT, DELETE)
Lists Endpoints:

/api/boards/{board_id}/lists (GET, POST)
/api/lists/{list_id} (GET, PUT, DELETE)
Cards Endpoints:

/api/lists/{list_id}/cards (GET, POST)
/api/cards/{card_id} (GET, PUT, DELETE)
Users Endpoints:

/api/users (GET, POST)
/api/users/{user_id} (GET, PUT, DELETE)
User-Board Relationship Endpoints:

/api/users/{user_id}/boards (GET, POST)
/api/users/{user_id}/boards/{board_id} (DELETE)
ANSWER 2:
To implement comments on tasks, we can introduce a new table and API endpoints :

Comment Table:

Fields: comment_id, card_id (foreign key), user_id (foreign key), text, created_at, etc.
Comments Endpoints:

/api/cards/{card_id}/comments (GET, POST)
This endpoint retrieves all comments for a specific card and allows users to add new comments.
/api/comments/{comment_id} (GET, PUT, DELETE)
This endpoint allows users to view, edit, or delete a specific comment.
Users Endpoints (if not already implemented):

/api/users/{user_id}/comments (GET)
This endpoint could retrieve all comments made by a specific user.
ANSWER 3:
Error Handling can be done on the basis of development level as follows :

HTTP Status Codes:

Use standard codes for success and failure.
Consistent Responses:

Return clear error messages and codes.
Detailed Logging:

Log relevant information for debugging.
Input Validation:

Validate user input on both client and server.
Global Exception Handling:

Catch unexpected errors and provide user-friendly messages.
Validation vs. Business Logic:

Differentiate and return relevant errors.
API Versioning:

Implement versioning for evolving APIs.
Using try - catch :

on the code level we can put async and error causing codes in try and catch block
