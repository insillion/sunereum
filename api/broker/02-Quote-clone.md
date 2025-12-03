### API Endpoint: Clone Quote
This endpoint allows users to clone an existing insurance quote based on its `quote_id`. It creates a new quote with the same details as the original, providing a convenient way to duplicate quote configurations.
#### Request Format
- **Method**: POST
    
- **URL**: `{{base_url}}/api/v1/quote/clone`
    
- **Content-Type**: application/json
    
#### Headers
- `in-auth-token` (string): An authentication token required for accessing the API.


#### Important Note: Handling Cloned Quote IDs for Updates

When the quote/clone API is successfully executed, it generates a new and distinct quote_id for the cloned quote. This new ID is typically derived from the original quote_id with a specific suffix. For example, if you clone a quote with quote_id Q000000000327, the cloned quote might receive an ID like Q0000000003271.001.

To proceed with modifying this newly cloned quote (e.g., to update its details), you must use this specific cloned quote ID in any subsequent calls to the quote/save API (or similar update endpoints).

Consequence of Not Using the Cloned ID:
Failing to provide the correct cloned quote ID to the quote/save API will result in the quote/save endpoint creating an entirely new quote instead of updating the one you intended to modify.  



#### Request Body
The request body must be in JSON format and should include the following field:
- `quote_id` (string) (Required): The identifier of the existing quote to be cloned.
    
**Example Request Body**:
``` json
{
    "quote_id": "Q000000000327"
}

```

#### Sample Response Format

On a successful request, the API will return a JSON response with the following structure:

- `status` (integer): The status of the request (0 indicates success).
    
- `txt` (string): A message related to the status.
    
- `data` (array): An array containing details about the created quote and associated entities, including:
    
    - `policy_id`: Identifier for the policy.
        
    - `product_id`: Identifier for the product.
        
    - `quote_id`: Identifier for the quote.
        
    - `premium_value`: The calculated premium value.
        
    - `quote`: An object containing detailed information about the quote, including customer information, coverage details, and more.
        

