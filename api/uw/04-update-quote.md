### API Endpoint: update Quote

This endpoint allows users to update a quote based on the provided parameters. It is primarily used for updating premium in the context of insurance.

#### Request Format

- **Method**: POST
    
- **URL**: `{{base_url}}/api/v1/quote`
    
- **Content-Type**: application/json
    

#### Request Body

This document outlines the fields present in the quote/policy JSON object, providing a description of each field and its expected data type.

The request body must be in JSON format and should include the following fields:

Get quote id from last quote api response.

- `quote_id` (string) (System Generated): The identifier for the quote.
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
- `construction_type` (string): The type of construction of the insured property.
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
- `__finalize` (number) (System Generated): An internal flag indicating if the process should finalize.
- `wf_id` (string) (Constant): The workflow identifier.
- `premium_value` (number) (System Generated): The initial calculated premium value.
- `company_loss_cost_multiplier` (string): Company loss cost multiplier.
- `rr_limit` (string): Re-Rater limit.
- `rr_deductible` (string): Re-Rater deductible.
- `rr_amt_of_insurance` (string): Re-Rater amount of insurance.
- `rr_claim_multiplier` (string): Re-Rater claim multiplier.
- `rr_broler_fees` (number): Re-Rater broker fees.
- `territory` (number): The territory code.
- `eq_rate_group` (number): Earthquake rate group.
- `susceptibility_code` (string): Susceptibility code.
- `which_set_of_loss_costs_to_be_used_toggle` (string): Toggle indicating which set of loss costs is to be used.
- `equipment_risk_level` (string): The risk level of the equipment.
- `age_of_eqpt` (string): The age range of the equipment.
- `wind_zone` (string): The wind zone classification.
- `ice_zone` (string): The ice zone classification.
- `flood_zone` (string): The flood zone classification.
- `flood_epossure` (string): The flood exposure level.
- `fire_construction_factor` (number): Factor based on fire construction.
- `class_code` (string): The class code for the property.

**Example Request Body**:

