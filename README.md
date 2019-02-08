This is a simple todo-app without any UI made following the REST API standard. Made as oriented by Andrew Mead in his NodeJS course.

There's a live version of the application at http://todo.rodrigovieira.work. If you prefer to install it locally, follow the Installation instructions. Otherwise, go straigth to the Usage section.

# Installation 

First, make sure you have node installed on your machine.

Then, clone the project. Run:

```
git clone https://github.com/rodriigovieira/todo-app.git
```

Second, install all project dependencies. Run:

```
yarn install
```

And voilà - you've successfully configured the project in your machine.

# Usage

To start the app, just run:

```
yarn start
```

The app will start automatically at port 3000.

The API requests can be made with your favorite client, although a UI-rich client such as Postman or Insomnia is recommended. The POST requests ought to be made sending data with JSON. Clearer instructions are provided bellow.

You can make the following requests:

### Authentication Requests

**POST /users** - create a user. Example:

```
{
  "email": "email@example.com",
  "password": "password"
}
```

After creating the user, the x-auth token will be returned in the Headers section. You should copy the x-auth in order to be able to perform the CRUD operations with the todos.

**POST /users/login** - return the x-auth if successfull login attempt is made. Example: (assuming the user exists and it matches)

```
{
  "email": "email@example.com",
  "password": "password"
}
```

If the data inserted is accurate, the x-auth token will be returned in the Headers section. You can refer to this route in case you would like to know your x-auth token.

**GET /users/me** - return the user data. 

For this request to work, it's necessary that you specifiy the x-auth token in the Header section. You can refer to the previous requests to know how to find your x-auth token.

This request will return the user id and email.

**DELETE /users/me/token** - remove the user's token in the database.

This request will remove the token in the database, essentialy logging out the user. To get a new token, just make another POST request at /users/login and a new token will be generated.

Same as before: it's necessary to specify the x-auth token in the Headers section.
