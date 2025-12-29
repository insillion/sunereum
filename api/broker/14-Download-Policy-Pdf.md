### API Endpoint: Download Policy PDF
This endpoint allows users to download a specific policy document (e.g., a PDF file) by providing its identifiers and an authentication token. It serves the raw binary content of the requested policy file.
#### Request Format
- **Method**: GET
    
- **URL**: `{{base_url}}/api/v1/policy/data/{policy_id}?data_id={{data_id}}&download=1&token={{doc_token}}`
    
- **Content-Type**: Not applicable for request body; the response `Content-Type` will be `application/pdf`.
    
    
#### Path Parameters
- `policy_id` (string) (Required): The unique identifier of the policy for which the PDF is to be downloaded (e.g., `P000000000496`).
#### Query Parameters
- `data_id` (integer) (Required): The identifier for the specific data item or version of the policy document to be downloaded. This is crucial for retrieving the correct policy PDF.
- `download` (integer) (Optional): Set to `1` to explicitly indicate that the file should be downloaded (triggering a download prompt in browsers). 
- `token` (string) (Required): An authentication token that authorizes the download of the policy document. This token ensures that only authorized users can access the document.

## Identifying Policy Documents for Download
To successfully download a policy PDF, you must first retrieve the `policy_id` and `data_id` associated with the desired policy. These identifiers are typically retrieved from a "Get Policy Details" or "List Policies" API response.

#### Important Note: 
Get data_id after payment done from below json path using "Get Quote Details" API response.

`data_id` : policy.data.policy1