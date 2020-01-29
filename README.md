# Build Week
Backend Setup

# Initializing the Project
## Requirements: Postman

1) Install Postman.
2) Create a "New Request".
3) Select a "GET" request for now.
4) Use `localhost:4040` for the address.
5) OR if you are using Heroku, use this link for the address instead - "https://build-week-backend.herokuapp.com/".
6) Send the request.
7) You should get the message "Welcome to the server!".

# Users
## Register and Login

JSON requirements for users:
```
{
"firstName": "First Name",
"lastName": "Last Name",
"email": "Email",
"password": "Password"
}
```

1) At the end of `localhost:4040` (or the Heroku link "https://build-week-backend.herokuapp.com/") in your address, put `api/auth` to use authorizationfor these routes. In example `localhost:4040/api/auth`.
For all of the following instructions you may replace `localhost:4040` with the Herokuu link if you want to use the hosted server.

## To Register

2) Select "POST" as the request.
3) The address should be `localhost:4040/api/auth/register`. This is your registration endpoint.
4) Under "Body" choose the "JSON" format in which you will register with. The JSON format should look similar to the following -
```
{
"firstName": "Your First Name Here",
"lastName": "Your Last Name Here",
"email": "Your Email Here",
"password": "Your Password Here"
}
```
5) Send that "POST" request and you will get back JSON information with an `id` included. You are now added as a user to the database.

## To Login

7) Right click that registration request and duplicate it. In the address bar of the duplicated request, remove `register` and replace it with `login`. In example - `localhost:4040/api/auth/login`. Keep the JSON data as it is.
8) Send this "POST" request. You will be logged in and a message will be returned - "Welcome "firstName lastName"!" and a "token".
9) Inside the quotes for the "token" value is your authorization, copy that entire string.
10) Click on the headers tab, and add a new header. The header must be called
`Authorization`. And the value must be your `Token` string.

## To View Existing Users

1) Duplicate this last request, which will in turn duplicate the `Authorization` header with the `Token` string that you added previously. If there is no token, the server will respond with an error. Tokens last 24 hours after a login.
2) Change the address to `localhost:4040/api/users` to recieve back ALL users, or `localhost:4040/api/users/:id` (Where `:id` is the id of the user) to get back a specific user with that Id.
3) Change the request back to a "GET" and send the request to recieve the JSON information back. 

## Updating the User

1) Using a "PUT" request to the address of `localhost:4040/api/users/:id`, you would select a user by its id, and use the following JSON information to update the existing user.
```
{
    "email": "Updated Email Here",
    "password": "Updated Password Here",
    "firstName": "Updated First Name Here",
    "lastName": "Updated Last Name Here"
}
```
2) Your updates will be shown in the return preview window in Postman

## Deleting the User

1) Using a "DELETE" request to the address of `localhost:4040/api/users/:id` you would select a user by its id, and send the "DELETE" request. 
2) That user is should now be deleted from the database.