**Example Response Body**:
``` json
 {
            "policy_id": "P000000000338",
            "product_id": "M000000000005",
            "wf_id": 8,
            "product_group_id": "PG000000000001",
            "par_product_id": "M000000000001",
            "quote_id": "Q0000000003271.003",
            "proposal_id": "",
            "discount_id": "",
            "document_id": "DT000000000160",
            "nstp_id": "",
            "payment_id": "",
            "covernote_id": "",
            "inspect_id": "",
            "cart_id": "",
            "uuid": "75c379cc-c35d-4675-9edd-e4a367800354",
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
            "c_ts": "2025-12-03 12:20:31",
            "u_ts": "2025-12-03 12:20:32.074549",
            "assigned_by": "agent@insillion.com",
            "assigned_at": "2025-12-03 12:20:31",
            "data": {},
            "quote": {
                "quote_id": "Q0000000003271.003",
                "wf_id": 8,
                "uuid": "04107ce5-73f9-4bd5-8182-b2560d0fbbd1",
                "quote_no": null,
                "par_quote_id": "Q000000000327",
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
                "quote_date": "2025-12-03 12:20:31",
                "valid_till": null,
                "cert_id": "",
                "pdf_date": null,
                "publish_date": null,
                "premium_value": 0,
                "total_tax": 0,
                "nstp_enabled": "",
                "qnstp_case": "No",
                "expiry_date": null,
                "tp_policy_no": "",
                "tp_reason": "",
                "status": 0,
                "created_by": "agent@insillion.com",
                "policy_id": "P000000000338",
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
                "c_ts": "2025-12-03 12:20:31",
                "u_ts": "2025-12-03 12:20:32.107651",
                "data": {
                    "quote_id": "Q0000000003271.003",
                    "wf_id": 8,
                    "product_id": "M000000000005",
                    "product_name": "R & R Rater",
                    "product_desc": "R & R Rater",
                    "product_group_id": "PG000000000001",
                    "par_product_id": "M000000000001",
                    "combo_type": "",
                    "product_group_name": "All LOB",
                    "product_group_code": "ALOB",
                    "catalog": [],
                    "policywordings": [],
                    "location_county": "Nassau",
                    "construction_type": "Frame",
                    "class_code": "30500",
                    "coverage": "Contents",
                    "property_still_under_construction": "No",
                    "watchperson_service_availed": "Central Station",
                    "extended_coverage": "Yes",
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
                    "uuid": "2acd7f20-09e8-4c03-92cc-c9b0eb401dd6",
                    "ip": "proxy_add_x_forwarded_for",
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
                    "location_city": "Nassau",
                    "location_site_number": "3453534",
                    "location_site_name": "Rio site",
                    "location_address_line1": "Rio add 1",
                    "location_address_line2": "Rio add 2",
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
                    "monthly_limitation": "1/3",
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
                    "premium_calc_html_version": 4,
                    "proposal_form_html_version": 3,
                    "premium_calc_js_version": 4,
                    "proposal_form_js_version": 3,
                    "f_premium_value": " $3,140 ",
                    "ar_basic_coverage_lc": 1924.48,
                    "f_ar_basic_coverage_lc": " $1,924.48 ",
                    "ar_special_perils_lc": 73.24,
                    "f_ar_special_perils_lc": " $73.24 ",
                    "ar_extended_coverage_lc": 1127.19,
                    "f_ar_extended_coverage_lc": " $1,127.19 ",
                    "broad_peril_lc": 57.07,
                    "f_broad_peril_lc": " $57.07 ",
                    "total_commercial_property_lc": 3181.98,
                    "f_total_commercial_property_lc": " $3,181.98 ",
                    "earthquake_rate": 1242,
                    "f_earthquake_rate": " $1,242.00 ",
                    "flood_coverage_rate": 2468.1,
                    "f_flood_coverage_rate": " $2,468.10 ",
                    "total_all_risk_property_premium": 6892.08,
                    "f_total_all_risk_property_premium": " $6,892.08 ",
                    "rr_basic_coverage_lc": 1383.4,
                    "f_rr_basic_coverage_lc": " $1,383.40 ",
                    "rr_special_perils_lc": 79.55,
                    "f_rr_special_perils_lc": " $79.55 ",
                    "rr_extended_coverage_lc": 1070.59,
                    "f_rr_extended_coverage_lc": " $1,070.59 ",
                    "rr_broad_peril_lc": 61.98,
                    "f_rr_broad_peril_lc": " $61.98 ",
                    "rr_total_commercial_property_lc": 2595.52,
                    "f_rr_total_commercial_property_lc": " $2,595.52 ",
                    "rr_earthquake_rate": 129.6,
                    "f_rr_earthquake_rate": " $129.60 ",
                    "rr_flood_coverage_rate": 414.72,
                    "f_rr_flood_coverage_rate": " $414.72 ",
                    "basic_coverage_mix": 0.1283,
                    "f_basic_coverage_mix": "12.83%",
                    "special_perils_mix": 0.0049,
                    "f_special_perils_mix": "0.49%",
                    "extended_coverage_mix": 0.0751,
                    "f_extended_coverage_mix": "7.51%",
                    "broad_perils_mix": 0.0038,
                    "f_broad_perils_mix": "0.38%",
                    "totoal_cp_mix": 0.2121,
                    "f_totoal_cp_mix": "21.21%",
                    "eq_rate_mix": 0.0828,
                    "f_eq_rate_mix": "8.28%",
                    "flood_coverage_mix": 0.1645,
                    "f_flood_coverage_mix": "16.45%",
                    "total_all_risk_property_mix": 0.4595,
                    "f_total_all_risk_property_mix": "45.95%",
                    "rr_basic_coverage_mix": 0.9223,
                    "f_rr_basic_coverage_mix": "92.23%",
                    "rr_special_perils_mix": 0.053,
                    "f_rr_special_perils_mix": "5.30%",
                    "rr_extended_coverage_mix": 0.7137,
                    "f_rr_extended_coverage_mix": "71.37%",
                    "rr_broad_perils_mix": 0.0413,
                    "f_rr_broad_perils_mix": "4.13%",
                    "rr_total_cp_mix": 1.7303,
                    "f_rr_total_cp_mix": "173.03%",
                    "rr_earthquake_mix": 0.0864,
                    "f_rr_earthquake_mix": "8.64%",
                    "rr_flood_coverage_mix": 0.2765,
                    "f_rr_flood_coverage_mix": "27.65%",
                    "rr_pemium_mix": 2.0932,
                    "f_rr_pemium_mix": "209.32%",
                    "mat_premium_summary": [
                        [
                            "Basic Coverage Loss Cost",
                            1924.48,
                            "",
                            0.1283
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Special Perils Loss Cost",
                            73.24,
                            "",
                            0.0049
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Extended Coverage Loss Cost",
                            1127.19,
                            "",
                            0.0751
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Broad Peril Loss Cost",
                            57.07,
                            "",
                            0.0038
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Total Commercial Property Loss Cost",
                            3181.98,
                            "",
                            0.2121
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
                            6892.08,
                            "",
                            0.4595
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
                            1383.4,
                            "",
                            0.9223
                        ],
                        [
                            "",
                            "",
                            "",
                            "Yes"
                        ],
                        [
                            "Special Perils Loss Cost",
                            79.55,
                            "",
                            0.053
                        ],
                        [
                            "",
                            "",
                            "",
                            "Included"
                        ],
                        [
                            "Extended Coverage Loss Cost",
                            1070.59,
                            "",
                            0.7137
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Broad Peril Loss Cost",
                            61.98,
                            "",
                            0.0413
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Total Commercial Property Loss Cost",
                            2595.52,
                            "",
                            1.7303
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Earthquake Rate",
                            129.6,
                            "",
                            0.0864
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Flood Coverage Rate",
                            414.72,
                            "",
                            0.2765
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
                            3139.84,
                            "",
                            2.0932
                        ],
                        [
                            "",
                            "",
                            "",
                            ""
                        ],
                        [
                            "Admin Loading",
                            627.97,
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
                            627.97,
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
                            379.14,
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
                            4774.92,
                            "",
                            ""
                        ]
                    ],
                    "admin_loading": 627.97,
                    "f_admin_loading": " $627.97 ",
                    "broker_fee": 627.97,
                    "f_broker_fee": " $627.97 ",
                    "state_sales_tax": 379.14,
                    "f_state_sales_tax": " $379.14 ",
                    "total_rr_premium": 4774.92,
                    "f_total_rr_premium": " $4,774.92 ",
                    "quote_valid": 1,
                    "total_charges": 1255.94,
                    "charges": {
                        "total": 1255.94,
                        "tax_total": 0,
                        "charge_parts": [
                            {
                                "name": "Admin Loading",
                                "value": 627.97,
                                "rate": 1
                            },
                            {
                                "name": "Broker Fee",
                                "value": 627.97,
                                "rate": 1
                            }
                        ],
                        "error": null
                    },
                    "tax_details": {
                        "tax_master_id": "TM000000000006",
                        "tax": 379.14,
                        "tax_parts": [
                            {
                                "name": "State Sales Tax",
                                "rate": 0,
                                "value": 379.14,
                                "amount": 3139.84,
                                "absolute": false
                            }
                        ],
                        "u_ts": "2025-11-24 12:38:28.406387"
                    },
                    "total_amount": "4774.92",
                    "error_count": 0,
                    "policy_start_time": null,
                    "submission_priority": "",
                    "company_country": "test",
                    "wind_zone": "Zone 2",
                    "par_quote_id": "Q000000000327",
                    "parent_policy_no": "",
                    "customer_id": "",
                    "first_name": "",
                    "last_name": "",
                    "email": "",
                    "mobile_no": "",
                    "id_1": "",
                    "id_1_type": "",
                    "id_2": "",
                    "id_2_type": "",
                    "status": 0,
                    "created_by": "agent@insillion.com",
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
                    "assigned_to": "agent@insillion.com",
                    "assigned_by": "angel@sunereum.com",
                    "policy_id": "P000000000338"
                },
                "assigned_to": "agent@insillion.com",
                "assigned_by": "agent@insillion.com"
            },
            "document": {
                "document_id": "DT000000000160",
                "proposal_id": "",
                "policy_id": "P000000000338",
                "quote_id": "Q0000000003271.003",
                "product_id": "M000000000005",
                "uuid": "f77a5535-6e1e-4040-930e-30d95b7e223c",
                "quote_no": "",
                "ready_state": 0,
                "status_desc": "{\"Existing all-risk insurance policy\":\"not-uploaded\",\"As-built engineering drawings\":\"not-uploaded\",\"Active O&M contract\":\"not-uploaded\",\"Loss runs from the site\":\"not-uploaded\"}",
                "status": 0,
                "created_by": "agent@insillion.com",
                "assigned_to": "agent@insillion.com",
                "proxy": "",
                "author": "agent@insillion.com",
                "ip": "proxy_add_x_forwarded_for",
                "c_ts": "2025-12-03 12:20:31",
                "u_ts": "2025-12-03 12:20:31.984519",
                "data": {
                    "policy_id": "P000000000338",
                    "product_id": "M000000000005",
                    "product_group_id": "PG000000000001",
                    "par_product_id": "M000000000001",
                    "quote_id": "Q0000000003271.003",
                    "proposal_id": "",
                    "discount_id": "",
                    "document_id": "DT000000000160",
                    "nstp_id": "",
                    "payment_id": "",
                    "covernote_id": "",
                    "inspect_id": "",
                    "cart_id": "",
                    "uuid": "f77a5535-6e1e-4040-930e-30d95b7e223c",
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
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.694915"
                },
                "details": []
            },
            "qnstp": {
                "nstp_id": "N000000000221",
                "stage": "quote",
                "policy_id": "P000000000338",
                "product_id": "M000000000005",
                "product_group_id": "PG000000000001",
                "quote_id": "Q0000000003271.003",
                "proposal_id": "",
                "uuid": "20b17b07-b07d-43c6-95d4-ab36f8fa45f6",
                "premium_value": 0,
                "nstp_enabled": "Yes",
                "nstp_status": "approved",
                "reason": "nstp-case w flag did not match Yes",
                "status_code": "",
                "status": 0,
                "created_by": "agent@insillion.com",
                "created_by_proxy": "",
                "assigned_to": "",
                "proxy": "",
                "author": "agent@insillion.com",
                "ip": "proxy_add_x_forwarded_for",
                "c_ts": "2025-12-03 12:20:32",
                "u_ts": "2025-12-03 12:20:32.027212",
                "data": {
                    "policy_id": "P000000000338",
                    "product_id": "M000000000005",
                    "product_group_id": "PG000000000001",
                    "quote_id": "Q0000000003271.003",
                    "proposal_id": "",
                    "uuid": "20b17b07-b07d-43c6-95d4-ab36f8fa45f6",
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
                    "nstp_id": "N000000000221",
                    "qnstp_id": "N000000000221"
                },
                "qnstp_id": "N000000000221",
                "details": []
            },
            "qnstp_id": "N000000000221",
            "proposal": {
                "proposal_id": "",
                "data": {}
            },
            "payment": {
                "payment_id": "",
                "data": {}
            },
            "policy": {
                "policy_id": "P000000000338",
                "product_id": "M000000000005",
                "wf_id": 8,
                "product_group_id": "PG000000000001",
                "par_product_id": "M000000000001",
                "quote_id": "Q0000000003271.003",
                "proposal_id": "",
                "discount_id": "",
                "document_id": "DT000000000160",
                "nstp_id": "",
                "payment_id": "",
                "covernote_id": "",
                "inspect_id": "",
                "cart_id": "",
                "uuid": "75c379cc-c35d-4675-9edd-e4a367800354",
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
                "c_ts": "2025-12-03 12:20:31",
                "u_ts": "2025-12-03 12:20:32.074549",
                "data": {}
            },
            "stage_status": [
                {
                    "policy_id": "P000000000338",
                    "stage": "document",
                    "stage_index": 2,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.791828"
                },
                {
                    "policy_id": "P000000000338",
                    "stage": "payment",
                    "stage_index": 5,
                    "status": "",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.791828"
                },
                {
                    "policy_id": "P000000000338",
                    "stage": "policy",
                    "stage_index": 6,
                    "status": "",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.791828"
                },
                {
                    "policy_id": "P000000000338",
                    "stage": "proposal",
                    "stage_index": 4,
                    "status": "",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.791828"
                },
                {
                    "policy_id": "P000000000338",
                    "stage": "qnstp",
                    "stage_index": 3,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.791828"
                },
                {
                    "policy_id": "P000000000338",
                    "stage": "quote",
                    "stage_index": 0,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "agent@insillion.com",
                    "ip": null,
                    "c_ts": "2025-12-03 12:20:31",
                    "u_ts": "2025-12-03 12:20:31.791828"
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

```