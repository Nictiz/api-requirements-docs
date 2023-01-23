# API testability

## TS001: Public test tooling MUST be freely available for test purposes

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **TS001.001**: An API server deployer **MUST** provide test tooling which allows API client developers and API client
  deployers to test their solutions without affecting production environments
- **TS001.002**: Test tooling **MAY** be supplied and maintained by API server developers
- **TS001.003**: Test tooling and data exposed by test tooling **MUST** mimic real API usage
    - Both online and offline tools are accepted.
- **TS001.004**: If online test tooling is supplied, the API server deployer **MUST** specify what are the Service Level
  Agreements for the availability and response times of the test tooling
- **TS001.005**: Test tooling **MUST NOT** expose confidential data, including but not limited to, patient data
- **TS001.006**: Test tooling **MUST** be freely available and accessible via a public website
    - Free registration to access the test tooling is accepted.
- **TS001.007**: Test tooling **MAY** be subject to specific onboarding procedures and policies if these policies comply
  with onboarding requirements in this specification