# Example-Swagger-yaml

```
swagger: "2.0"
info:
  description: "This is a sample specification for user service"
  version: "1.0.0"
  title: "User Service contract"
tags:
  - name: "user"
paths:
  /user:
    get:
      tags:
        - "user"
      summary: "Gets a list of users"
      description: ""
      operationId: "getUsers"
      consumes:
      - "*/*"
      produces:
      - "application/json"
      responses:
        200:
          schema:
            $ref: "#/definitions/ListUserResponse"
          description: "List of all users"
    post:
      tags:
        - "user"
      summary: "Creates a new user"
      operationId: "createUser"
      consumes:
      - "application/json"
      produces:
      - "application/json"
      parameters:
      - in: "body"
        name: "user"
        description: "The user data"
        required: true
        schema:
          $ref: "#/definitions/UserCreateRequest"
      responses:
        201:
          description: "User successfully created"
        400:
          description: "Validation error"
definitions:
  ListUserResponse:
    type: "array"
    items:
      $ref: "#/definitions/UserResponse"
  UserResponse:
    type: "object"
    properties:
      id:
        type: "integer"
      name:
        type: "string"
  UserCreateRequest:
    type: "object"
    properties:
      name:
        type: "string"
```
