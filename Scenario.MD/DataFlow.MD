### DataFlow
User devices sends login requests to the Auth Service which checks credentials and issues tokens. API calls carry tokens through an API Gateway to the resource servers, and every step writes events to logs for detection.


```mermaid 
erDiagram
    USER-APP ||--o{ AUTH-SERVICE : "sends login request"
    AUTH-SERVICE ||--o{ IDENTITY-DB : "checks credentials in"
    AUTH-SERVICE ||--o{ API-GATEWAY : "issues token to"
    USER-APP ||--o{ API-GATEWAY : "sends API requests with token"
    API-GATEWAY ||--o{ INSTAGRAM-API : "forwards valid requests to"
    INSTAGRAM-API ||--o{ USER-DATA-STORE : "reads/writes data in"
    API-GATEWAY ||--o{ LOGS : "writes logs to"
    INSTAGRAM-API ||--o{ LOGS : "writes logs to"

