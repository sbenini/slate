# Return Codes & Errors

YonderAPI returns codes that follow the HTTP standard.

## Successfull requests

When everything goes fine, YonderAPI returns HTTP codes of the type `2xx`:

Error Code | Meaning
---------- | -------
200 | OK
201 | CREATED
202 | ACCEPTED
204 | NO CONTENT

## Client-side errors

When something goes wrong on the request side, YonderAPI returns HTTP error codes of type `4xx`:

Error Code | Meaning
---------- | -------
400 | BAD REQUEST (e.g. a required parameter is missing)
401 | UNAUTHORIZED (e.g. wrong credentials)
404 | NOT FOUND (e.g. misspelled resource)
405 | METHOD NOT ALLOWED (e.g. `GET` is requested but only `POST` is available)

Error messages are self-explanatory and clearly point where the problem is. 
An example of `BAD REQUEST` response due to a missing parameter is provided aside:

```
{
    "message": {
        "text": "Missing required parameter in the JSON body or the post body or the query string"
    }
}
```

## Server-side errors

When something goes wrong on the API side, YonderAPI returns HTTP error code `500 INTERNAL SERVER ERROR` with a message body such as the one provided aside:

```
{
    "message": {
        "error": "API processing error - Code 001."
    }
}
```

