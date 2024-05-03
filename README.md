[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/ciscotee/CiscoSecureEndpoint-ExclusionList)
# Cisco Secure Endpoint Exclusion List Workflow
The Workflow will list exclusion lists of Cisco Secure Endpoint for validating and review.
The Exclusion API in Cisco Secure Endpoint avaialble on API [v3](https://developer.cisco.com/docs/secure-endpoint/introduction/)

The Workflow work together with sub workflow (Atomics) "XDR generate Token" that you need to import after import the workflow.
The exclusion information will list and update into environment table "CiscoSecureEndpoint_Exclusion_Table" in variable.

## Requirements
  ### Authentication [More Details](https://developer.cisco.com/docs/secure-endpoint/authentication/#authentication) This will use on number 12 in Installation
  > [!IMPORTANT]
  >  -  Integrate Cisco Secure Endpoint with Cisco XDR (SecureX)
  >  -  Register Cisco XDR API Client
  >        - Click the Admnistration tab and choose API Clients in the navigation pane.
  >        - Click Generate API Client button, Enter a client name and select scope. (Note: The Secure Endpoint API will work with any of the selected Scopes.)
  >        - The Client ID and Client Password are generated (Noted: The Client Password cannot be recovered, Please store securely.

## Installation
  1. Browse to your Cisco XDR, click the **Automate** and choose **Workflows**.
  2. Click on **Import Workflow**.
  3. Navigate **Import From**, click on **Browse**
  4. Copy [CiscoSecureEndpoint-ExclusionList.json](https://github.com/ciscotee/CiscoSecureEndpoint-ExclusionList/blob/main/CiscoSecureEndpoint-ExclusionList.json) and paste the content inside of the text window.
  5. Click on **Import**. You will get a warning about *missing sub work-flows*, however please click **Continue**. (Sub work-flow will import later).
  6. You will see workflow impored and show *Import completed*
  7. Click **View Workflow** you will see "2 Invalid Actions"
  8. Select activity **"XDR Generate Access Token"**, click **"Import Sub-Workflow"**
  9. Navigate **Import From**, click on **Browse**
  10. Copy [XDR-generate-access-token.json](https://github.com/ciscotee/CiscoSecureEndpoint-ExclusionList/blob/main/Atomics/XDR-generate-access-token.json) and paste the content inside of the text window.
  11. Click on **Import**. You will get a warning, however please click on **Update** to get everything sorted.
  12. Update **Credentials** you get from Cisco XDR (Reference In Requirement), click **Import**
  13. The workflow ready to validate, click "Validate" button.
  14. Import workflow and sub workflow create following, please validate.
      - ### **Target** Navigate to **Automate** and choose **Targets**
            "Secure_Endpoint_V3" *HTTP Endpoint* Target Type
            "CTR_For_Access_Token" *HTTP Endpoint* Target Type
      - ### **Variable** Navigate to **Automate** and choose **Variables**
            "CiscoSecureEndpoint_Exclusion_Table" *Table* Data Type
            "Secure_Endpoint_OrgID" *String* Data Type
      - ### **Account Keys** Navigate to **Automate** and choose **Account Keys**
            "CTR_Credentials_Basic"
     
## Usage
  - Update target region "Secure_Endpoint_V3"
    - North America:  api.amp.cisco.com
    - APJC:           api.apjc.amp.cisco.com
    - Europe:         api.eu.amp.cisco.com
  - Update Target "CTR_For_Access_Token" on your Cisco XDR region
    - North America:  visibility.amp.cisco.com
    - APJC:           visibility.apjc.amp.cisco.com
    - Europe:         visibility.eu.amp.cisco.com
  - Open workflow then click **"Run"**
  - After running completed, you will get Exclusion list details in Variable Table. Navigate **Automate**, click on **Variables** "CiscoSecureEndpoint_Exclusion_Table" 
  

## Workflow Steps
  - Generate Access Token communication between Cisco XDR and Cisco Secure Endpoint.
  - Validate Organization ID and update to environment variable "Secure_Endpoint_OrgID".
  - List Exclusion Set, transform, and load to Table.
  - List Exclusion Details refer from Set details, transform, and load to Table for reference.

## Notes
Get benefits of Exclusion Details available on Cisco XDR to validate or comparision as data in table.
