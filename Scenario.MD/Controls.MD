### Controls

## Authentication controls

Enforce MFA (TOTP or push) for user logins.

Rate limit login attempts and require CAPTCHA after thresholds.

## Token controls

Use signed, short-lived access tokens and longer-lived refresh tokens.

Validate token scopes and revoke tokens on suspicious activity.

## Network & API controls

Rate limiting per IP/client and IP reputation blocking.

API Gateway validates tokens and scopes before routing.

## Monitoring & Detection

Log auth events, token issues, refresh calls, and suspicious patterns.

Alerts for multiple failed logins, token reuse from different IPs, and high-volume data requests.

## Response controls

Automatic token revocation and session invalidation for suspected compromise.

Block offending IPs and notify the user and SOC.