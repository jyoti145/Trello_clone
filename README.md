# ANSWER 1:
1. Board Table:
   - Fields: board_id, board_name, created_at, etc.

2. List Table:
   - Fields: list_id, board_id (foreign key), list_name, position, etc.

3. Card Table:
   - Fields: card_id, list_id (foreign key), card_title, description, due_date, position, etc.

4. User Table:
   - Fields: user_id, username, email, password_hash, etc.

5. UserBoard Table (for M:M relationship between users and boards):
   - Fields: user_id (foreign key), board_id (foreign key).

For API endpoints:

1. Boards Endpoints:
   - /api/boards (GET, POST)
   - /api/boards/{board_id} (GET, PUT, DELETE)

2. Lists Endpoints:
   - /api/boards/{board_id}/lists (GET, POST)
   - /api/lists/{list_id} (GET, PUT, DELETE)

3. Cards Endpoints:
   - /api/lists/{list_id}/cards (GET, POST)
   - /api/cards/{card_id} (GET, PUT, DELETE)

4. Users Endpoints:
   - /api/users (GET, POST)
   - /api/users/{user_id} (GET, PUT, DELETE)

5. User-Board Relationship Endpoints:
   - /api/users/{user_id}/boards (GET, POST)
   - /api/users/{user_id}/boards/{board_id} (DELETE)
   - 

  # ANSWER 2:
  To implement comments on tasks, we can introduce a new table and API endpoints :

1. Comment Table:
   - Fields: comment_id, card_id (foreign key), user_id (foreign key), text, created_at, etc.

2. Comments Endpoints:
   - /api/cards/{card_id}/comments (GET, POST)
     - This endpoint retrieves all comments for a specific card and allows users to add new comments.
   - /api/comments/{comment_id} (GET, PUT, DELETE)
     - This endpoint allows users to view, edit, or delete a specific comment.

3. Users Endpoints (if not already implemented):
   - /api/users/{user_id}/comments (GET)
     - This endpoint could retrieve all comments made by a specific user.
       
    
   # ANSWER 3:
   Error Handling can be done on the basis of development level as follows :

1. HTTP Status Codes:
   - Use standard codes for success and failure.

2. Consistent Responses:
   - Return clear error messages and codes.

3. Detailed Logging:
   - Log relevant information for debugging.

4. Input Validation:
   - Validate user input on both client and server.

5. Global Exception Handling:
   - Catch unexpected errors and provide user-friendly messages.

6. Validation vs. Business Logic:
   - Differentiate and return relevant errors.

7. API Versioning:
    - Implement versioning for evolving APIs.

8. Using try - catch:
 - on the code level we can put async and error causing codes in try and catch block
