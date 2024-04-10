Absolutely, I've incorporated the changes you requested:

**# Advanced Cypress Study**


## Author

I am Aytekin.

## What’s in this repo

This repo contains all the materials for the course. Most of the chapters start with `[chapter_name]_start.js` and finish with `[chapter_name]_end.js` file.

### Installation

Super simple

1. `npm install`
2. `npm start`
3. Open your browser on `http://localhost:3000`

### Application utilities

By typing `F2` key in the application, a small toolset appears that will allow you to reset your application to a desired state. You can delete boards, lists, cards, users, or everything. This is useful when playing with the application manually.

# API documentation

**`GET`** `/api/boards`

Returns all boards

**Example (unauthorized user):**

```json
[
  {
    "name": "new project",
    "user": 0,
    "id": 27315982008,
    "starred": false,
    "created": "2020-09-01"
  },
  {
    "name": "moon landing 2",
    "user": 0,
    "id": 14254049205,
    "starred": true,
    "created": "2020-09-01"
  }
]
```

**Example (authorized user):**

```json
[
  {
    "name": "new project",
    "user": 0,
    "id": 27315982008,
    "starred": false,
    "created": "2020-09-01"
  },
  {
    "name": "moon landing 2",
    "user": 0,
    "id": 14254049205,
    "starred": true,
    "created": "2020-09-01"
  },
  {
    "name": "private board",
    "user": 1, // User ID of the board author
    "id": 6606529940,
    "starred": false,
    "created": "2020-09-01"
  }
]
```

---

**`POST`** `/api/boards`

Creates a new board

**Example request:**

```json
{
  "name": "moon landing 2"
}
```

**Example response:**

```json
{
  "name": "moon landing 2",
  "user": 1,
  "id": 22559285486,
  "starred": false,
  "created": "2020-09-01"
}
```

---

**`GET`** `/api/boards/{boardId}`

Returns details of a board with a given `boardId`

**Example response:**

```json
{
  "name": "new project",
  "user": 0,
  "id": 27315982008,
  "starred": false,
  "created": "2020-09-01"
}
```

---

**`PATCH`** `/api/boards/{boardId}`

Changes details of a board with a given `boardId`. `starred` and `name` attributes can be changed.

**Example request:**

```json
{
  "starred": true,
  "name": "project alpha"
}
```

---

**`DELETE`** `/api/boards/{boardId}`

Deletes a board with a given `boardId`.

---

**`GET`** `/api/lists`

Returns all lists.

**Example response**

```json
[
  {
    "boardId": 123456789,
    "name": "Groceries",
