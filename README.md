This is a simple todo-app without any UI made following the REST API standard.

# Installation 

First, make sure you have node installed on your machine.

Then, clone the project. Run:

```
git clone https://github.com/rodriigovieira/mongo-app.git
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

You can make the following requests:

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


