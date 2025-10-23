## About the File
This file contains information about using Acode API endpoints, 
such as request method, URL, example responses, status code, etc.

# Login

## `GET` • `/api/login`
> Retrieve Information about Currently Logged-In User.

- headers
  - `cookie: token=<some value>`

**Checks for same-origin or same-domain**

Response (200): 
```json
{
  "id": 1,
  "name": "Example",
  "role": "user",
  "email": "user@example.com",
  "github": "github",
  "website": "",
  "verified": 0,
  "threshold": 1000,
  "created_at": "2023-11-25 15:36:47",
  "updated_at": "2023-11-25 15:36:47"
}
```

## `POST` • `/api/login`
> Used to send user email & password as `FormData`.
> Returns **400 (bad request) if it's incorrect.** 

**Checks for same-origin or same-domain**

Response (200):
```json
{
  "message": "Logged in",
  "token": "<Access Token>"
}
```

## `DELETE` • `/api/login`
> For Deleting(invalidate) access tokens 
> Returns **400 (bad request) if not logged in (checks for request's cookies).**

**Checks for same-origin or same-domain**

Response (200):
```json
{
  "message": "Logged out"
}
```