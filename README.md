# Cisco Secure Endpoint Exclusion List Workflow
The Workflow will list exclusion lists of Cisco Secure Endpoint for validating and review.
The Exclusion API in Cisco Secure Endpoint avaialble on API [v3](https://developer.cisco.com/docs/secure-endpoint/introduction/)

The Workflow work with sub workflow (Atomics) "XDR generate Token" that you need to import after import the workflow.
The exclusion information will list and update into environment table "CiscoSecureEndpoint_Exclusion_Table" in variable.

## Requirement
  - Validate subwork flow ["XDR generate Token"](https://github.com/ciscotee/CiscoSecureEndpoint-ExclusionList/tree/main/Atomics) 
  - Update target region "Secure_Endpoint_V3"
    -  North America:  api.amp.cisco.com
    -  APJC:           api.apjc.amp.cisco.com
    -  Europe:         api.eu.amp.cisco.com

## Workflow Steps
  - Generate Access Token communication between Cisco XDR and Cisco Secure Endpoint.
  - Validate Organization ID and update to environment variable "Secure_Endpoint_OrgID".
  - List Exclusion Set, transform, and load to Table.
  - List Exclusion Details refer from Set details, transform, and load to Table for reference.

## Notes
Get benefits of Exclusion Details available on Cisco XDR to validate or comparision as data in table.