``` json
{
    "quote_id":"Q000000000126",
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
    "construction_type": "Frame",
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
     "company_loss_cost_multiplier": "1",
    "rr_limit": "150000",
    "rr_deductible": "6000",
    "rr_amt_of_insurance": "1.55",
    "rr_claim_multiplier": "3",
    "rr_broler_fees": 0.2,
    "territory": 141,
    "eq_rate_group": 2,
    "susceptibility_code": "A",
    "which_set_of_loss_costs_to_be_used_toggle": "Ordinary Class basis",
    "equipment_risk_level": "Medium",
    "age_of_eqpt": "greater than 25 years",
    "wind_zone": "Zone 2",
    "ice_zone": "Zone 3",
    "flood_zone": "Zone A, V, and D",
    "flood_epossure": "High",
    "fire_construction_factor": 1,
    "class_code": "30500"
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
            "qnstp_case": "Yes",
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
            "assigned_to": "uw@sunerum.cloware.in",
            "proxy": "",
            "author": "broker@sunereum.cloware.in",
            "ip": "10.81.234.138",
            "c_ts": "2025-11-10 13:05:13",
            "u_ts": "2025-11-10 13:05:27.384598",
            "assigned_by": "uw@sunerum.cloware.in",
            "assigned_at": "2025-11-10 13:05:44",
            "data": {},
            "quote": {
                "quote_id": "Q000000000131",
                "wf_id": 7,
                "uuid": "ae363b61-09df-4788-a2b5-e03b511bb0c0",
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
                "premium_value": 3461.01,
                "total_tax": 0,
                "nstp_enabled": "",
                "qnstp_case": "Yes",
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
                "author": "uw@sunerum.cloware.in",
                "ip": "10.81.234.138",
                "c_ts": "2025-11-10 13:05:13",
                "u_ts": "2025-11-10 13:05:47.924354",
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
                    "product_name": "R & R Rater",
                    "product_desc": "R & R Rater",
                    "product_group_id": "PG000000000001",
                    "par_product_id": "M000000000001",
                    "wf_id": "7",
                    "premium_value": 3461.01,
                    "combo_type": "",
                    "product_group_name": "All LOB",
                    "product_group_code": "ALOB",
                    "catalog": [],
                    "policywordings": [],
                    "policy_id": "P000000000131",
                    "construction_type": "Frame",
                    "territory": 141,
                    "eq_rate_group": 2,
                    "susceptibility_code": "A",
                    "which_set_of_loss_costs_to_be_used_toggle": "Ordinary Class basis",
                    "equipment_risk_level": "Medium",
                    "age_of_eqpt": "greater than 25 years",
                    "wind_zone": "Zone 2",
                    "ice_zone": "Zone 3",
                    "flood_zone": "Zone A, V, and D",
                    "flood_epossure": "High",
                    "fire_construction_factor": 1,
                    "dispersion_factor": 1,
                    "ques1": "No",
                    "ques2": "No",
                    "ques3": "No",
                    "ques4": "No",
                    "ques5": "No",
                    "ques6": "No",
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
                    "uuid": "ae363b61-09df-4788-a2b5-e03b511bb0c0",
                    "author": "uw@sunerum.cloware.in",
                    "proxy": "",
                    "ip": "10.81.234.138",
                    "quote_id": "Q000000000131",
                    "premium_calc_html_version": 16,
                    "proposal_form_html_version": 16,
                    "premium_calc_js_version": 16,
                    "proposal_form_js_version": 16,
                    "f_premium_value": " $3,461.01 ",
                    "nstp_flag": "Yes",
                    "ar_basic_coverage_lc": 1924.48,
                    "f_ar_basic_coverage_lc": " $1,924.48 ",
                    "ar_special_perils_lc": 73.24,
                    "f_ar_special_perils_lc": " $73.24 ",
                    "ar_extended_coverage_lc": 1465.35,
                    "f_ar_extended_coverage_lc": " $1,465.35 ",
                    "broad_peril_lc": 57.07,
                    "f_broad_peril_lc": " $57.07 ",
                    "total_commercial_property_lc": 3520.14,
                    "f_total_commercial_property_lc": " $3,520.14 ",
                    "earthquake_rate": 1242,
                    "f_earthquake_rate": " $1,242.00 ",
                    "flood_coverage_rate": 2468.1,
                    "f_flood_coverage_rate": " $2,468.10 ",
                    "total_all_risk_property_premium": 7230.24,
                    "f_total_all_risk_property_premium": " $7,230.24 ",
                    "rr_basic_coverage_lc": 1383.4,
                    "f_rr_basic_coverage_lc": " $1,383.40 ",
                    "rr_special_perils_lc": 79.55,
                    "f_rr_special_perils_lc": " $79.55 ",
                    "rr_extended_coverage_lc": 1391.77,
                    "f_rr_extended_coverage_lc": " $1,391.77 ",
                    "rr_broad_peril_lc": 61.98,
                    "f_rr_broad_peril_lc": " $61.98 ",
                    "rr_total_commercial_property_lc": 2916.69,
                    "f_rr_total_commercial_property_lc": " $2,916.69 ",
                    "rr_earthquake_rate": 129.6,
                    "f_rr_earthquake_rate": " $129.60 ",
                    "rr_flood_coverage_rate": 414.72,
                    "f_rr_flood_coverage_rate": " $414.72 ",
                    "basic_coverage_mix": 0.1283,
                    "f_basic_coverage_mix": " 0.13 ",
                    "special_perils_mix": 0.0049,
                    "f_special_perils_mix": " 0.00 ",
                    "extended_coverage_mix": 0.0977,
                    "f_extended_coverage_mix": " 0.10 ",
                    "broad_perils_mix": 0.0038,
                    "f_broad_perils_mix": " 0.00 ",
                    "totoal_cp_mix": 0.2347,
                    "f_totoal_cp_mix": " 0.23 ",
                    "eq_rate_mix": 0.0828,
                    "f_eq_rate_mix": " 0.08 ",
                    "flood_coverage_mix": 0.1645,
                    "f_flood_coverage_mix": " 0.16 ",
                    "total_all_risk_property_mix": 0.482,
                    "f_total_all_risk_property_mix": " 0.48 ",
                    "rr_basic_coverage_mix": 0.9223,
                    "f_rr_basic_coverage_mix": " 0.92 ",
                    "rr_special_perils_mix": 0.053,
                    "f_rr_special_perils_mix": " 0.05 ",
                    "rr_extended_coverage_mix": 0.9278,
                    "f_rr_extended_coverage_mix": " 0.93 ",
                    "rr_broad_perils_mix": 0.0413,
                    "f_rr_broad_perils_mix": " 0.04 ",
                    "rr_total_cp_mix": 1.9445,
                    "f_rr_total_cp_mix": " 1.94 ",
                    "rr_earthquake_mix": 0.0864,
                    "f_rr_earthquake_mix": " 0.09 ",
                    "rr_flood_coverage_mix": 0.2765,
                    "f_rr_flood_coverage_mix": " 0.28 ",
                    "rr_pemium_mix": 2.3073,
                    "f_rr_pemium_mix": " 2.31 ",
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
                            1465.35,
                            "",
                            0.0977
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
                            3520.14,
                            "",
                            0.2347
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
                            7230.24,
                            "",
                            0.482
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
                            1391.77,
                            "",
                            0.9278
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
                            2916.69,
                            "",
                            1.9445
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
                            "Total R&R Premium (incl. admin and broker fees)",
                            3461.01,
                            "",
                            2.3073
                        ]
                    ],
                    "age_of_equipment": 1.25,
                    "f_age_of_equipment": "1.25",
                    "all_other_deductible_factor": 0.55,
                    "base_coverage_lc": 1924.4848218750005,
                    "f_base_coverage_lc": " $1,924.48 ",
                    "bi_and_extra_expense_rate_factor": 0.63,
                    "f_bi_and_extra_expense_rate_factor": "0.63",
                    "bi_base_loss_cost": 0.9459450000000001,
                    "f_bi_base_loss_cost": " $0.95 ",
                    "bi_deductible_factor": 0.72,
                    "f_bi_deductible_factor": "0.72",
                    "bi_lc": 1137.86223285924,
                    "f_bi_lc": " $1,137.86 ",
                    "broad_peril_base_lc": 0.017,
                    "f_broad_peril_base_lc": " $0.02 ",
                    "broad_peril_base_loss_cost": 0.371,
                    "f_broad_peril_base_loss_cost": " $0.37 ",
                    "broad_peril_loss_cost": 57.06632250000001,
                    "f_broad_peril_loss_cost": " $57.07 ",
                    "broad_peril_time_element_lc": 0.013,
                    "f_broad_peril_time_element_lc": " $0.01 ",
                    "broker_fees": 692.2029474000001,
                    "f_broker_fees": " $692.20 ",
                    "burglary_protection_factor": 0.9,
                    "f_burglary_protection_factor": "0.90",
                    "coinsurance_factor": 0.9,
                    "f_coinsurance_factor": "0.90",
                    "contents_amount_of_insurance": 0.621,
                    "f_contents_amount_of_insurance": "0.62",
                    "contents_amount_of_insurance_broadspecial": 0.411,
                    "f_contents_amount_of_insurance_broadspecial": "0.41",
                    "contents_amount_of_insurance_extended_coverage": 0.47,
                    "f_contents_amount_of_insurance_extended_coverage": "0.47",
                    "debit_credit_1": 0,
                    "f_debit_credit_1": "0%",
                    "debit_credit_2": 0,
                    "f_debit_credit_2": "0%",
                    "debit_credit_3": 0,
                    "f_debit_credit_3": "0%",
                    "debit_credit_4": 0,
                    "f_debit_credit_4": "0%",
                    "debit_credit_5": 0,
                    "f_debit_credit_5": "0%",
                    "debit_credit_6": 0,
                    "f_debit_credit_6": "0%",
                    "eei_breakdown_deductible_factor": 0.64,
                    "f_eei_breakdown_deductible_factor": "0.640",
                    "eq_deductible_factor": 0.92,
                    "f_eq_deductible_factor": "0.92",
                    "eq_prem": 1242.0000000000002,
                    "f_eq_prem": " $1,242.00 ",
                    "eqbase_prem": 0.1,
                    "f_eqbase_prem": " $0.10 ",
                    "equipment_breakdown_loss_cost": 4.3776,
                    "f_equipment_breakdown_loss_cost": " $4.38 ",
                    "equipment_breakdown_rate": 0.01,
                    "f_equipment_breakdown_rate": " $0.01 ",
                    "equipment_modification_factor": 0.76,
                    "f_equipment_modification_factor": "0.76",
                    "expediting_expense_factor": 0.9,
                    "f_expediting_expense_factor": "0.90",
                    "extended_coverage_lc": 1465.3460250000003,
                    "f_extended_coverage_lc": " $1,465.35 ",
                    "fire_protection_class": "Protected",
                    "flood_cover_prem": 2468.1024,
                    "f_flood_cover_prem": " $2,468.10 ",
                    "flood_deductible_factor": 0.92,
                    "f_flood_deductible_factor": "0.92",
                    "floodbase_prem": 0.32,
                    "f_floodbase_prem": " $0.32 ",
                    "ice_zone_factor": 1.1,
                    "f_ice_zone_factor": "1.10",
                    "individual_risk_modification_factor": 1,
                    "f_individual_risk_modification_factor": " 1.00 ",
                    "maximum_period_of_indemnity": 2.03,
                    "f_maximum_period_of_indemnity": "2.03",
                    "monthly_period_of_indemnity": 1.84,
                    "f_monthly_period_of_indemnity": "1.84",
                    "panel_risk_factor": 1,
                    "f_panel_risk_factor": "1.00",
                    "rr_base_coverage_lc": 1383.3977850000003,
                    "f_rr_base_coverage_lc": " $1,383.40 ",
                    "rr_broadperil_lc": 61.98152400000001,
                    "f_rr_broadperil_lc": " $61.98 ",
                    "rr_eq_prem": 129.60000000000002,
                    "f_rr_eq_prem": " $129.60 ",
                    "rr_ex_cov_lc": 1391.7669480000004,
                    "f_rr_ex_cov_lc": " $1,391.77 ",
                    "rr_flood_cov_prem": 414.72,
                    "f_rr_flood_cov_prem": " $414.72 ",
                    "rr_spl_perils_lc": 79.54848000000001,
                    "f_rr_spl_perils_lc": " $79.55 ",
                    "rr_total_commlprop_lc": 2916.6947370000007,
                    "f_rr_total_commlprop_lc": " $2,916.69 ",
                    "soft_cost__extra_expense_deductible_factor": 0.766,
                    "f_soft_cost__extra_expense_deductible_factor": "0.766",
                    "soft_cost__extra_expenses_base_premium": 93.069,
                    "f_soft_cost__extra_expenses_base_premium": " $93.07 ",
                    "soft_cost_and_extra_expense_base_rate": 0.243,
                    "f_soft_cost_and_extra_expense_base_rate": " $0.24 ",
                    "special_peril_base_lc": 0.024,
                    "f_special_peril_base_lc": " $0.02 ",
                    "special_peril_time_element_lc": 0.023,
                    "f_special_peril_time_element_lc": " $0.02 ",
                    "special_perils_lc": 73.2402,
                    "f_special_perils_lc": " $73.24 ",
                    "time_element_factor": 0.7918000000000001,
                    "f_time_element_factor": "0.79",
                    "total_com_prop_lc": 3520.137369375001,
                    "f_total_com_prop_lc": " $3,520.14 ",
                    "total_equipment_breakdown_premium": 97.4466,
                    "f_total_equipment_breakdown_premium": " $97.45 ",
                    "total_lc": 4657.999602234241,
                    "f_total_lc": " $4,658.00 ",
                    "total_prem_with_br_Fees": 4153.2176844000005,
                    "f_total_prem_with_br_Fees": " $4,153.22 ",
                    "total_premium_d137": 8465.548602234241,
                    "f_total_premium_d137": " $8,465.55 ",
                    "waiting_period_factor": 0.95,
                    "f_waiting_period_factor": "0.95",
                    "wind_zone_factor": 1.3,
                    "f_wind_zone_factor": "1.30",
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
                    "total_amount": "3461.01",
                    "nstp_enabled": "",
                    "error_count": 0,
                    "policy_start_time": null,
                    "submission_priority": "",
                    "company_loss_cost_multiplier": "1",
                    "rr_limit": "150000",
                    "rr_deductible": "6000",
                    "rr_amt_of_insurance": "1.55",
                    "rr_claim_multiplier": "3",
                    "rr_broler_fees": 0.2,
                    "class_code": "30500"
                },
                "assigned_to": "uw@sunerum.cloware.in",
                "assigned_by": "uw@sunerum.cloware.in"
            },
            "document": {
                "document_id": "DT000000000129",
                "proposal_id": "",
                "policy_id": "P000000000131",
                "quote_id": "Q000000000131",
                "product_id": "M000000000004",
                "uuid": "8e626ad1-f234-43ad-82c1-7347abeab71a",
                "quote_no": "",
                "ready_state": 1,
                "status_desc": "{\"Existing all-risk insurance policy\":\"not-uploaded\",\"As-built engineering drawings\":\"not-uploaded\",\"Active O&M contract\":\"uploaded\",\"Loss runs from the site\":\"uploaded\"}",
                "status": 0,
                "created_by": "broker@sunereum.cloware.in",
                "assigned_to": "broker@sunereum.cloware.in",
                "proxy": "",
                "author": "broker@sunereum.cloware.in",
                "ip": "10.81.234.138",
                "c_ts": "2025-11-10 13:05:13",
                "u_ts": "2025-11-10 13:05:23.616899",
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
                "details": [
                    {
                        "document_details_id": "DX000000000156",
                        "document_id": "DT000000000129",
                        "document_type": "Active O&M contract",
                        "document_desc": "",
                        "document_size": 96456,
                        "name": "0516000010.pdf",
                        "uuid": "24f9758b-c188-4558-9918-74f7158ead8c",
                        "verified_by": "",
                        "verified_on": null,
                        "status": 0,
                        "created_by": "broker@sunereum.cloware.in",
                        "assigned_to": "",
                        "proxy": "",
                        "author": "broker@sunereum.cloware.in",
                        "ip": "10.81.234.138",
                        "c_ts": "2025-11-10 13:05:18",
                        "u_ts": "2025-11-10 13:05:18.816449",
                        "data": {
                            "document_id": "DT000000000129",
                            "document_type": "Active O&M contract",
                            "document_desc": "",
                            "document_size": 96456,
                            "name": "0516000010.pdf",
                            "uuid": "24f9758b-c188-4558-9918-74f7158ead8c",
                            "status": 0,
                            "author": "broker@sunereum.cloware.in",
                            "proxy": "",
                            "ip": "10.81.234.138",
                            "document_details_id": "DX000000000156"
                        }
                    },
                    {
                        "document_details_id": "DX000000000157",
                        "document_id": "DT000000000129",
                        "document_type": "Loss runs from the site",
                        "document_desc": "",
                        "document_size": 96456,
                        "name": "0516000010.pdf",
                        "uuid": "a0383b6f-aabb-4dfb-bbf2-3cce0b18f2f5",
                        "verified_by": "",
                        "verified_on": null,
                        "status": 0,
                        "created_by": "broker@sunereum.cloware.in",
                        "assigned_to": "",
                        "proxy": "",
                        "author": "broker@sunereum.cloware.in",
                        "ip": "10.81.234.138",
                        "c_ts": "2025-11-10 13:05:23",
                        "u_ts": "2025-11-10 13:05:23.240170",
                        "data": {
                            "document_id": "DT000000000129",
                            "document_type": "Loss runs from the site",
                            "document_desc": "",
                            "document_size": 96456,
                            "name": "0516000010.pdf",
                            "uuid": "a0383b6f-aabb-4dfb-bbf2-3cce0b18f2f5",
                            "status": 0,
                            "author": "broker@sunereum.cloware.in",
                            "proxy": "",
                            "ip": "10.81.234.138",
                            "document_details_id": "DX000000000157"
                        }
                    }
                ]
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
                "qnstp_case": "Yes",
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
                "u_ts": "2025-11-10 13:05:27.384598",
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

### Notes

Ensure that all required parameters are included in the request body to avoid errors.

The response may contain additional nested objects and arrays that provide comprehensive details about the quote and its associated data.

Users should handle the response appropriately, especially when processing the data array for further actions or displays.
