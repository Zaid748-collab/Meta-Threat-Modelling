### Inherent Risk Assessment 


| Asset / Process       | Threat Example            | Likelihood (L/M/H) | Impact (L/M/H) | Inherent Risk (L/M/H) | Notes                             |
|-----------------------|--------------------------|------------------|----------------|----------------------|----------------------------------|
| **Auth Service**      | Credential stuffing       | H                | H              | H                    | Many users share passwords        |
| **Token Handling**    | Token theft / reuse       | M                | H              | H                    | Tokens in local storage vulnerable |
| **API Data**          | Mass exfiltration via API | M                | H              | H                    | Rate limiting reduces risk        |
| **Logging**           | Incomplete logs           | M                | M              | M                    | Impacts detection capability      |
