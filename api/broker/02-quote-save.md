### API Endpoint: Create Quote

This endpoint allows users to create a new insurance quote based on the provided parameters. It is primarily used for generating quotes in the context of insurance.

#### Request Format

- **Method**: POST
    
- **URL**: `{{base_url}}/api/v1/quote`
    
- **Content-Type**: application/json
    

#### Request Body

This document outlines the fields present in the quote/policy JSON object, providing a description of each field and its expected data type.

The request body must be in JSON format and should include the following fields:
- `product_id` (string) (Constant): The identifier for the product.
- `customer_first_name` (string): The first name of the customer.
- `customer_last_name` (string): The last name of the customer.
- `customer_email` (string): The email address of the customer.
- `customer_phone` (string): The phone number of the customer.
- `company_name` (string): The name of the company.
- `comapany_address_line1` (string): The first line of the company's address.
- `company_address_line2` (string): The second line of the company's address.
- `company_city` (string): The city of the company's address.
- `company_state` (string): The state of the company's address.
- `company_postal_code` (string): The postal code of the company's address.
- `location_state` (string): The state where the insured property is located.
- `coverage` (string): The primary type of coverage selected.
- `property_still_under_construction` (string): Indicates if the property is still under construction.
- `watchperson_service_availed` (string): Describes the status of watchperson services for the property.
- `extended_coverage` (string): Indicates if extended coverage is selected.
- `location_city` (string): The city where the insured property is located.
- `location_site_number` (string): The number identifying the location site.
- `location_site_name` (string): The name of the insured location/site.
- `location_address_line1` (string): The first line of the location's address.
- `location_address_line2` (string): The second line of the location's address.
- `location_county` (string): The county of the insured location.
- `location_zip` (string): The zip code of the insured location.
- `location_lat_long` (string): The latitude and longitude coordinates of the insured location.
- `commercial_operating_date` (string): The date when commercial operations began.
- `dc_mw` (string): DC megawatt capacity.
- `ac_mw` (string): AC megawatt capacity.
- `annual_output_mwh` (string): Annual output in megawatt-hours.
- `mounting_type` (string): Type of mounting for equipment (e.g., solar panels).
- `inverter_make` (string): Make of the inverter.
- `module_make` (string): Make of the module.
- `oandm_provider` (string): Operations and Maintenance provider.
- `property_tiv` (string): Total Insured Value (TIV) for the property.
- `annual_revenue_tiv` (string): Total Insured Value (TIV) for annual revenue.
- `primary_insurer` (string): Name of the primary insurer.
- `bi_waiting_period` (string): Business Interruption waiting period.
- `notes` (string): General notes or comments.
- `panel_type` (string): Type of panel used.
- `theft` (string): Theft coverage status.
- `restoration_period_extension_in_days` (string): Extension for the restoration period in days.
- `waiting_period` (string): The waiting period before coverage applies.
- `optional_coverage` (string): Description of the optional coverage selected.
- `commercial_property` (string): Limit for commercial property coverage.
- `business_interruption` (string): Limit for business interruption coverage.
- `equipment_breakdown_limit` (string): Limit for equipment breakdown coverage.
- `eb_expediting_expense_sublimit` (string): Sublimit for expediting expenses under equipment breakdown.
- `insurers_coinsurance` (string): Coinsurance percentage from the insurer.
- `monthly_limitation` (string): Monthly limitation for certain coverages.
- `earthquake_coverage` (string): Indicates if earthquake coverage is selected.
- `special_perils` (string): Indicates if special perils coverage is selected.
- `broad_perils` (string): Indicates if broad perils coverage is selected.
- `equipment_breakdown` (string): Indicates if equipment breakdown coverage is selected.
- `flood_coverage` (string): Indicates if flood coverage is selected.
- `all_other_deductible` (string): Deductible for all other perils.
- `earthquake_deductible` (string): Deductible for earthquake coverage.
- `flood_deductible` (string): Deductible for flood coverage.
- `business_interruption_deductible_in_days` (string): Business interruption deductible in days.
- `equipment_breakdown_deductible_in_dollars` (string): Equipment breakdown deductible in dollars.
- `soft_cost__extra_expense_deductible` (string): Deductible for soft cost and extra expense.
- `percent_exposure` (string): Percentage of exposure.

**Example Request Body**:

` json
{
    "product_id": "M000000000004",
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
    "percent_exposure": "1"
}

 `

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
        

**Example Response**:

