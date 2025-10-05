### Mitre ATT&CK



| Threat Scenario                  | MITRE ATT&CK Technique (ID)      | Why it matches (one sentence)                                  |
|---------------------------------|---------------------------------|----------------------------------------------------------------|
| Credential stuffing / valid login | T1078 (Valid Accounts)          | Attackers use valid credentials to access accounts.           |
| Brute-force login attempts        | T1110 (Brute Force)             | Repeated attempts to guess passwords.                         |
| Token theft from client storage   | T1530 / T1552 (Local Data / Unsecured creds) | Tokens in local storage can be stolen by malware or XSS.      |
| Token replay / session hijack     | T1550.003 (Application Access Token) | Reusing valid tokens to access services.                       |
| Data exfiltration via API         | T1041 (Exfiltration over C2)    | API used to pull large amounts of user data.                  |
