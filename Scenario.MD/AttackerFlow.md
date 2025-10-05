### Attacker Flow
An attacker first gets user credentials (e.g., by phishing) then logs into the Auth Service to obtain a token. They use that token to call the API and read or exfiltrate user data while monitoring logs looks for anomalies.



flowchart LR
  Attacker[Attacker] -->|1. Phishing / Credential Leak| Victim[User Account]
  Victim -->|2. Use stolen creds| AuthService[Auth Service]
  Attacker -->|3. Exploit Auth| AuthService
  AuthService -->|4. Issue token| Token[Access Token]
  Attacker -->|5. Use token| API[Instagram API]
  API -->|6. Access data| Data[User Data]
  API -->|7. Unusual requests| Monitoring[Monitoring / Logs]