` json
{
    "status": 0,
    "txt": "",
    "data": [
        {
            "policy_id": "P000000000131",
            "product_id": "M000000000004",
            "wf_id": 7,
            "product_group_id": "PG000000000001",
            "par_product_id": "M000000000001",
            "quote_id": "Q000000000131",
            "proposal_id": "",
            "discount_id": "",
            "document_id": "DT000000000129",
            "nstp_id": "",
            "payment_id": "",
            "covernote_id": "",
            "inspect_id": "",
            "cart_id": "",
            "uuid": "217aa681-6bc0-4e61-b544-48c184d116ec",
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
            "created_by": "broker@sunereum.cloware.in",
            "created_by_proxy": "",
            "assigned_to": "broker@sunereum.cloware.in",
            "proxy": "",
            "author": "broker@sunereum.cloware.in",
            "ip": "10.81.234.138",
            "c_ts": "2025-11-10 13:05:13",
            "u_ts": "2025-11-10 13:05:13.410381",
            "assigned_by": "broker@sunereum.cloware.in",
            "assigned_at": "2025-11-10 13:05:13",
            "data": {},
            "quote": {
                "quote_id": "Q000000000131",
                "wf_id": 7,
                "uuid": "875ee8ee-8101-4175-a50e-0acf4f978485",
                "quote_no": null,
                "par_quote_id": "",
                "parent_policy_no": "",
                "customer_id": "",
                "product_id": "M000000000004",
                "product_group_id": "PG000000000001",
                "first_name": "",
                "last_name": "",
                "email": "",
                "mobile_no": "",
                "id_1": "",
                "id_1_type": "",
                "id_2": "",
                "id_2_type": "",
                "quote_date": "2025-11-10 13:05:13",
                "valid_till": null,
                "cert_id": "",
                "pdf_date": null,
                "publish_date": null,
                "premium_value": 1,
                "total_tax": 0,
                "nstp_enabled": "",
                "qnstp_case": "No",
                "expiry_date": null,
                "tp_policy_no": "",
                "tp_reason": "",
                "status": 0,
                "created_by": "broker@sunereum.cloware.in",
                "policy_id": "P000000000131",
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
                "author": "broker@sunereum.cloware.in",
                "ip": "10.81.234.138",
                "c_ts": "2025-11-10 13:05:13",
                "u_ts": "2025-11-10 13:05:13.638572",
                "data": {
                    "product_id": "M000000000004",
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
                    "wf_id": "7",
                    "premium_value": 1,
                    "combo_type": "",
                    "product_group_name": "All LOB",
                    "product_group_code": "ALOB",
                    "catalog": [],
                    "policywordings": [],
                    "policy_id": "P000000000131",
                    "construction_type": "Frame",
                    "_ready": "1",
                    "agent_email": "broker@sunereum.cloware.in",
                    "agent_first_name": "",
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
                    "agent_zulip_id": "",
                    "agent_name": "broker",
                    "broker_code": "123",
                    "agent_code": "null",
                    "user_code": "",
                    "broker_id": "BR000000000001",
                    "broker_name": "Broker",
                    "broker_type": "",
                    "broker_group_id": "G000000000005",
                    "broker_address_1": "",
                    "broker_address_2": "",
                    "broker_phone_no_1": "",
                    "broker_phone_no_2": "",
                    "broker_deposit_balance_mode": "broker",
                    "uuid": "875ee8ee-8101-4175-a50e-0acf4f978485",
                    "author": "broker@sunereum.cloware.in",
                    "proxy": "",
                    "ip": "10.81.234.138",
                    "quote_id": "Q000000000131",
                    "premium_calc_html_version": 16,
                    "proposal_form_html_version": 16,
                    "premium_calc_js_version": 16,
                    "proposal_form_js_version": 16,
                    "f_premium_value": " $1.00 ",
                    "ar_basic_coverage_lc": "",
                    "f_ar_basic_coverage_lc": "",
                    "ar_special_perils_lc": 0,
                    "f_ar_special_perils_lc": " $-   ",
                    "ar_extended_coverage_lc": 0,
                    "f_ar_extended_coverage_lc": " $-   ",
                    "broad_peril_lc": 0,
                    "f_broad_peril_lc": " $-   ",
                    "total_commercial_property_lc": "",
                    "f_total_commercial_property_lc": "",
                    "earthquake_rate": 1242,
                    "f_earthquake_rate": " $1,242.00 ",
                    "flood_coverage_rate": 2468.1,
                    "f_flood_coverage_rate": " $2,468.10 ",
                    "total_all_risk_property_premium": "",
                    "f_total_all_risk_property_premium": "",
                    "rr_basic_coverage_lc": "",
                    "f_rr_basic_coverage_lc": "",
                    "rr_special_perils_lc": 0,
                    "f_rr_special_perils_lc": " $-   ",
                    "rr_extended_coverage_lc": 0,
                    "f_rr_extended_coverage_lc": " $-   ",
                    "rr_broad_peril_lc": 0,
                    "f_rr_broad_peril_lc": " $-   ",
                    "rr_total_commercial_property_lc": "",
                    "f_rr_total_commercial_property_lc": "",
                    "rr_earthquake_rate": 0,
                    "f_rr_earthquake_rate": " $-   ",
                    "rr_flood_coverage_rate": 0,
                    "f_rr_flood_coverage_rate": " $-   ",
                    "basic_coverage_mix": "",
                    "f_basic_coverage_mix": "",
                    "special_perils_mix": 0,
                    "f_special_perils_mix": " -   ",
                    "extended_coverage_mix": 0,
                    "f_extended_coverage_mix": " -   ",
                    "broad_perils_mix": 0,
                    "f_broad_perils_mix": " -   ",
                    "totoal_cp_mix": "",
                    "f_totoal_cp_mix": "",
                    "eq_rate_mix": 0.0828,
                    "f_eq_rate_mix": " 0.08 ",
                    "flood_coverage_mix": 0.1645,
                    "f_flood_coverage_mix": " 0.16 ",
                    "total_all_risk_property_mix": "",
                    "f_total_all_risk_property_mix": "",
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
                            "Total R&R Premium (incl. admin and broker fees)",
                            1,
                            "",
                            ""
                        ]
                    ],
                    "quote_valid": 1,
                    "total_charges": 0,
                    "charges": {
                        "total": 0,
                        "tax_total": 0,
                        "charge_parts": [],
                        "error": null
                    },
                    "tax_details": {
                        "tax": 0,
                        "tax_parts": [],
                        "master": {},
                        "error": ""
                    },
                    "total_tax": 0,
                    "total_amount": "1.00",
                    "nstp_enabled": "",
                    "error_count": 0,
                    "policy_start_time": null,
                    "submission_priority": ""
                },
                "assigned_to": "broker@sunereum.cloware.in",
                "assigned_by": "broker@sunereum.cloware.in"
            },
            "document": {
                "document_id": "DT000000000129",
                "proposal_id": "",
                "policy_id": "P000000000131",
                "quote_id": "Q000000000131",
                "product_id": "M000000000004",
                "uuid": "8e626ad1-f234-43ad-82c1-7347abeab71a",
                "quote_no": "",
                "ready_state": 0,
                "status_desc": "{\"Existing all-risk insurance policy\":\"not-uploaded\",\"As-built engineering drawings\":\"not-uploaded\",\"Active O&M contract\":\"not-uploaded\",\"Loss runs from the site\":\"not-uploaded\"}",
                "status": 0,
                "created_by": "broker@sunereum.cloware.in",
                "assigned_to": "broker@sunereum.cloware.in",
                "proxy": "",
                "author": "broker@sunereum.cloware.in",
                "ip": "10.81.234.138",
                "c_ts": "2025-11-10 13:05:13",
                "u_ts": "2025-11-10 13:05:13.390046",
                "data": {
                    "policy_id": "P000000000131",
                    "product_id": "M000000000004",
                    "product_group_id": "PG000000000001",
                    "par_product_id": "M000000000001",
                    "quote_id": "Q000000000131",
                    "proposal_id": "",
                    "discount_id": "",
                    "document_id": "DT000000000129",
                    "nstp_id": "",
                    "payment_id": "",
                    "covernote_id": "",
                    "inspect_id": "",
                    "cart_id": "",
                    "uuid": "8e626ad1-f234-43ad-82c1-7347abeab71a",
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
                    "created_by": "broker@sunereum.cloware.in",
                    "created_by_proxy": "",
                    "assigned_to": "broker@sunereum.cloware.in",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": "10.81.234.138",
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.330843"
                },
                "details": []
            },
            "qnstp": {
                "nstp_id": "N000000000146",
                "stage": "quote",
                "policy_id": "P000000000131",
                "product_id": "M000000000004",
                "product_group_id": "PG000000000001",
                "quote_id": "Q000000000131",
                "proposal_id": "",
                "uuid": "1c40d7c5-0ca5-4f41-a244-abf11272e81f",
                "premium_value": 0,
                "nstp_enabled": "Yes",
                "nstp_status": "",
                "reason": "nstp-case w flag did not match Yes",
                "status_code": "",
                "status": 0,
                "created_by": "broker@sunereum.cloware.in",
                "created_by_proxy": "",
                "assigned_to": "",
                "proxy": "",
                "author": "broker@sunereum.cloware.in",
                "ip": "10.81.234.138",
                "c_ts": "2025-11-10 13:05:13",
                "u_ts": "2025-11-10 13:05:13.653816",
                "data": {
                    "policy_id": "P000000000131",
                    "product_id": "M000000000004",
                    "product_group_id": "PG000000000001",
                    "quote_id": "Q000000000131",
                    "proposal_id": "",
                    "uuid": "1c40d7c5-0ca5-4f41-a244-abf11272e81f",
                    "premium_value": 0,
                    "nstp_status": "approved",
                    "nstp_enabled": "Yes",
                    "reason": "nstp-case w flag did not match Yes",
                    "created_by": "broker@sunereum.cloware.in",
                    "created_by_proxy": "",
                    "stage": "quote",
                    "status": 0,
                    "author": "broker@sunereum.cloware.in",
                    "proxy": "",
                    "ip": "10.81.234.138",
                    "nstp_id": "N000000000146",
                    "qnstp_id": "N000000000146"
                },
                "qnstp_id": "N000000000146",
                "details": [
                    {
                        "nstp_details_id": "ND000000000143",
                        "nstp_id": "N000000000146",
                        "uuid": "5b2ee9f7-f364-4bed-87b2-81b83aa9c50f",
                        "reason": "quotation modified, unapproved",
                        "ext_id": "",
                        "nstp_status": "",
                        "status": 0,
                        "created_by": "broker@sunereum.cloware.in",
                        "assigned_to": "",
                        "proxy": "",
                        "author": "broker@sunereum.cloware.in",
                        "ip": "10.81.234.138",
                        "c_ts": "2025-11-10 13:05:13",
                        "u_ts": "2025-11-10 13:05:13.659979"
                    }
                ]
            },
            "qnstp_id": "N000000000146",
            "proposal": {
                "proposal_id": "",
                "data": {}
            },
            "payment": {
                "payment_id": "",
                "data": {}
            },
            "policy": {
                "policy_id": "P000000000131",
                "product_id": "M000000000004",
                "wf_id": 7,
                "product_group_id": "PG000000000001",
                "par_product_id": "M000000000001",
                "quote_id": "Q000000000131",
                "proposal_id": "",
                "discount_id": "",
                "document_id": "DT000000000129",
                "nstp_id": "",
                "payment_id": "",
                "covernote_id": "",
                "inspect_id": "",
                "cart_id": "",
                "uuid": "217aa681-6bc0-4e61-b544-48c184d116ec",
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
                "created_by": "broker@sunereum.cloware.in",
                "created_by_proxy": "",
                "assigned_to": "broker@sunereum.cloware.in",
                "proxy": "",
                "author": "broker@sunereum.cloware.in",
                "ip": "10.81.234.138",
                "c_ts": "2025-11-10 13:05:13",
                "u_ts": "2025-11-10 13:05:13.410381",
                "data": {}
            },
            "stage_status": [
                {
                    "policy_id": "P000000000131",
                    "stage": "document",
                    "stage_index": 1,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": null,
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.341872"
                },
                {
                    "policy_id": "P000000000131",
                    "stage": "payment",
                    "stage_index": 6,
                    "status": "",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": null,
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.341872"
                },
                {
                    "policy_id": "P000000000131",
                    "stage": "policy",
                    "stage_index": 7,
                    "status": "",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": null,
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.341872"
                },
                {
                    "policy_id": "P000000000131",
                    "stage": "proposal",
                    "stage_index": 3,
                    "status": "",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": null,
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.341872"
                },
                {
                    "policy_id": "P000000000131",
                    "stage": "qnstp",
                    "stage_index": 2,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": null,
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.341872"
                },
                {
                    "policy_id": "P000000000131",
                    "stage": "quote",
                    "stage_index": 0,
                    "status": "inprogress",
                    "proxy": "",
                    "author": "broker@sunereum.cloware.in",
                    "ip": null,
                    "c_ts": "2025-11-10 13:05:13",
                    "u_ts": "2025-11-10 13:05:13.341872"
                }
            ],
            "stages": {
                "document": "inprogress",
                "payment": "",
                "policy": "",
                "proposal": "",
                "qnstp": "inprogress",
                "quote": "inprogress"
            },
            "errors": []
        }
    ]
}
 `

This endpoint is essential for initiating the insurance quoting process and will return all relevant details needed for further processing or user interaction.