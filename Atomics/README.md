# XDR Generate Token (For Secure Endpoint API v3)
Regarding with API v3, The Secure Endpoint API requires access via an authenticated and authorized account. Only authorized accounts are able to submit requests to API operations. All operations must communicate over a secure HTTPS connection.
[Documentations](https://developer.cisco.com/docs/secure-endpoint/authentication/#authentication)

## Requirements
  - Integrate Secure Endpoint with Cisco XDR (SecureX)
  - Register Cisco XDR API Client
    - Click the Admnistration tab and choose API Clients in the navigation pane.
    - Click Generate API Client button, Enter a client name and select scope. (Note: The Secure Endpoint API will work with any of the selected Scopes.)
    - The Client ID and Client Password are generated (Noted: The Client Password cannot be recovered, Please store securely)
  - Update Account Keys "CTR_Credentials_Basic" with Client ID and Client Password
  - Update Target "CTR_For_Access_Token" on your Cisco XDR region
    - North America: visibility.amp.cisco.com
    - APJC:          visibility.apjc.amp.cisco.com
    - Europe:        visibility.eu.amp.cisco.com
