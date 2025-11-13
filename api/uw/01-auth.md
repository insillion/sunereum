### API Endpoint: Auth API

This `auth` endpoint allows users to authenticate and obtain access to our Insurance policy issuance system.

By default, the auth token remains valid for 30 minutes (idle period). To extend this duration for each user, kindly reach out to the admin.

We recommend making the auth request prior to each transaction.

#### Request Format

- **Method**: POST
    
- **URL**: `{{host}}/api/v1/auth`
    
- **Content-Type**: application/json
    

#### Request Body

The request body must be in JSON format and should include the following fields:

- `email` (string, required): The email address of the user.
    
- `mpwd` (string, required): The password of the user.
    
The token from this request's response is used for subsequent API calls.

**Example Request Body**:

``` json
{
    "email": "xxxx",
    "mpwd": "yyyy"
}

 ```

#### Response Format

On a successful request, the API will return a JSON response with the following structure:

| Key | Description |
| --- | --- |
| status | The status of the response. 0 indicates success. |
| txt | Error message, if any. |
| token | System generated token to access other APIs. |
| email | The email of the logged-in user. |
        

**Example Response**:

``` json
{
    "status": 0,
    "txt": "",
    "data": {
        "email": "uw@sunerum.cloware.in",
        "first_name": "Underwriter",
        "last_name": "",
        "salt_public": "25506252",
        "pepper": 0,
        "priv_level": 0,
        "fail_count": 0,
        "pass_change_dt": null,
        "author": "not-registered",
        "ip": "::ffff:127.0.0.1",
        "c_ts": "2025-10-30 06:15:49",
        "u_ts": "2025-11-06 12:35:07.248229",
        "token": "MvoCNqfuKGvNJqEr6sKvmmCMxylXmrdY9St4U2p0Bwu/e6VmEx8bJdFvvYdaLEBO9gk7sNNnQljNmM1LfTK84jsiOWaCyy7SJV5K9Xi+WqZmtQ=="
    }
}

 ```
