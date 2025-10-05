### Stride
A threat modeling framework used to categorize security threats into six types: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege

```mermaid
flowchart LR
    subgraph Spoofing
        S1["Stolen credentials"] --> S2["MFA, device fingerprinting, rate limits"]
    end

    subgraph Tampering
        T1["Manipulated JWT / request"] --> T2["Signed tokens, server-side validation"]
    end

    subgraph Repudiation
        R1["Missing auth audit trail"] --> R2["Immutable logs, token events"]
    end

    subgraph InfoDisclosure
        I1["Tokens intercepted over network"] --> I2["TLS, secure cookie flags, never log tokens"]
    end

    subgraph DoS
        D1["Flooding auth endpoints"] --> D2["Rate limiting, WAF, autoscaling"]
    end

    subgraph Elevation
        E1["Token scope abuse"] --> E2["Enforce scope checks & RBAC"]
    end
