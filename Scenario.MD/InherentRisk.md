### Inherent Risk Assessment 



```mermaid
classDiagram
    class AuthService {
        Threat: Credential stuffing
        Likelihood: High
        Impact: High
        InherentRisk: High
        Notes: Many users share passwords
    }

    class TokenHandling {
        Threat: Token theft / reuse
        Likelihood: Medium
        Impact: High
        InherentRisk: High
        Notes: Tokens in local storage vulnerable
    }

    class APIData {
        Threat: Mass exfiltration via API
        Likelihood: Medium
        Impact: High
        InherentRisk: High
        Notes: Rate limiting reduces risk
    }

    class Logging {
        Threat: Incomplete logs
        Likelihood: Medium
        Impact: Medium
        InherentRisk: Medium
        Notes: Impacts detection capability
    }

    AuthService --> TokenHandling : affects
    TokenHandling --> APIData : exposes
    APIData --> Logging : logged by
