# Input 

Generate API docs for the following Swagger petstore JSON example:

[Json from <https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/examples/v2.0/json/petstore.json> here]

# Answer

Here is some example API documentation for the Swagger petstore JSON example:

### List all pets

```
GET /v1/pets

```

Retrieves a list of all pets.

#### Parameters

| Name | Type | Description | Required |
| --- | --- | --- | --- |
| limit | integer | How many items to return at one time (max 100) | No |

#### Responses

##### 200

An paged array of pets.

##### default

unexpected error

### Create a pet

```
POST /v1/pets

```

Creates a new pet.

#### Responses

##### 201

Null response

##### default

unexpected error

### Info for a specific pet

```
GET /v1/pets/{petId}

```

Retrieves information for a specific pet.

#### Parameters

| Name | Type | Description | Required |
| --- | --- | --- | --- |
| petId | string | The id of the pet to retrieve | Yes |

#### Responses

##### 200

Expected response to a valid request

##### default

unexpected error

### Definitions

#### Pet

A pet object.

| Name | Type | Description | Required |
| --- | --- | --- | --- |
| id | integer | The pet's id | Yes |
| name | string | The pet's name | Yes |
| tag | string | The pet's tag | No |

#### Pets

An array of Pet objects.

#### Error

An error object.

| Name | Type | Description | Required |
| --- | --- | --- | --- |
| code | integer | The error code | Yes |
| message | string | The error message | Yes |