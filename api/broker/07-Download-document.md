### API Endpoint: Download Document
This endpoint allows users to download a specific document (e.g., a PDF file) by providing its identifiers and an authentication token. It serves the raw binary content of the requested file.

#### Request Format
- **Method**: GET
    
- **URL**: `{{base_url}}/api/v1/document/data/{document_id}/{document_name}/{file_name.extention}?download=1&token={{doc_token}}`
    
- **Content-Type**: Not applicable for request body; the response `Content-Type` will be `application/pdf` (or corresponding file type).
    
    
#### Path Parameters
- `document_id` (string) (Required): The unique identifier of the document.
- `document_name` (string) (Required): The name of the document, which must be URL-encoded.
- `file_name.pdf` (string) (Required): The specific name of the file to be downloaded, including its extension (e.g., `hello_world.pdf`).

#### Query Parameters
- `download` (integer) (Optional): Set to `1` to explicitly indicate that the file should be downloaded (triggering a download prompt in browsers). If omitted or set to `0`, browsers might attempt to display the file inline.
- `token` (string) (Required): An authentication token that authorizes the download of the document. This token ensures that only authorized users can access the document.

#### Important Note: URL Encoding for Path Parameters
Path parameters like `{document_name}` must be URL-encoded, especially if they contain spaces or special characters. For example, "Existing all-risk insurance policy" becomes "Existing%20all-risk%20insurance%20policy" in the URL.

## Identifying Documents for Deletion

**Important:** Each document upload creates an object within the `document.data.details` path in the associated policy's JSON response. To successfully download a document, you must first retrieve the `document_id`, `document_type`, `name`from this object.

You can identify the specific document you wish to download within the `document.data.details` array by inspecting parameters like:
*   `name`: The filename of the document.
*   `document_type`: The category of the document.
*   `document_id`: Doc id.


**Example Policy JSON Snippet (showing where to find document details):**

```json
{
  "policy_id": "P000000000182",
  "document": {
    "data": {
      "details": [
        {
          "document_details_id": "DX000000000125",
          "name": "0516000010.pdf",
          "document_type": "Active O&M contract",
          "document_desc": "O&M Contract for solar panels 2024",
          "uploaded_on": "2024-07-20T10:30:00Z",
          "document_id": "DT000000000160",
        },
        {
          "document_details_id": "DX000000000126",
          "name": "InsurancePolicy_2024.pdf",
          "document_type": "Policy Document",
          "document_desc": "Main policy document for current year",
          "uploaded_on": "2024-07-19T09:00:00Z",
          "document_id": "DT000000000160",
        }
      ]
    }
  },
  "other_policy_data": {}
}

```

#### Response 

When this API is called:

In a Web Browser: The document (e.g., PDF) will typically open directly in a new browser tab/window or trigger a download prompt, depending on browser settings and the download query parameter.


In an API Client (e.g., Postman): The raw binary content of the document will be visible in the response body. You can then use the client's features (e.g., Postman's "Save Response" option) to save this content as a file (e.g., hello_world.pdf) to your local machine.