# Restaurant_API_Project

## User registration and token generation endpoints 
For user registration and token generation. It provides the following functionalities:

- User registration: **/api/users** (POST) - Creates a new user with name, email, and password.
- Get current user: **/api/users/users/me/** (GET) - Displays only the current user.
- Token generation: **/token/login/** (POST) - Generates access tokens that can be used in other API calls in this project.

Example request for User Registration
<pre>
bash
echo 'POST /api/users/' \
  -H 'Content-Type: application/json' \
  -d '{
    "username": "john.doe@example.com",
    "password": "password123"
  }'
</pre>
     

     
