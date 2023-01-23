# API agreements

## AG001: API Service Levels MUST be openly and freely available

With the intention to protect API client developers, API users and API client deployers from unpredictable service level
quality.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **AG001.001**: API Service Levels **MUST** be documented in the form of an agreement between API server deployer, API
  client developer and/or API client deployer
- **AG001.002**: The API server deployer **MAY** require API client developers and/or API client deployers to sign a
  Service Level Agreement before using the API
- **AG001.003**: Service Levels **MAY** be provided on a best-efforts basis
- **AG001.004**: If Service Levels are provided on a best-efforts basis, the SLA documentation **MUST** explicitly state
  relevant terms such as no liability for costs or charges incurred in the event of unavailability of the API
- **AG001.005**: Service Levels **MAY** be provided in tiers, such as free tiers without developer support and paid
  tiers that include developer support
- **AG001.006**: API Service Levels **MUST** be documented to the extent that API client developers and API client
  deployers are fully informed about the duties and responsibilities of each party involved and about the remedies or
  penalties for breaching these duties and 
- **AG001.007**: The API Service Levels **MUST** at least include a description of the service(s) provided
- **AG001.008**: The API Service Levels **MUST** at least include availability requirements, such as days and times the
  API is available and any restrictions for special days
- **AG001.009**: The API Service Levels **MUST** at least include details on planned outage and unplanned outage,
  expressed as a maximum percentage of total availability times
- **AG001.010**: The API Service Levels **MUST** at least include response time expectations, such as a percentage of
  calls that return within a given amount of time
- **AG001.011**: The API Service Levels **MUST** at least include details on technical support and support windows such
  as developer support or other technical support
- **AG001.012**: The API Service Levels **MUST** describe any restrictions on using the API
- **AG001.013**: The API Service Levels **MUST** at least include usage restrictions, such as number of calls per time
  unit or maximum call size and consequences for exceeding these restrictions
- **AG001.014**: The API Service Levels **MUST** at least include any terms and conditions regarding the use of the data
  acquired via the API, including requirements and responsibilities for secure and lawful use of data returned by the
  API such as retention and destruction policies
- **AG001.015**: The API Service Levels **MUST** at least include any restrictions on what persons or organizations are
  allowed to access the API (API access restriction policies)
- **AG001.016**: If the API server deployer provides online test tooling, Service Levels for test tooling **MUST** be
  described using the same metrics for availability, outage, usage restrictions, response times and technical support
- **AG001.017**: If the API server deployer provides offline test tooling, only details on technical support **MUST** be
  provided for the offline test tool
- **AG001.018**: The API Service Level Agreement **MUST** detail the process and restrictions for changing the agreement
  and/or service levels

## AG002: API Access Restriction Policies MUST be openly and freely available

With the intention to prevent information blocking strategies based on arbitrary access to APIs.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **AG002.001**: Any restrictions on persons or organizations to access and/or use the API **MUST** be transparent and
  documented
- **AG002.002**: The API server deployer **MUST NOT** restrict persons or organizations from using the API for reasons
  other than the documented access restriction policies
- **AG002.003**: Access Restriction Policies **MAY** include an accreditation process and review of the API client
  system, API client developer organization and/or API client deployer organization
- **AG002.004**: If an accreditation process is in place, details on how accreditation is achieved **MUST** be provided,
  including criteria for exclusion

## AG003: Data Processing Policies MUST be openly and freely available

With the intention to protect API user, API client developer and API client deployer organizations from unwanted use of
API usage data.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **AG003.001**: API server deployer Data Processing Policies **MUST** be documented
- **AG003.002**: API server deployer Data Processing Policies **MUST** include at least the details on how API usage
  will be monitored and what data will be stored as part of the monitoring process, such as IP addresses of the API
  deployer or API user
    - This requirement concerns monitoring data that is not personal data. Requirements for the processing of personal
      data is the concern of the European [General Data Protection Regulation](https://gdpr.eu/) (GDPR) and therefore is
      not part of this specification.
- **AG003.003**: API server deployers **MAY** document details on processing personal data

## AG004: When an API server deployer charges API client developers and/or API client deployers for using the API in a production environment, any fees MUST be predictable and openly and freely available

With the intention to prevent information blocking strategies based on non-transparent pricing.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **AG004.001**: Fees **MUST** be predictable, meaning that the API client developer and the API client deployer have
  enough pricing information to predict the cost of API usage for at least two years after signing the agreement