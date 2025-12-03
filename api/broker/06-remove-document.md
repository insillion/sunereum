### API Endpoint: To remove document detail

This document outlines the API endpoint for deleting a specific document from the system using its unique identifier.

#### Request Format

- **Method**: DELETE
    
- **URL**: `{{base_url}}/api/v1/document?document_details_id=DX000000000125`
    

#### Request Body

## Description

This API allows you to delete an existing document from the system. To remove any document, you need to pass its unique identifier, `document_details_id`, as a query parameter in the API request.

---

## Identifying Documents for Deletion

**Important:** Each document upload creates an object within the `document.data.details` path in the associated policy's JSON response. To successfully delete a document, you must first retrieve the `document_details_id` from this object.

You can identify the specific document you wish to delete within the `document.data.details` array by inspecting parameters like:
*   `name`: The filename of the document.
*   `document_type`: The category of the document.
*   `document_desc`: A brief description of the document (if provided).

Once you locate the desired document object, you can extract its `document_details_id` from that same object.

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
          "uploaded_on": "2024-07-20T10:30:00Z"
        },
        {
          "document_details_id": "DX000000000126",
          "name": "InsurancePolicy_2024.pdf",
          "document_type": "Policy Document",
          "document_desc": "Main policy document for current year",
          "uploaded_on": "2024-07-19T09:00:00Z"
        }
      ]
    }
  },
  "other_policy_data": {}
}

