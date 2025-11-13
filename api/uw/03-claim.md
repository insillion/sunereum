### API Endpoint: To takeover the case

This endpoint allows change in the ownership or responsibility for a specific quote from the UW bucket.

#### Request Format

- **Method**: POST
    
- **URL**: `{{base_url}}/api/v1/quote/claim`
    
- **Content-Type**: application/json
    

#### Request Body

The request body must be in JSON format and should include the following fields:

Get quote id from last quote api response.

- `quote_id` (string)(System Generated): The identifier for the quote.

**Example Request Body**:

` json
{
     "quote_id": "Q000000000131",
}

 `

#### Sample Response Format

On a successful request, the API will return a JSON response with the following structure:

- `status` (integer): The status of the request (0 indicates success).
    
- `txt` (string): A message related to the status.
    
- `data` (string): It will return empty.
    

        

**Example Response**:

` json
{
    "status": 0,
    "txt": "",
    "data": ""
}
`

### Notes

Ensure that all required parameters are included in the request body to avoid errors.

