# Coteacher API documentation

This document contains information on all client-side API calls, including the name of the method, HTTP request, endpoint, and sample reques/response object data.

## Table of Contents

* [Collection API](#collection-api)
    + [getCollection](#getcollection)
    * [getCollections](#getcollections)
    * [createCollection](#createcollection)
    * [updateCollection](#updatecollection)
    * [deleteCollection](#deletecollection)
* [Category API](#category-api)
    * [createCategory](#createcategory)
    * [updateCategory](#updatecategory)
    * [deleteCategory](#deletecategory)
* [Resource API](#resource-api)
    * [getResource](#getresource)
    * [getResources](#getresources)
    * [updateResource](#updateresource)
    * [deleteResource](#deleteresource)
    * [getResourceThumbnail](#getresourcethumbnail)

## Collection API

### getCollection

```
HTTP Request: GET
Endpoint: /collection/${id}
```

**Response:**
```json
{
    "collection": {
        "categories": [] //see categories API,
        "contributors": [
            {
                "adminPermission": true,
                "collectionId": 1,
                "id": 1,
                "profile": {},
                "profileId": 1,
                "writePermission": true
            }
        ],
        "createdAt": "2021-07-13T12:26:27.765064Z",
        "description": "string",
        "grade": {
            "category": null,
            "categoryId": null,
            "createdAt": "0001-01-01T00:00:00Z",
            "id": 5,
            "name": "5",
            "updatedAt": "0001-01-01T00:00:00Z"
        },
        "gradeId": 5,
        "id": 1,
        "invites": [],
        "name": "collection name",
        "postDate": "",
        "private": false,
        "profile": {} //see profile API,
        "profileId": 1,
        "slug": "",
        "standards": [] //see standards API,
        "tags": [
            {
                "createdAt": "2021-07-16T16:21:44.954378Z",
                "id": 2,
                "name": "science",
                "updatedAt": "2021-07-16T16:21:44.954378Z"
            }
        ],
        "topics": [
            {
                "CreatedAt": "0001-01-01T00:00:00Z",
                "id": 10,
                "name": "Math",
                "subject": {
                    "createdAt": "0001-01-01T00:00:00Z",
                    "id": 0,
                    "name": "",
                    "updatedAt": "0001-01-01T00:00:00Z"
                },
                "subjectId": 4,
                "updatedAt": "0001-01-01T00:00:00Z"
            }
        ]
    }
}
```

## getCollections

```
HTTP Request: GET
Endpoint: /collection?name=${name}&profile_id=${profile}
```

**Response:**

```json
{
    "collections": [] //array of collections
}
```

## createCollection

```
HTTP Request: POST
Endpoint: /collection/create
```

**Request:**
```json
{
    "description": "something",
    "grade": {
        "id": 1
    },
    "name": "a collection",
    "private": false,
    "standards": [] //see standards API, 
    "tags": [
        {
            "name": "tag"
        }
    ],
    "topics": [
        {
            "id": 10
        }
    ]
}
```
**Response:**
```json
{
    "collection": {} //see getCollection
}
```
## updateCollection
```
HTTP Request: POST
Endpoint: /collection/update
```
**Request:**
```json
{
    "categories": [] //see categories API,
    "contributors": [
        {
            "adminPermission": true,
            "collectionId": 1,
            "id": 1,
            "profile": {},
            "profileId": 1,
            "writePermission": true
        }
    ],
    "createdAt": "2021-07-16T16:40:29.332009Z",
    "description": "YOU ARE EDITED!!!",
    "grade": {"id": 5},
    "gradeId": 5,
    "id": 7,
    "invites": [],
    "name": "edited name",
    "postDate": "",
    "private": false,
    "profile": {} //see profile API,
    "profileID": 2,
    "slug": "",
    "standards": [] //see standards API,
    "tags": [
        {"name": "tag"}
    ],
    "topics": [
        {"id": 10 }
    ],
    "updatedAt": "2021-07-16T16:40:29.332009Z"
}
```

**Response:**

```json
{
    "collection": {} //see getCollection
}
```

## deleteCollection

```
HTTP Request: POST
Endpoint: /collection/delete
```

**Request:**

```json
{
    "collection": {} //see getCollection
}
```

# Category API
## createCategory

```
HTTP request: POST
Endpoint: /collection/category/create
```

**Request:**
```json
{
    "collectionId": 1,
    "id": 2
}
```
**Response:**
```json
{
    "collection": {} //see collection API
}
```

## updateCategory
```
HTTP request: POST
Endpoint: /collection/category/update
```

**Request:**
```json
{
    "collectionId": 1,
    "id": 2,
    "name": "my category"
}
```
**Response:**
```json
{
    "category": {
        "collectionId": 1,
        "id": 2,
        "name": "my category"
    }
}
```

## deleteCategory

```
HTTP request: POST
Endpoint: /collection/category/delete
```

**Request:**
```json
{
    "collectionId": 1,
    "id": 2
}
```

**Response:**
```json
{
    "collection": {} //see collection API
}
```

# Resource API

## getResource
```
HTTP request: GET
Endpoint: /resource/${id}
```
**Response:**
```json
{
    "resource": {
        "categoryId": 1,
        "collection": {} //see collection API,
        "collectionId": 1,
        "createdAt": "2021-07-17T16:24:02.353452Z",
        "description": "my resource",
        "fileId": "1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM",
        "grade": {},
        "gradeId": 5,
        "id": 2,
        "icon": "https://drive-thirdparty.googleusercontent.com/16/type/application/pdf",
        "link": "https://drive.google.com/file/d/1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM/view?usp=drive_web",
        "name": "file.pdf",
        "positionNo": 0,
        "profileId": 1,
        "resourceType": {
            "createdAt": "0001-01-01T00:00:00Z",
            "id": 1,
            "name": "Google",
            "updatedAt": "0001-01-01T00:00:00Z"
        },
        "slug": "",
        "standards": [] //see standards API,
        "tags": [],
        "thumbnail": "",
        "topics": [],
        "updatedAt": "2021-07-17T16:54:42.271857Z"
    }
}
```

## getResources
```
HTTP request: GET
Endpoint: /resource?name=${name}&collection_id=${collectionId}
```
**Response:**
```json
{
    "resources": [] //see getResource
}
```



## updateResource
```
HTTP request: POST
Endpoint: /resource/update
```
**Request:**
```json
{
    "categoryId": 1,
    "collection": {} //see collection API,
    "collectionId": 1,
    "createdAt": "2021-07-17T16:24:02.353452Z",
    "description": "my resource",
    "fileId": "1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM",
    "grade": {},
    "gradeId": 5,
    "id": 2,
    "icon": "https://drive-thirdparty.googleusercontent.com/16/type/application/pdf",
    "link": "https://drive.google.com/file/d/1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM/view?usp=drive_web",
    "name": "file.pdf",
    "positionNo": 0,
    "profileId": 1,
    "resourceType": {
        "createdAt": "0001-01-01T00:00:00Z",
        "id": 1,
        "name": "Google",
        "updatedAt": "0001-01-01T00:00:00Z"
    },
    "slug": "",
    "standards": [] //see standards API,
    "tags": [],
    "thumbnail": "",
    "topics": [],
    "updatedAt": "2021-07-17T17:06:18.064146Z"
}
```

**Response:**
```json
{
    "resource": {
        "categoryId": 1,
        "collection": {} //see collection API,
        "collectionId": 1,
        "createdAt": "2021-07-17T16:24:02.353452Z",
        "description": "my resource",
        "fileId": "1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM",
        "grade": {},
        "gradeId": 5,
        "id": 2,
        "icon": "https://drive-thirdparty.googleusercontent.com/16/type/application/pdf",
        "link": "https://drive.google.com/file/d/1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM/view?usp=drive_web",
        "name": "file.pdf",
        "positionNo": 0,
        "profileId": 1,
        "resourceType": {
            "createdAt": "0001-01-01T00:00:00Z",
            "id": 1,
            "name": "Google",
            "updatedAt": "0001-01-01T00:00:00Z"
        },
        "slug": "",
        "standards": [] //see standards API,
        "tags": [],
        "thumbnail": "",
        "topics": [],
        "updatedAt": "2021-07-17T17:06:18.064146Z"
    }
}
```
## deleteResource
```
HTTP request: POST
Endpoint: /resource/delete
```

**Request:**
```json
{
    "categoryId": 1,
    "collection": {} //see collection API,
    "collectionId": 1,
    "createdAt": "2021-07-17T16:24:02.353452Z",
    "description": "my resource",
    "fileId": "1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM",
    "grade": {},
    "gradeId": 5,
    "id": 2,
    "icon": "https://drive-thirdparty.googleusercontent.com/16/type/application/pdf",
    "link": "https://drive.google.com/file/d/1Olmbnbz_c8uHIQXDt4DsBgV82gH-U0DM/view?usp=drive_web",
    "name": "file.pdf",
    "positionNo": 0,
    "profileId": 1,
    "resourceType": {
        "createdAt": "0001-01-01T00:00:00Z",
        "id": 1,
        "name": "Google",
        "updatedAt": "0001-01-01T00:00:00Z"
    },
    "slug": "",
    "standards": [] //see standards API,
    "tags": [],
    "thumbnail": "",
    "topics": [],
    "updatedAt": "2021-07-17T17:06:18.064146Z"
}
```

## getResourceThumbnail
```
HTTP request: GET
Endpoint: /thumbnail/resource?url=${url}"
```
**Response:**
```json
{
    "thumbnailUrl": "http://www.nasa.gov/sites/default/files/images/nasaLogo-570x450.png"
}
```