### DataFlow
User devices sends login requests to the Auth Service which checks credentials and issues tokens. API calls carry tokens through an API Gateway to the resource servers, and every step writes events to logs for detection.


```mermaid 
flowchart TD
  User[User App / Browser] -->|Login Request| Auth[Auth Service]
  Auth -->|Check creds| DB[Identity DB]
  Auth -->|Issue tokens| Gateway[API Gateway]
  User -->|API Request (Bearer Token)| Gateway
  Gateway -->|Forward if valid| API[Instagram API]
  API -->|Read/Write| Storage[User Data Store]
  API -->|Write logs| Logs[Logging & Monitoring]
