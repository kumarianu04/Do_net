# JWT Authentication in ASP.NET Core Web API

## Overview

This project demonstrates how to implement **JWT (JSON Web Token) Authentication** in an **ASP.NET Core Web API**. It secures API endpoints by allowing access only to authenticated users through bearer tokens.

## Technologies Used

* ASP.NET Core Web API
* C#
* JWT (JSON Web Token)
* Swagger UI
* Visual Studio Code
* .NET 10

## Project Structure

```
JwtAuthApi
├── Controllers
│   ├── AuthController.cs
│   └── SecureController.cs
├── Models
│   ├── LoginModel.cs
│   └── User.cs
├── Properties
│   └── launchSettings.json
├── appsettings.json
├── Program.cs
└── README.md
```

## Key Features

* Developed a login endpoint for user authentication.
* Generated JWT tokens after successful login.
* Configured JWT Authentication and Authorization.
* Secured API endpoints using the `[Authorize]` attribute.
* Verified API functionality using Swagger UI.

## JWT Configuration

### `appsettings.json`

```json
"Jwt": {
  "Key": "ThisIsMySuperSecretJwtKeyForWeek4Lab12345",
  "Issuer": "MyAuthServer",
  "Audience": "MyApiUsers"
}
```

## API Endpoints

### Login

**POST**

```
/api/Auth/login
```

**Request**

```json
{
  "username": "admin",
  "password": "admin123"
}
```

**Response**

```json
{
  "token": "<JWT_TOKEN>"
}
```

### Protected Endpoint

**GET**

```
/api/Secure/data
```

**Authorized Response**

```
This is protected data.
```

**Unauthorized Response**

```
401 Unauthorized
```

## Steps Performed

1. Created an ASP.NET Core Web API project.
2. Added the required NuGet packages.
3. Configured JWT settings in `appsettings.json`.
4. Enabled Authentication and Authorization in `Program.cs`.
5. Implemented `AuthController` for JWT token generation.
6. Protected API endpoints through `SecureController` using `[Authorize]`.
7. Executed the application with:

   ```
   dotnet run
   ```
8. Tested all endpoints using Swagger UI.

## Results

* JWT token was successfully generated after user login.
* Protected endpoints denied unauthorized access with a **401 Unauthorized** response.
* Only users with a valid JWT token could access secured resources.

## Learning Outcomes

* Gained practical knowledge of JWT-based authentication.
* Learned how JWT tokens are generated and validated.
* Implemented authentication and authorization in an ASP.NET Core Web API.
* Secured REST API endpoints using bearer token authentication.

## Status

**Completed ✅**

**Module:** Deepskilling Week 4 – Microservices Architecture using ASP.NET Core Web API

**Topic:** JWT Authentication in ASP.NET Core Web API
