#API Documentation

## Install dependencies

npm i body-parser express morgan mysql nodemon jwt-simple bcryptjs sequelize

````json
"dependencies": {
    "bcrypt": "^5.0.0",
    "bcryptjs": "^2.4.3",
    "body-parser": "^1.19.0",
    "express": "^4.17.1",
    "express-validator": "^6.5.0",
    "jwt-simple": "^0.5.6",
    "morgan": "^1.10.0",
    "mysql2": "^2.1.0",
    "nodemon": "^2.0.4",
    "sequelize": "^5.21.12"
  }
````

## Run server

\Delilah-API\api>npm run dev

```javascript
npm run dev
http://localhost:3000/

node index.js
http://localhost:3000/
```

Database, tables, and content are generete automatic.
See more in db.js

## Test API in POSTMAN or similar.

GET - http://localhost:3000/

```javascript
{
  Api Delilah.
}
```

## Get all Products

GET - http://localhost:3000/api/products

```json
[
  {
    "id": 1,
    "name": "Lomo Pizza",
    "price": 300,
    "stock": true,
    "createdAt": "2020-06-18T03:17:02.000Z",
    "updatedAt": "2020-06-18T03:17:02.000Z"
  },
  {
    "id": 2,
    "name": "Burger Queen",
    "price": 500,
    "stock": true,
    "createdAt": "2020-06-18T03:17:02.000Z",
    "updatedAt": "2020-06-18T03:17:02.000Z"
  },
  {
    "id": 3,
    "name": "Tomacco",
    "price": 800,
    "stock": true,
    "createdAt": "2020-06-18T03:17:02.000Z",
    "updatedAt": "2020-06-18T03:17:02.000Z"
  }
]
```

## New Product

ATENTION, for this POST you need to be logging as Admin.

POST - http://localhost:3000/api/users/login

```json
In Body-raw includes.

{
    "email": "admin@baberoot.com",
    "password": "123qwe",
    "admin": "123123"
}

Return TOKEN

POST - http://localhost:3000/api/products

Include Admin Token in headers

user-token - token

In Body pass the new Product.

{
	"name": "Asado para 4",
    "price": 1000,
    "stock": 1
}

If its OK, res.status(200).json

{
    "id": 4,
    "name": "Asado para 4",
    "price": 1000,
    "stock": true,
    "updatedAt": "2020-06-18T10:37:36.438Z",
    "createdAt": "2020-06-18T10:37:36.438Z"
}

```

## Update Product

Include Admin Token in headers

PUT - http://localhost:3000/api/products/4

```json
{
	"name": "Asado para 4",
    "price": 800,
    "stock": 1
}

Return

{
    "success": "Modificado correctamente."
}
```

## Delete Product

Include Admin Token in headers

DELETE - http://localhost:3000/api/products/4

```json
{
  "success": "Producto borrado correctamente."
}
```

## Get all user

Include Admin Token in headers

GET - http://localhost:3000/api/users

```json
[
  {
    "id": 1,
    "username": "Admin",
    "name": "root",
    "lastname": "babe",
    "email": "admin@baberoot.com",
    "phone": "351235",
    "direction": "holliwood 123",
    "password": "$2a$08$be/9I426l9j3A7CmfXmB7.3LlEdxbPz7YgFnuX1PY4fcixYUrTIKu",
    "admin": 123123,
    "createdAt": "2020-06-18T10:50:41.000Z",
    "updatedAt": "2020-06-18T10:50:41.000Z"
  },
  {
    "id": 2,
    "username": "JohnDoe",
    "name": "John",
    "lastname": "Doe",
    "email": "JohnDoe@baberoot.com",
    "phone": "354235",
    "direction": "holliwood 123",
    "password": "$2a$08$Cus7qzIFJtJ2aTXuwcBCjeKDL0qOjQjKRA9VkN1WmH9LEWFlepwZy",
    "admin": null,
    "createdAt": "2020-06-18T10:50:41.000Z",
    "updatedAt": "2020-06-18T10:50:41.000Z"
  },
  {
    "id": 3,
    "username": "2JohnDoe",
    "name": "2John",
    "lastname": "2Doe",
    "email": "2JohnDoe@baberoot.com",
    "phone": "364235",
    "direction": "holliwood 123",
    "password": "$2a$08$RIHjcJu1DqsAOZA1cfx0peO/Hjk2p6XOscxaaDMHYGN2OGLBftbwO",
    "admin": null,
    "createdAt": "2020-06-18T10:50:41.000Z",
    "updatedAt": "2020-06-18T10:50:41.000Z"
  }
]
```

## Create new user

POST - http://127.0.0.1:3000/api/users/register

In Body-raw pass

```json
{
"username": "johndoe2",
"name": "john2",
"lastname": "doe2",
"email": "johndo2e@user.com",
"phone": "351235",
"direction": "holliwood 123",
"password": "$123qwe"
}

Response the new User.

{
    "id": 4,
    "username": "johndoe2",
    "name": "john2",
    "lastname": "doe2",
    "email": "johndo2e@user.com",
    "phone": "351235",
    "direction": "holliwood 123",
    "password": "$2a$08$.7i2A0TJz/HMAlaT92MUvelEnQOIiblAujxwybFPKODWiolZmlySu",
    "updatedAt": "2020-06-18T10:56:16.687Z",
    "createdAt": "2020-06-18T10:56:16.687Z"
}
```

---

## Modificate User

PUT - http://127.0.0.1:3000/api/users/2

Include User Token in headers
In Body-raw pass

```json
{
  "lastname": "doee",
  "email": "johndoee@user.com",
  "phone": "241235",
  "direction": "Los Angeles 123"
}
```

## Delete User

DELETE - http://localhost:3000/api/users/2

Include Admin Token in headers

````json
{
    "success": "Usuario borrado correctamente."
}
````
