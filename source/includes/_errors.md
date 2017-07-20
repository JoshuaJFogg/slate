# Errors

> In the event an error occurs, an object will be returned:

```json
{
  "result" : {
      "status" : "FAILED",
      "reason" : "Example String"
  }
}
```

<aside class="notice">This error section is a summary of the possible error codes you could recieve from the eSuite API. The API will return a specific error message alongside one of these codes to detail the specific error that has occurred.</aside>


Error Code | Meaning
---------- | -------
400 | `Bad Request` -- Your request is malformed in some way
401 | `Unauthorized` -- The API key provided is not valid
403 | `Forbidden` -- The resource is not accessible using the provided API key
404 | `Not Found` -- The specified resource could not be found
405 | `Method Not Allowed` -- You tried to access a resource with an invalid method
406 | `Not Acceptable` -- You requested a format that isn't json
412 | `Pre-Condition Failed` -- The request has failed basic validation
500 | `Internal Server Error` -- We had a problem with our server. Try again later.
503 | `Service Unavailable` -- We're temporarily offline for maintenance. Please try again later.
