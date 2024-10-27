
#  Login & Sign in APIs

### This file contains the Login & Sign in APIs



# Users Sign in

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
# Institutions Sign in

```http
  POST api/institutions/signin
```


Request body

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| CreateInstitutionDTO | CreateInstitutionDTO |New institution info to add.



Response body

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| sendInstitutionDTO  | sendInstitutionDTO   | Institution response object.


### Example Request Body

```json
{
  "Latitude": "40.7128 N",
  "Longitude": "74.0060 W",
  "InstitutionName": "Example University",
  "WebsiteURL": "https://exampleuniversity.edu",
  "InstitutionID": 2001,
  "EstablishedYear": "1850-01-01T00:00:00",
  "Username": "exampleUser",
  "Password": "password123",
  "Notes": "Some notes about the institution",
  "PreferredLanguageID": 1,
  "CountryID": 1
}

```

### Example Response Body


```json

{
  "InstitutionID": 2001,
  "Latitude": "40.7128 N",
  "Longitude": "74.0060 W",
  "InstitutionName": "Example University",
  "WebsiteURL": "https://exampleuniversity.edu",
  "EstablishedYear": "1850-01-01T00:00:00",
  "Username": "exampleUser",
  "Password": "hashedPassword123",
  "Notes": "Some notes about the institution",
  "PreferredLanguageID": 1,
  "CountryID": 1
}

```

# Log In (for users and institutions)

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
| `Username` | `string`      | **Required**. Username of the user  MinLength(5)   |
| `Password` | `string`      | **Required**. Password of the user  MinLength(8)   |
| `Person`   | `AddPersonDTO` | **Required**. Person details                     |

---

### AddPersonDTO Schema

| Property             | Type       | Description                                |
|----------------------|------------|--------------------------------------------|
| `FirstName`          | `string`   | (optional) First name of the person     |
| `SecondName`         | `string`   | (optional) Middle name of the person       |
| `LastName`           | `string`   | (optional) Last name of the person         |
| `Address`            | `string`   | (optional) Address of the person           |
| `Gender`             | `bool`     | (optional) Gender of the person            |
| `CountryID`          | `byte`     | **Required**. Country ID of the person     |
| `DateOfBirth`        | `DateTime` | (optional). Date of birth                |
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
| `FirstName`          | `string`   | (optional) First name of the person     |
| `SecondName`         | `string`   | (optional) Middle name of the person       |
| `LastName`           | `string`   | (optional) Last name of the person         |
| `Address`            | `string`   | (optional) Address of the person           |
| `Gender`             | `bool`     | (optional) Gender of the person            |
| `CountryID`          | `byte`     | **Required**. Country ID of the person     |
| `DateOfBirth`        | `DateTime` | (optional). Date of birth                |
| `Email`              | `string`   | (optional) Email address                   |
| `Notes`              | `string`   | (optional) Additional notes                |
| `PreferredLanguageID`| `short`    | **Required**. Preferred language ID        |




### LoginDTO Schema
| Property  | Type             | Description                               |
|-----------|------------------|-------------------------------------------|
| `Username`| `string`         | **Required**. Username of the user        |
| `Password`| `string`         | **Required**. Password of the user        |
 
 ### CreateInstitutionDTO Schema
 | Property             | Type       | Description                                       |
|----------------------|------------|---------------------------------------------------|
| `Latitude`           | `string`   | Latitude coordinate of the institution            |
| `Longitude`          | `string`   | Longitude coordinate of the institution           |
| `InstitutionName`    | `string`   |  **Required**. Name of the institution                           |
| `WebsiteURL`         | `string`   | URL of the institution's website                  |
| `EstablishedYear`    | `DateTime` | Year the institution was established              |
| `Username`           | `string`   | **Required**. Username of the user                |
| `Password`           | `string`   | **Required**. Password of the user                |
| `Notes`              | `string?`  | Additional notes or comments (optional)           |
| `PreferredLanguageID`| `short`    |  **Required**.ID representing the user's preferred language     |
| `CountryID`          | `byte`     |  **Required**.ID of the country where the institution is located |

 ### SendInstitutionDTO Schema
 | Property             | Type       | Description                                       |
|----------------------|------------|---------------------------------------------------|
| `Latitude`           | `string`   | Latitude coordinate of the institution            |
| `Longitude`          | `string`   | Longitude coordinate of the institution           |
| `InstitutionName`    | `string`   |  **Required**. Name of the institution                           |
| `WebsiteURL`         | `string`   | URL of the institution's website                  |
| `InstitutionID`      | `int`      | **Primary Key**. Unique ID of the institution     |
| `EstablishedYear`    | `DateTime` | Year the institution was established              |
| `Username`           | `string`   | **Required**. Username of the user                |
| `Password`           | `string`   | **Required**. Password of the user                |
| `Notes`              | `string?`  | Additional notes or comments (optional)           |
| `PreferredLanguageID`| `short`    |  **Required**.ID representing the user's preferred language     |
| `CountryID`          | `byte`     |  **Required**.ID of the country where the institution is located |

