

# Sign in

```http
  POST /api/users/signin
```


Request body

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| AddUserDTO | AddUserDTO |New user info to add.



Response body

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| SendUserDTO  | SendUserDTO   | Added user info.


### Example Request Body

```json
{
  "Username": "exampleUser",
  "Password": "password123",
  "Person": {
    "FirstName": "John",
    "SecondName": "Doe",
    "LastName": "Smith",
    "Address": "123 Main St",
    "Gender": true,
    "CountryID": 1,
    "DateOfBirth": "1990-01-01T00:00:00",
    "Email": "john@example.com",
    "Notes": "Some notes about the user",
    "PreferredLanguageID": 1
  }
}

```
### Example Response Body
```json


{
  "UserID": 101,
  "Username": "exampleUser",
  "Password": "hashedPassword123",
  "Person": {
    "PersonID": 5001,
    "JoinedDate": "2024-01-01T00:00:00",
    "FirstName": "John",
    "SecondName": "Doe",
    "LastName": "Smith",
    "Address": "123 Main St",
    "Gender": true,
    "CountryID": 1,
    "DateOfBirth": "1990-01-01T00:00:00",
    "Email": "john@example.com",
    "Notes": "Some notes about the user",
    "PreferredLanguageID": 1
  }
}


```

# Log In

```http
POST /api/users/login
```

Request body

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| LoginDTO | LoginDTO |Login object.



Response body

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| JWTToken  | string   | JWT.


### Example Request Body

```json
{
  "Username": "exampleUser",
  "Password": "password123",
}

```
### Example Response Body

```json
{
  "Token": "eyJhbGciOiJIUzI1NiIsInR..."
}

```




# Schemas 

#### AddUserDTO Schema

| Parameter | Type           | Description                            |
|-----------|----------------|----------------------------------------|
| `Username` | `string`      | **Required**. Username of the user     |
| `Password` | `string`      | **Required**. Password of the user     |
| `Person`   | `AddPersonDTO` | **Required**. Person details         |

---

### AddPersonDTO Schema

| Property             | Type       | Description                                |
|----------------------|------------|--------------------------------------------|
| `FirstName`          | `string`   | **Required**. First name of the person     |
| `SecondName`         | `string`   | (optional) Middle name of the person       |
| `LastName`           | `string`   | (optional) Last name of the person         |
| `Address`            | `string`   | (optional) Address of the person           |
| `Gender`             | `bool`     | (optional) Gender of the person            |
| `CountryID`          | `byte`     | **Required**. Country ID of the person     |
| `DateOfBirth`        | `DateTime` | **Required**. Date of birth                |
| `Email`              | `string`   | (optional) Email address                   |
| `Notes`              | `string`   | (optional) Additional notes                |
| `PreferredLanguageID`| `short`    | **Required**. Preferred language ID        |




### SendUserDTO Schema

| Property  | Type             | Description                               |
|-----------|------------------|-------------------------------------------|
| `UserID`  | `int`            | **Required**. Unique ID of the user       |
| `Username`| `string`         | **Required**. Username of the user        |
| `Password`| `string`         | **Required**. Password of the user        |
| `Person`  | `SendPersonDTO`  | **Required**. Details of the person       |

---

### SendPersonDTO Schema

| Property             | Type       | Description                                |
|----------------------|------------|--------------------------------------------|
| `PersonID`           | `int`      | **Required**. Unique ID of the person      |
| `JoinedDate`         | `DateTime` | **Required**. Date when the person joined  |
| `FirstName`          | `string`   | **Required**. First name of the person     |
| `SecondName`         | `string`   | (optional) Middle name of the person       |
| `LastName`           | `string`   | (optional) Last name of the person         |
| `Address`            | `string`   | (optional) Address of the person           |
| `Gender`             | `bool`     | (optional) Gender of the person            |
| `CountryID`          | `byte`     | **Required**. Country ID of the person     |
| `DateOfBirth`        | `DateTime` | **Required**. Date of birth                |
| `Email`              | `string`   | (optional) Email address                   |
| `Notes`              | `string`   | (optional) Additional notes                |
| `PreferredLanguageID`| `short`    | **Required**. Preferred language ID        |




### LoginDTO Schema
| Property  | Type             | Description                               |
|-----------|------------------|-------------------------------------------|
| `Username`| `string`         | **Required**. Username of the user        |
| `Password`| `string`         | **Required**. Password of the user        |
 
