Entries
=======

Get Entries
-----------

 - `GET /v1/entries.json` will return all entries in a user's queue.

```json
[{}]
```

| Parameter | Required | Example                                                             |
|-----------|----------|---------------------------------------------------------------------|
| `test`    | true     | `GET some example` will something something                         |

**Status Codes**

 - `200 OK` will be returned if found.
 - `403 Forbidden` will be returned if the user does not have permission.

Get Entry
---------

 - `GET /v1/entry/81.json` will return the entry with the id of `81`.

```json
[{}]
```

**Status Codes**

 - `200 OK` will be returned if found.
 - `403 Forbidden` will be returned if the user does not own this entry.

Create Entry
------------

 - `POST /v1/entries.json` will add an entry to the user's queue, with the contents based on the parameters specified.

```json
[{}]
```

| Parameter | Required | Example                                                             |
|-----------|----------|---------------------------------------------------------------------|
| `test`    | true     | `POST some example` will something something                        |

**Status Codes**

- `201 Created`
- `302 Found` will be returned if the audio URL is already part of the user's queue.
- `404 Not Found` will be returned if the audio URL provided does not exist.

Delete Entry
------------

It is not possible to delete an entry from the queue. You can however archive an entry (see Update Entry).

Update Entry
------------

Updating an entry can be used to archive an entry, as well as update the title, user notes etc. associated with it.

`PATCH /v1/entries/81.json` will update the entry with an ID of `81`.

**Request**

```json
{
    "archive": "true"
}
```
| Parameter | Required | Example                                                             |
|-----------|----------|---------------------------------------------------------------------|
| `test`    | true     | `POST some example` will something something                        |

**Response**

```json
```

**Status Codes**

 - `200 OK` will be returned if the request was successful.
 - `403 Forbidden` will be returned if the user does not own this entry.
