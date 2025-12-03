## API Endpoint: Generate payment link

This API endpoint allows you to generate a Stripe payment link for a given policy.

### Request Method

- **Method**: POST
    
- **URL**: `{{base_url}}/api/v1/stripe_payment/gen_payment`
    
- **Content-Type**: application/json

### Request Body

The request body should be sent in JSON format and must include the following parameters:

Get policy id from proposal finalize api responce.

The request body must be a JSON object containing the `policy_id`.

| Parameter   | Type   | Description                                           | Required | Example           |
| :---------- | :----- | :---------------------------------------------------- | :------- | :---------------- |
| `policy_id` | String | The unique identifier for the policy to generate a payment link for. | Yes      | `"P000000000213"` |



**Example Request Body**:
```json
{
   "policy_id":"P000000000213"
}
```
### Expected Response

If the payment link is successfully generated, the API will return a JSON object with a `status` of `0` and the `stripe_payment_url` within the `data` object.

```json
{
    "status": 0,
    "txt": "",
    "data": {
        "stripe_payment_url": "https://sunereum.sb.insillion.com/pub/payment/8tw24H%2FGsu701NH7KejY%2BUp8%2BkMAE4q2bjkAJXpo7jG94xI5thfvke%2FKn1OJFLIeHwWBFecXW9Yu6G9z?auto=1"
    }"
    }
}
```
This API is used to create a one-time use payment URL for a given policy. When a user needs to make a payment for a particular policy, the backend system can call this endpoint with the relevant policy_id. The API will then return a URL that the user can be redirected to, enabling them to complete the payment securely through the designated payment processor (Stripe in this case).
