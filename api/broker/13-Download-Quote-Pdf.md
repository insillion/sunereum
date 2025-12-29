### API Endpoint: Download Quote PDF
This endpoint allows users to download a specific quote document (e.g., a PDF file) by providing its identifiers and an authentication token. It serves the raw binary content of the requested quote file.
#### Request Format
- **Method**: GET
    
- **URL**: `{{base_url}}/api/v1/quote/data/{quote_id}?data_id={{data_id}}&download=1&token={{doc_token}}`
    
- **Content-Type**: Not applicable for request body; the response `Content-Type` will be `application/pdf`.
    
    
#### Path Parameters
- `quote_id` (string) (Required): The unique identifier of the quote for which the PDF is to be downloaded (e.g., `Q000000000490`).
#### Query Parameters
- `data_id` (integer) (Required): The identifier for the specific data item or version of the quote document to be downloaded. This is crucial for retrieving the correct quote PDF.
- `download` (integer) (Optional): Set to `1` to explicitly indicate that the file should be downloaded (triggering a download prompt in browsers). 
- `token` (string) (Required): An authentication token that authorizes the download of the quote document. This token ensures that only authorized users can access the document.

## Identifying Quote Documents for Download
To successfully download a quote PDF, you must first retrieve the `quote_id` and `data_id` associated with the desired quote. These identifiers are typically retrieved from a "Get Quote Details" API response.

#### Important Note: 
Get data_id after approval UW from below json path using "Get Quote Details" API response.

`data_id` : quote.data.quote12