```

| Parameter           | Type   | Required | Description                                  | Example            |
| :------------------ | :----- | :------- | :------------------------------------------- | :----------------- |
| `document_details_id` | String | Yes      | The unique identifier of the document to delete. | `DX000000000125`   |



**Example  Request Body**:

``` json
document_details_id:DX000000000125

 ```

#### SampleResponse Format

On a successful request, the API will return a JSON response with the following structure:

- `status` (integer): The status of the request (0 indicates success).
    
- `txt` (string): A message related to the status.
    
- `data` (array): An array containing details about the created quote and associated entities, including:
    
    - `policy_id`: Identifier for the policy.
        
    - `product_id`: Identifier for the product.
        
    - `quote_id`: Identifier for the quote.
        
    - `premium_value`: The calculated premium value.
        
    - `quote`: An object containing detailed information about the quote, including customer information, coverage details, and more.
        

**Example Response**:

``` json
{
    "status": 0,
    "txt": "",
    "data": [
        {
            "policy_id": "P000000000304",
            "product_id": "M000000000005",
            "wf_id": 8,
            "product_group_id": "PG000000000001",
            "par_product_id": "M000000000001",
            "quote_id": "Q000000000304",
            "proposal_id": "",
            "discount_id": "",
            "document_id": "DT000000000126",
            "nstp_id": "",
            "payment_id": "",
            "covernote_id": "",
            "inspect_id": "",
            "cart_id": "",
            "uuid": "1968547b-dd43-44d1-b7d9-8ab3cf75ff79",
            "customer_id": "",
            "policy_no": null,
            "quote_no": "",
            "proposal_no": "",
            "tp_policy_no": "",
            "parent_policy_no": "",
            "renewal_count": 0,
            "issue_date": null,
            "cert_id": "",
            "pdf_date": null,
            "nstp_enabled": "",
            "qnstp_enabled": "Yes",
            "pnstp_enabled": "",
            "nstp_case": "",
            "qnstp_case": "No",
            "pnstp_case": "",
            "policy_start_date": "",
            "policy_end_date": "",
            "policy_start_date_dt": null,
            "policy_end_date_dt": null,
            "policy_start_date_dt_ext": null,
            "policy_end_date_dt_ext": null,
            "master_policy_no": "",
            "combo_policy_id": "",
            "ckyc_on": null,
            "ckyc_by": "",
            "archive_url": "",
            "cust_fld_1": "",
            "cust_fld_2": "",
            "cust_fld_3": "",
            "cust_fld_4": "",
            "cust_fld_5": "",
            "cust_fld_6": "",
            "cust_fld_7": "",
            "cust_fld_8": "",
            "cust_fld_9": "",
            "cust_fld_10": "",
            "broker_code": "123",
            "agent_code": "null",
            "status": 0,
            "created_by": "agent@insillion.com",
            "created_by_proxy": "",
            "assigned_to": "agent@insillion.com",
            "proxy": "",
            "author": "agent@insillion.com",
            "ip": "proxy_add_x_forwarded_for",
            "c_ts": "2025-11-27 04:31:38",
            "u_ts": "2025-11-27 04:31:38.551689",
            "assigned_by": "agent@insillion.com",
            "assigned_at": "2025-11-27 04:31:38",
            "data": {},
            "quote": {
                "quote_id": "Q000000000304",
                "wf_id": 8,
                "uuid": "2575c11a-0b09-4917-93b2-33267ade411e",
                "quote_no": null,
                "par_quote_id": "",
                "parent_policy_no": "",
                "customer_id": "",
                "product_id": "M000000000005",
                "product_group_id": "PG000000000001",
                "first_name": "",
                "last_name": "",
                "email": "",
                "mobile_no": "",
                "id_1": "",
                "id_1_type": "",
                "id_2": "",
                "id_2_type": "",
                "quote_date": "2025-11-27 04:31:38",
                "valid_till": null,
                "cert_id": "",
                "pdf_date": null,
                "publish_date": null,
                "premium_value": 0.001,
                "total_tax": 0,
                "nstp_enabled": "",
                "qnstp_case": "No",
                "expiry_date": null,
                "tp_policy_no": "",
                "tp_reason": "",
                "status": 0,
                "created_by": "agent@insillion.com",
                "policy_id": "P000000000304",
                "cust_fld_1": "",
                "cust_fld_2": "",
                "cust_fld_3": "",
                "cust_fld_4": "",
                "cust_fld_5": "",
                "cust_fld_6": "",
                "cust_fld_7": "",
                "cust_fld_8": "",
                "cust_fld_9": "",
                "cust_fld_10": "",
                "broker_code": "123",
                "agent_code": "null",
                "otp_verified": null,
                "agreed_on": null,
                "agreed_by": "",
                "proxy": "",
                "author": "agent@insillion.com",
                "ip": "proxy_add_x_forwarded_for",
                "c_ts": "2025-11-27 04:31:38",
                "u_ts": "2025-11-27 04:31:38.708514",
                "data": {
                    "product_id": "M000000000005",
                    "customer_first_name": "Rio",
                    "customer_last_name": "R",
                    "customer_email": "rio@anc.com",
                    "customer_phone": "9887989898",
                    "company_name": "Rio Company",
                    "comapany_address_line1": "r street",
                    "company_address_line2": "io post",
                    "company_city": "chennai",
                    "company_state": "tamilnadu",
                    "company_postal_code": "400001",
                    "location_state": "New York",
                    "coverage": "Contents",
                    "property_still_under_construction": "No",
                    "watchperson_service_availed": "Central Station",
                    "extended_coverage": "Yes",
                    "location_city": "Nassau",
                    "location_site_number": "3453534",
                    "location_site_name": "Rio site",
                    "location_address_line1": "Rio add 1",
                    "location_address_line2": "Rio add 2",
                    "location_county": "Nassau",
                    "location_zip": "11204",
                    "location_lat_long": "Lat long",
                    "commercial_operating_date": "10-11-2025",
                    "dc_mw": "DC",
                    "ac_mw": "AD",
                    "annual_output_mwh": "MWH",
                    "mounting_type": "tracker",
                    "inverter_make": "IM",
                    "module_make": "MM",
                    "oandm_provider": "O&M",
                    "property_tiv": "TIVP",
                    "annual_revenue_tiv": "TIVAR",
                    "primary_insurer": "Rio Raj",
                    "bi_waiting_period": "BI",
                    "notes": "Notes",
                    "panel_type": "Ground Mounted",
                    "theft": "Excluded",
                    "restoration_period_extension_in_days": "30",
                    "waiting_period": "11-15 Days",
                    "optional_coverage": "Monthly Period of Indemnity",
                    "commercial_property": "1500000",
                    "business_interruption": "100000",
                    "equipment_breakdown_limit": "100000",
                    "eb_expediting_expense_sublimit": "50000",
                    "insurers_coinsurance": "1",
                    "monthly_limitation": "",
                    "earthquake_coverage": "Yes",
                    "special_perils": "Yes",
                    "broad_perils": "Yes",
                    "equipment_breakdown": "Yes",
                    "flood_coverage": "Yes",
                    "all_other_deductible": "5000",
                    "earthquake_deductible": "0.1",
                    "flood_deductible": "0.1",
                    "business_interruption_deductible_in_days": "30",
                    "equipment_breakdown_deductible_in_dollars": "75000",
                    "soft_cost__extra_expense_deductible": "10",
                    "percent_exposure": "1",
                    "product_name": "R & R Rater",
                    "product_desc": "R & R Rater",
                    "product_group_id": "PG000000000001",
                    "par_product_id": "M000000000001",
                    "wf_id": "8",
                    "premium_value": 0.001,
                    "combo_type": "",
                    "product_group_name": "All LOB",
                    "product_group_code": "ALOB",
                    "catalog": [],
                    "policywordings": [],
                    "policy_id": "P000000000304",
                    "construction_type": "Frame",
                    "class_code": 30500,
                    "_ready": "1",
                    "agent_email": "agent@insillion.com",
                    "agent_last_login": "2025-05-07 07:07:22",
                    "agent_first_name": "Agent",
                    "agent_last_name": "",
                    "agent_designation": "",
                    "agent_alt_email": "",
                    "agent_broker_code": "123",
                    "agent_user_code": "",
                    "agent_broker_id": "BR000000000001",
                    "agent_underwriter": "",
                    "agent_address": "",
                    "agent_state": "",
                    "agent_country": "",
                    "agent_phone_no": "",
                    "agent_mobile_no": "",
                    "agent_two_f_a": "",
                    "agent_two_f_a_key": "",
                    "agent_zulip_id": "",
                    "agent_name": "Agent",
                    "agent_deposit_balance": "28861.1700",
                    "agent_wflow_template": "",
                    "agent_version": "1.24.2-rc.30",
                    "agent_sandbox": "1",
                    "broker_code": "123",
                    "agent_code": "null",
                    "user_code": "",
                    "broker_id": "BR000000000001",
                    "broker_name": "RR Broker",
                    "broker_type": "",
                    "broker_group_id": "G000000000005",
                    "broker_address_1": "",
                    "broker_address_2": "",
                    "broker_phone_no_1": "",
                    "broker_phone_no_2": "",
                    "broker_deposit_balance_mode": "broker",
                    "uuid": "2575c11a-0b09-4917-93b2-33267ade411e",
                    "author": "agent@insillion.com",
                    "proxy": "",
                    "ip": "proxy_add_x_forwarded_for",
                    "quote_id": "Q000000000304",
                    "premium_calc_html_version": 3,
                    "proposal_form_html_version": 3,
                    "premium_calc_js_version": 3,
                    "proposal_form_js_version": 3,
                    "f_premium_value": " $0 ",
                    "ar_basic_coverage_lc": 0,
                    "f_ar_basic_coverage_lc": " $-   ",
                    "ar_special_perils_lc": 0,
                    "f_ar_special_perils_lc": " $-   ",
                    "ar_extended_coverage_lc": 0,
                    "f_ar_extended_coverage_lc": " $-   ",
                    "broad_peril_lc": 0,
                    "f_broad_peril_lc": " $-   ",
                    "total_commercial_property_lc": 0,
                    "f_total_commercial_property_lc": " $-   ",
                    "earthquake_rate": 1242,
                    "f_earthquake_rate": " $1,242.00 ",
                    "flood_coverage_rate": 2468.1,
                    "f_flood_coverage_rate": " $2,468.10 ",
                    "total_all_risk_property_premium": 3710.1,
                    "f_total_all_risk_property_premium": " $3,710.10 ",
                    "rr_basic_coverage_lc": 0,
                    "f_rr_basic_coverage_lc": " $-   ",
                    "rr_special_perils_lc": 0,
                    "f_rr_special_perils_lc": " $-   ",
                    "rr_extended_coverage_lc": 0,
                    "f_rr_extended_coverage_lc": " $-   ",
                    "rr_broad_peril_lc": 0,
                    "f_rr_broad_peril_lc": " $-   ",
                    "rr_total_commercial_property_lc": 0,
                    "f_rr_total_commercial_property_lc": " $-   ",
                    "rr_earthquake_rate": 0,
                    "f_rr_earthquake_rate": " $-   ",
                    "rr_flood_coverage_rate": 0,
                    "f_rr_flood_coverage_rate": " $-   ",
                    "basic_coverage_mix": 0,
                    "f_basic_coverage_mix": "0.00%",
                    "special_perils_mix": 0,
                    "f_special_perils_mix": "0.00%",
                    "extended_coverage_mix": 0,
                    "f_extended_coverage_mix": "0.00%",
                    "broad_perils_mix": 0,
                    "f_broad_perils_mix": "0.00%",
                    "totoal_cp_mix": 0,
                    "f_totoal_cp_mix": "0.00%",
                    "eq_rate_mix": 0.0828,
                    "f_eq_rate_mix": "8.28%",
                    "flood_coverage_mix": 0.1645,
                    "f_flood_coverage_mix": "16.45%",
                    "total_all_risk_property_mix": 0.2473,
                    "f_total_all_risk_property_mix": "24.73%",
                    "rr_basic_coverage_mix": "",
                    "f_rr_basic_coverage_mix": "",
                    "rr_special_perils_mix": "",
                    "f_rr_special_perils_mix": "",
                    "rr_extended_coverage_mix": "",
                    "f_rr_extended_coverage_mix": "",
                    "rr_broad_perils_mix": "",
                    "f_rr_broad_perils_mix": "",
                    "rr_total_cp_mix": "",
                    "f_rr_total_cp_mix": "",
                    "rr_earthquake_mix": "",
                    "f_rr_earthquake_mix": "",
                    "rr_flood_coverage_mix": "",
                    "f_rr_flood_coverage_mix": "",
                    "rr_pemium_mix": "",
                    "f_rr_pemium_mix": "",
                    "mat_premium_summary": [
                        [
                            "Basic Coverage Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Special Perils Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Extended Coverage Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Broad Peril Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Total Commercial Property Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Earthquake Rate",
                            1242,
                            "",
                            0.0828
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Flood Coverage Rate",
                            2468.1,
                            "",
                            0.1645
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Total All Risk Property Premium",
                            3710.1,
                            "",
                            0.2473
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Basic Coverage Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            "Yes"
                        ],
                        [
                            "Special Perils Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            "Included"
                        ],
                        [
                            "Extended Coverage Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Broad Peril Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Total Commercial Property Loss Cost",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Earthquake Rate",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Flood Coverage Rate",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Pre-tax and Fee R&R Premium",
                            0.001,
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Admin Loading",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Broker Fee",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "State Sales Tax",
                            "",
                            "",
                            ""
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Total R&R Premium",
                            "",
                            "",
                            ""
                        ]
                    ],
                    "admin_loading": 0,
                    "f_admin_loading": " $-   ",
                    "broker_fee": 0,
                    "f_broker_fee": " $-   ",
                    "state_sales_tax": 0,
                    "f_state_sales_tax": " $-   ",
                    "total_rr_premium": 0,
                    "f_total_rr_premium": " $-   ",
                    "quote_valid": 1,
                    "total_charges": 0,
                    "charges": {
                        "total": 0,
                        "tax_total": 0,
                        "charge_parts": [
                            {
                                "name": "Admin Loading",
                                "value": 0,
                                "rate": 1
                            },
                            {
                                "name": "Broker Fee",
                                "value": 0,
                                "rate": 1
                            }
                        ],
                        "error": null
                    },
                    "tax_details": {
                        "tax_master_id": "TM000000000006",
                        "tax": 0,
                        "tax_parts": [],
                        "u_ts": "2025-11-24 12:38:28.406387"
                    },
                    "total_tax": 0,
                    "total_amount": "0.00",
                    "nstp_enabled": "",
                    "error_count": 0,
                    "policy_start_time": null,
                    "submission_priority": ""
                },
                "assigned_to": "agent@insillion.com",
                "assigned_by": "agent@insillion.com"
            },
            "document": {
                "document_id": "DT000000000126",
                "proposal_id": "",
                "policy_id": "P000000000304",
                "quote_id": "Q000000000304",
                "product_id": "M000000000005",
                "uuid": "9411e2af-b899-4017-8fad-65dc4e875646",
                "quote_no": "",
                "ready_state": 1,
                "status_desc": "{\"Existing all-risk insurance policy\":\"uploaded\",\"As-built engineering drawings\":\"not-uploaded\",\"Active O&M contract\":\"not-uploaded\",\"Loss runs from the site\":\"not-uploaded\"}",
                "status": 0,
                "created_by": "agent@insillion.com",
                "assigned_to": "agent@insillion.com",
                "proxy": "",
                "author": "agent@insillion.com",
                "ip": "proxy_add_x_forwarded_for",
                "c_ts": "2025-11-27 04:31:38",
                "u_ts": "2025-11-27 04:32:12.202645",
                "data": {
                    "policy_id": "P000000000304",
                    "product_id": "M000000000005",
                    "product_group_id": "PG000000000001",
                    "par_product_id": "M000000000001",
                    "quote_id": "Q000000000304",
                    "proposal_id": "",
                    "discount_id": "",
                    "document_id": "DT000000000126",
                    "nstp_id": "",
                    "payment_id": "",
                    "covernote_id": "",
                    "inspect_id": "",
                    "cart_id": "",
                    "uuid": "9411e2af-b899-4017-8fad-65dc4e875646",
                    "customer_id": "",
                    "quote_no": "",
                    "proposal_no": "",
                    "tp_policy_no": "",
                    "parent_policy_no": "",
                    "cert_id": "",
                    "nstp_enabled": "",
                    "qnstp_enabled": "Yes",
                    "pnstp_enabled": "",
                    "nstp_case": "",
                    "qnstp_case": "",
                    "pnstp_case": "",
                    "policy_start_date": "",
                    "policy_end_date": "",
                    "master_policy_no": "",
                    "combo_policy_id": "",
                    "ckyc_by": "",
                    "archive_url": "",
                    "cust_fld_1": "",
                    "cust_fld_2": "",
                    "cust_fld_3": "",
                    "cust_fld_4": "",
                    "cust_fld_5": "",
                    "cust_fld_6": "",
                    "cust_fld_7": "",
                    "cust_fld_8": "",
                    "cust_fld_9": "",
                    "cust_fld_10": "",
                    "broker_code": "",
                    "agent_code": "",
                    "created_by": "agent@insillion.com",
                    "created_by_proxy": "",
                    "assigned_to": "agent@insillion.com",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": "proxy_add_x_forwarded_for",
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.320190"
                },
                "details": []
            },
            "qnstp": {
                "nstp_id": "N000000000187",
                "stage": "quote",
                "policy_id": "P000000000304",
                "product_id": "M000000000005",
                "product_group_id": "PG000000000001",
                "quote_id": "Q000000000304",
                "proposal_id": "",
                "uuid": "2f9fc581-e16e-4152-b0dc-8c24e3f97b0f",
                "premium_value": 0,
                "nstp_enabled": "Yes",
                "nstp_status": "",
                "reason": "nstp-case w flag did not match Yes",
                "status_code": "",
                "status": 0,
                "created_by": "agent@insillion.com",
                "created_by_proxy": "",
                "assigned_to": "",
                "proxy": "",
                "author": "agent@insillion.com",
                "ip": "proxy_add_x_forwarded_for",
                "c_ts": "2025-11-27 04:31:38",
                "u_ts": "2025-11-27 04:31:38.793921",
                "data": {
                    "policy_id": "P000000000304",
                    "product_id": "M000000000005",
                    "product_group_id": "PG000000000001",
                    "quote_id": "Q000000000304",
                    "proposal_id": "",
                    "uuid": "2f9fc581-e16e-4152-b0dc-8c24e3f97b0f",
                    "premium_value": 0,
                    "nstp_status": "approved",
                    "nstp_enabled": "Yes",
                    "reason": "nstp-case w flag did not match Yes",
                    "created_by": "agent@insillion.com",
                    "created_by_proxy": "",
                    "stage": "quote",
                    "status": 0,
                    "author": "agent@insillion.com",
                    "proxy": "",
                    "ip": "proxy_add_x_forwarded_for",
                    "nstp_id": "N000000000187",
                    "qnstp_id": "N000000000187"
                },
                "qnstp_id": "N000000000187",
                "details": [
                    {
                        "nstp_details_id": "ND000000000146",
                        "nstp_id": "N000000000187",
                        "uuid": "a6493558-c14f-43fd-a5eb-1d70d4cadf50",
                        "reason": "quotation modified, unapproved",
                        "ext_id": "",
                        "nstp_status": "",
                        "status": 0,
                        "created_by": "agent@insillion.com",
                        "assigned_to": "",
                        "proxy": "",
                        "author": "agent@insillion.com",
                        "ip": "proxy_add_x_forwarded_for",
                        "c_ts": "2025-11-27 04:31:38",
                        "u_ts": "2025-11-27 04:31:38.809245"
                    }
                ]
            },
            "qnstp_id": "N000000000187",
            "proposal": {
                "proposal_id": "",
                "data": {}
            },
            "payment": {
                "payment_id": "",
                "data": {}
            },
            "policy": {
                "policy_id": "P000000000304",
                "product_id": "M000000000005",
                "wf_id": 8,
                "product_group_id": "PG000000000001",
                "par_product_id": "M000000000001",
                "quote_id": "Q000000000304",
                "proposal_id": "",
                "discount_id": "",
                "document_id": "DT000000000126",
                "nstp_id": "",
                "payment_id": "",
                "covernote_id": "",
                "inspect_id": "",
                "cart_id": "",
                "uuid": "1968547b-dd43-44d1-b7d9-8ab3cf75ff79",
                "customer_id": "",
                "policy_no": null,
                "quote_no": "",
                "proposal_no": "",
                "tp_policy_no": "",
                "parent_policy_no": "",
                "renewal_count": 0,
                "issue_date": null,
                "cert_id": "",
                "pdf_date": null,
                "nstp_enabled": "",
                "qnstp_enabled": "Yes",
                "pnstp_enabled": "",
                "nstp_case": "",
                "qnstp_case": "No",
                "pnstp_case": "",
                "policy_start_date": "",
                "policy_end_date": "",
                "policy_start_date_dt": null,
                "policy_end_date_dt": null,
                "policy_start_date_dt_ext": null,
                "policy_end_date_dt_ext": null,
                "master_policy_no": "",
                "combo_policy_id": "",
                "ckyc_on": null,
                "ckyc_by": "",
                "archive_url": "",
                "cust_fld_1": "",
                "cust_fld_2": "",
                "cust_fld_3": "",
                "cust_fld_4": "",
                "cust_fld_5": "",
                "cust_fld_6": "",
                "cust_fld_7": "",
                "cust_fld_8": "",
                "cust_fld_9": "",
                "cust_fld_10": "",
                "broker_code": "123",
                "agent_code": "null",
                "status": 0,
                "created_by": "agent@insillion.com",
                "created_by_proxy": "",
                "assigned_to": "agent@insillion.com",
                "proxy": "",
                "author": "agent@insillion.com",
                "ip": "proxy_add_x_forwarded_for",
                "c_ts": "2025-11-27 04:31:38",
                "u_ts": "2025-11-27 04:31:38.551689",
                "data": {}
            },
            "stage_status": [
                {
                    "policy_id": "P000000000304",
                    "stage": "document",
                    "stage_index": 2,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.369157"
                },
                {
                    "policy_id": "P000000000304",
                    "stage": "payment",
                    "stage_index": 5,
                    "status": "",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.369157"
                },
                {
                    "policy_id": "P000000000304",
                    "stage": "policy",
                    "stage_index": 6,
                    "status": "",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.369157"
                },
                {
                    "policy_id": "P000000000304",
                    "stage": "proposal",
                    "stage_index": 4,
                    "status": "",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.369157"
                },
                {
                    "policy_id": "P000000000304",
                    "stage": "qnstp",
                    "stage_index": 3,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.369157"
                },
                {
                    "policy_id": "P000000000304",
                    "stage": "quote",
                    "stage_index": 0,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-11-27 04:31:38",
                    "u_ts": "2025-11-27 04:31:38.369157"
                }
            ],
            "stages": {
                "document": "inprogress",
                "payment": "",
                "policy": "",
                "proposal": "",
                "qnstp": "inprogress",
                "quote": "inprogress"
            }
        }
    ]
}
 ```
