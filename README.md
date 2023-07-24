# random-data-api
This API uses randomly generated JSON data courtesy of [JSON Generator](https://json-generator.com/#). This project utilizes:
- MongoDB (database)
- Mongoose (data modeling)
- Express (server)
- Heroku (deployment)

## GET Requests & Endpoints
#### Base URL
```
https://random-data-api-50875b874049.herokuapp.com/api
```
Without parameters, this will return all of the documents in the API.

Querying
---
### By ID:
#### Request URL
```
https://random-data-api-50875b874049.herokuapp.com/api/DOCUMENT_ID
```
#### Example
```
https://random-data-api-50875b874049.herokuapp.com/api/64bc528f474689bddfb72e67
```
This will return the document where the value of _id is "64bc528f474689bddfb72e67".

---
### With a single query parameter:
#### Request URL
```
https://random-data-api-50875b874049.herokuapp.com/api?KEY=VALUE
```
#### Example
```
https://random-data-api-50875b874049.herokuapp.com/api?eyeColor=blue
```
This will return all documents in the API where the value of eyeColor is "blue".

---
### With multiple query parameters:
#### Request URL
```
https://random-data-api-50875b874049.herokuapp.com/api?KEY=VALUE&KEY=VALUE
```
#### Example
```
https://random-data-api-50875b874049.herokuapp.com/api?eyeColor=blue&name=Barber%20Bray
```
This will return all documents where the value of eyeColor is "blue" **AND** the value of name is "Barber Bray".

## POST Requests
A POST request to the base URL will add a new document to the API. A body containing raw JSON data must be submitted with the request with the following format:
```json
{
  "_id": String,
  "index": Number,
  "guid": String,
  "isActive": Boolean,
  "balance": String,
  "picture": String,
  "age": Number,
  "eyeColor": String,
  "name": String,
  "gender": String,
  "company": String,
  "email": String,
  "phone": String,
  "address": String,
  "about": String,
  "registered": String,
  "latitude": Number,
  "longitude": Number,
  "tags": [String],
  "friends": [{
    "id": Number,
    "name": String
  }],
  "greeting": String,
  "favoriteFruit": String
}
```

## PUT Requests
To update one or more documents in the API, a PUT request can be made to:
- The base URL (using query paramters to specify which document(s) to update)
- The /DOCUMENT_ID endpoint to specifiy a single document to update by its ID.
</br>

A PUT request must be submitted with a body containing raw JSON data in the [appropriate format](https://github.com/nnmcgovern/unit-project-2/edit/main/README.md#post-requests).

## DELETE Requests
To delete one or more documents in the API, a DELETE request can be made to either the base URL (using query parameters) or to the /DOCUMENT_ID endpoint.
