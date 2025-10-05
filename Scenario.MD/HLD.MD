### High Level Design
This shows the main components: clients, an auth plane for login and token handling, an API/service plane for user data, and an observability layer that collects logs and feeds alerts. The API Gateway and WAF protect the service plane.



```mermaid
graph LR
  subgraph Client
    UA[User App / Browser]
  end
  subgraph Edge
    GW[API Gateway]
    WAF[WAF/Rate Limiter]
  end
  subgraph AuthPlane
    AS[Auth Service]
    IDB[Identity DB]
    TokenSvc[Token Revocation Service]
  end
  subgraph ServicePlane
    API[Instagram API]
    Storage[User Data Store]
  end
  subgraph Observability
    Logs[Logging & Monitoring]
    SIEM[SIEM / Alerts]
  end

  UA --> AS
  AS --> IDB
  AS --> TokenSvc
  UA --> GW
  GW --> WAF
  GW --> API
  API --> Storage
  AS --> Logs
  GW --> Logs
  API --> Logs
  Logs --> SIEM
