# API onboarding

## OB001: All API onboarding policies, criteria and procedures MUST be documented

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **OB001.001**: API documentation **MUST** include details of the onboarding process, including criteria and policies
  for onboarding approval and disapproval
- **OB001.002**: When the onboarding process requires a review of the client software and/or API client developer
  organization, the documentation **MUST** include details on the review process

## OB002: API onboarding SHOULD be an online self-service process

To speed up the onboarding process.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **OB002.001**: An online service **SHOULD** be used to submit all the information required to onboard the API client
  developer and/or client system

## OB003: API onboarding MAY require a review of the client system and API client developer organization

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **OB003.001**: The API onboarding process **MAY** include a review of the client system and of the organizations that
  develop and/or deploy the API client
- **OB003.002**: An API server deployer **MAY** require an external review of the API client software, such as a
  security review, as part of the API onboarding procedure
- **OB003.003**: An API server deployer **MAY** require external certification of the Quality Management System (QMS)
  and/or Information Security Management System (ISMS) used by organizations that develop and/or deploy the API client
  as part of the API onboarding procedure

## OB004: When API onboarding requires the API client developer to provide information on the client system and/or client developer organization, the API server deployer MUST provide an Information Disclosure Statement

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **OB004.001**: The Information Disclosure Statement **MUST** explicitly state what information is considered
  confidential and what information is NOT considered confidential
- **OB004.002**: The Information Disclosure Statement **MUST** explicitly state what information is permanently
  destroyed, and what information is not, after offboarding
- **OB004.003**: The Information Disclosure Statement **MUST** explicitly state to which other parties information is
  supplied and for what purpose
- **OB004.004**: The Information Disclosure Statement **MUST** explicitly state any restrictions on the time period that
  the statement is considered in effect

## OB005: The API server deployer MUST provide a procedure for offboarding an API client and/or organization responsible for developing and/or deploying an API client

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **OB005.001**: After offboarding, the API server deployer **MUST** remove any public (published) statements that
  indicate active onboarding by the API client and/or API client organization
- **OB005.002**: The API server deployer **MAY** store information that was previously submitted as part of the API
  onboarding process for an unlimited period of time, even after API offboarding

## OB006: All API offboarding policies, criteria and procedures MUST be documented

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **OB006.001**: API documentation **MUST** include details of the offboarding process, including criteria and policies
  for offboarding, initiated by the API server deployer