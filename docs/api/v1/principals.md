<!-- omit in toc -->
# Principals (`ruek.api.v1.Principals`)

```proto
package ruek.api.v1;

service Principals {}
```

- [(rpc) Create (`ruek.api.v1.Principals.Create`)](#rpc-create-ruekapiv1principalscreate)
  - [Request message](#request-message)
  - [Response message](#response-message)
  - [Example](#example)
- [(rpc) Delete (`ruek.api.v1.Principals.Delete`)](#rpc-delete-ruekapiv1principalsdelete)
  - [Request message](#request-message-1)
  - [Response message](#response-message-1)
- [(rpc) List (`ruek.api.v1.Principals.List`)](#rpc-list-ruekapiv1principalslist)
  - [Request message](#request-message-2)
  - [Response message](#response-message-2)
  - [Example](#example-1)
- [(rpc) Retrieve (`ruek.api.v1.Principals.Retrieve`)](#rpc-retrieve-ruekapiv1principalsretrieve)
  - [Request message](#request-message-3)
  - [Response message](#response-message-3)
- [(rpc) Update (`ruek.api.v1.Principals.Update`)](#rpc-update-ruekapiv1principalsupdate)
  - [Request message](#request-message-4)
  - [Response message](#response-message-4)
- [Messages](#messages)
  - [Principal](#principal)
  - [PrincipalsCreateRequest](#principalscreaterequest)
  - [PrincipalsDeleteRequest](#principalsdeleterequest)
  - [PrincipalsDeleteResponse](#principalsdeleteresponse)
  - [PrincipalsListRequest](#principalslistrequest)
  - [PrincipalsListResponse](#principalslistresponse)
  - [PrincipalsRetrieveRequest](#principalsretrieverequest)
  - [PrincipalsUpdateRequest](#principalsupdaterequest)


## (rpc) Create (`ruek.api.v1.Principals.Create`)

Create a new principal.

```proto
rpc Create(PrincipalsCreateRequest) returns (Principal) {
  option (google.api.http) = {
    post : "/v1/principals"
    body : "*"
  };
}
```

### Request message

[`PrincipalsCreateRequest`](#principalscreaterequest)

### Response message

[`Principal`](#principal)

### Example

```
❯ grpcurl \
  -import-path proto \
  -import-path ./.build/_deps/googleapis-src \
  -proto proto/ruek/api/v1/principals.proto \
  -plaintext \
  localhost:8080 ruek.api.v1.Principals/Create

{
  "id": "cn7qtdu56a1cqrj8kur0"
}
```


## (rpc) Delete (`ruek.api.v1.Principals.Delete`)

Delete an existing principal.

```proto
rpc Delete(PrincipalsDeleteRequest) returns (PrincipalsDeleteResponse) {
  option (google.api.http) = {
    delete : "/v1/principals/{id}"
    body : "*"
  };
}
```

### Request message

[`PrincipalsDeleteRequest`](#principalsdeleterequest)

### Response message

[`PrincipalsDeleteResponse`](#principalsdeleteresponse)


## (rpc) List (`ruek.api.v1.Principals.List`)

List principals.

```proto
rpc List(PrincipalsListRequest) returns (PrincipalsListResponse) {
  option (google.api.http) = {
    get : "/v1/principals?segment={segment}&_limit={pagination_limit}&_start={pagination_token}"
  };
}
```

### Request message

[`PrincipalsListRequest`](#principalslistrequest)

### Response message

[`PrincipalsListResponse`](#principalslistresponse)

### Example

```
❯ grpcurl \
  -import-path proto \
  -import-path ./.build/_deps/googleapis-src \
  -proto proto/ruek/api/v1/principals.proto \
  -plaintext \
  localhost:8080 ruek.api.v1.Principals/List

{
  "principals": [
    {
      "id": "cn7qtim56a1cqrj8kurg"
    },
    {
      "id": "cn7qtdu56a1cqrj8kur0"
    }
  ]
}
```


## (rpc) Retrieve (`ruek.api.v1.Principals.Retrieve`)

Retrieve a principal.

```proto
rpc Retrieve(PrincipalsRetrieveRequest) returns (Principal) {
  option (google.api.http) = {
    get : "/v1/principals/{id}"
  };
}
```

### Request message

[`PrincipalsRetrieveRequest`](#principalsretrieverequest)

### Response message

[`Principal`](#principal)


## (rpc) Update (`ruek.api.v1.Principals.Update`)

Update a principal.

```proto
  rpc Update(PrincipalsUpdateRequest) returns (Principal) {
    option (google.api.http) = {
      put : "/v1/principals/{id}"
      body : "*"
    };
  }
```

### Request message

[`PrincipalsUpdateRequest`](#principalsupdaterequest)

### Response message

[`Principal`](#principal)


## Messages

### Principal

| Field   | Type                | Description |
| ------- | ------------------- | ----------- |
| id      | `string`            | |
| attrs   | (optional) [`google.protobuf.Struct`](https://protobuf.dev/reference/protobuf/google.protobuf/#struct) | |
| segment | (optional) `string` | |

### PrincipalsCreateRequest

| Field   | Type                | Description |
| ------- | ------------------- | ----------- |
| id      | (optional) `string` | |
| attrs   | (optional) [`google.protobuf.Struct`](https://protobuf.dev/reference/protobuf/google.protobuf/#struct) | |
| segment | (optional) `string` | |

### PrincipalsDeleteRequest

| Field   | Type      | Description |
| ------- | --------- | ----------- |
| id      | `string`  | |

### PrincipalsDeleteResponse

| Field   | Type                | Description |
| ------- | ------------------- | ----------- |

### PrincipalsListRequest

| Field            | Type                | Description |
| ---------------- | ------------------- | ----------- |
| segment          | (optional) `string` | |
| pagination_limit | (optional) `uint32` | |
| pagination_token | (optional) `string` | |

### PrincipalsListResponse

| Field            | Type                        | Description |
| ---------------- | --------------------------- | ----------- |
| principals       | [`[]Principal`](#principal) | |
| pagination_token | (optional) `string`         | |

### PrincipalsRetrieveRequest

| Field   | Type      | Description |
| ------- | --------- | ----------- |
| id      | `string`  | |

### PrincipalsUpdateRequest

| Field   | Type                | Description |
| ------- | ------------------- | ----------- |
| id      | `string`            | |
| attrs   | (optional) [`google.protobuf.Struct`](https://protobuf.dev/reference/protobuf/google.protobuf/#struct) | |
| segment | (optional) `string` | |