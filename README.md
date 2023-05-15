# Restaurant_API_Project

## User registration and token generation endpoints 
For user registration and token generation. It provides the following functionalities:

- User registration: **/api/users** (POST) - Creates a new user with name, email, and password.
- Get current user: **/api/users/users/me/** (GET) - Displays only the current user.
- Token generation: **/token/login/** (POST) - Generates access tokens that can be used in other API calls in this project.

### Example request for User Registration
<pre>
POST /api/users/
Content-Type: application/json

{
  "username": "john.doe@example.com",
  "password": "password123"
}
</pre>

### Example request for Get current user
<pre>
GET /api/users/users/me/
Authorization: Bearer <user-token>
</pre>

### Example request for Token generation
<pre>
POST /token/login/
Content-Type: application/json

{
  "username": "john.doe",
  "password": "password123"
}
</pre>


## Menu items endpoints                                                                                                                                                    Endpoints for managing menu items. It supports various operations based on user roles. The following endpoints and functionalities are available:

### List Menu Items
- Endpoint: **/api/menu-items**
- Role: Customer, Manager, Delivery Crew
- Method: GET
- Purpose: Lists all menu items. Returns a 200 - Ok HTTP status code.

### Create Menu Item (Manager Only) - User with other role would get 403 - Unauthorized HTTP status code.
- Endpoint: **/api/menu-items**
- Role: Manager
- Method: POST
- Purpose: Creates a new menu item and returns 201 - Created HTTP status code.


     
