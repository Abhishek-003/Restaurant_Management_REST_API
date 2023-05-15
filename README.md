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


## Menu items endpoints
Endpoints for managing menu items. It supports various operations based on user roles. The following endpoints and functionalities are available:

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

### Get Single Menu Item
- Endpoint: **/api/menu-items/{menuItem}**
- Role: Customer, Delivery Crew, Manager
- Method: GET
- Purpose: Lists a single menu item.

### Update Single Menu Item (Manager Only) - User with other role would get 403 - Unauthorized HTTP status code.
- Endpoint: **/api/menu-items/{menuItem}**
- Role: Manager
- Methods: PUT, PATCH
- Purpose: Updates a single menu item.

### Delete Menu Item (Manager Only) - User with other role would get 403 - Unauthorized HTTP status code.
- Endpoint: **/api/menu-items/{menuItem}**
- Role: Manager
- Method: DELETE
- Purpose: Deletes a menu item.

## User Group Management Endpoints
Endpoints for managing user groups. It includes functionalities for managing managers and delivery crew. The following endpoints and functionalities are available:

### Get Managers
- Endpoint: **/api/groups/manager/users**
- Role: Manager
- Method: GET
- Purpose: Returns all managers.

### Assign Manager
- Endpoint: **/api/groups/manager/users**
- Role: Manager
- Method: POST
- Purpose: Assigns the user in the payload to the manager group and returns 201 - Created.

### Remove Manager
- Endpoint: **/api/groups/manager/users/{userId}**
- Role: Manager
- Method: DELETE
- Purpose: Removes this particular user from the manager group. Returns 200 - Success if everything is okay. If the user is not found, returns 404 - Not found.

### Get Delivery Crew
- Endpoint: **/api/groups/delivery-crew/users**
- Role: Manager
- Method: GET
- Purpose: Returns all delivery crew.

### Assign Delivery Crew
- Endpoint: **/api/groups/delivery-crew/users**
- Role: Manager
- Method: POST
- Purpose: Assigns the user in the payload to the delivery crew group and returns 201 - Created.

### Remove Delivery Crew
- Endpoint: **/api/groups/delivery-crew/users/{userId}**
- Role: Manager
- Method: DELETE
- Purpose: Removes this user from the delivery crew group. Returns 200 - Success if everything is okay. If the user is not found, returns 404 - Not found.


     
