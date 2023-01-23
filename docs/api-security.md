# API security

## Generic

### SC001: API specifications MUST comply with Dutch NCSC guidelines for web applications

The Dutch governmental organization NCSC (National Cyber Security Centre) has specified
[IT Security Guidelines for Web Applications](https://www.ncsc.nl/documenten/publicaties/2019/mei/01/ict-beveiligingsrichtlijnen-voor-webapplicaties)
(Dutch). The API specifications **MUST** comply with these guidelines.

Compliance check will be limited to a confirmation by the specifier.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC002: API implementations MUST comply with Dutch NCSC guidelines for web applications

The Dutch governmental organization NCSC (National Cyber Security Centre) has specified
[IT Security Guidelines for Web Applications](https://www.ncsc.nl/documenten/publicaties/2019/mei/01/ict-beveiligingsrichtlijnen-voor-webapplicaties)
(Dutch). The API implementations **MUST** comply with these guidelines.

Compliance check will be limited to a confirmation by the server developer.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### SC003: API deployments MUST comply with Dutch NCSC guidelines for web applications

The Dutch governmental organization NCSC (National Cyber Security Centre) has specified
[IT Security Guidelines for Web Applications](https://www.ncsc.nl/documenten/publicaties/2019/mei/01/ict-beveiligingsrichtlijnen-voor-webapplicaties)
(Dutch). The API deployments **MUST** comply with these guidelines.

Compliance check will be limited to a confirmation by the server deployer.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### SC004: API deployments MUST comply with Dutch NCSC guidelines for Transport Layer Security

The Dutch governmental organization NCSC (National Cyber Security Centre) has specified
[IT Security Guidelines for Transport Layer Security (TLS)](https://english.ncsc.nl/publications/publications/2021/january/19/it-security-guidelines-for-transport-layer-security-2.1).
The API deployments **MUST** comply with these guidelines.

Compliance check will be limited to a confirmation by the server deployer.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

#### Sub-requirements

- **SC004.001**: The status of used TLS versions, algorithms, key size & choice of groups and options **SHOULD** at
  least be Sufficient
    - The secure configuration of TLS is important to secure network connections. TLS has secure and less secure
      settings. Legacy software does not always support the most secure settings. Use Good settings when possible and
      complement these with Sufficient settings to support legacy software. Do you need to support a lot of legacy
      software? Then use a broad palette of Sufficient settings and complement it with Good settings where possible. Use
      Phase out settings only whilst you have a further need for client compatibility and set clear criteria for their
      deprecation. Do not use Insufficient settings.

### SC005: An API MUST provide audit logging conforming to NEN 7513

The audit logging should conform to what is described in [NEN 7513](https://www.nen.nl/nen-7513-2018-nl-245399), at
least the content matches to what is described in the same NEN 7513.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### SC006: Specifications for 'System APIs' MUST use authentication and authorization models that are not specific to a use case or (type of) client or user

To ensure the disconnection between System APIs and other types of APIs, the authentication and authorization models
used by System APIs cannot be specific to a use case or (type of) client or user.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC007: APIs MUST use fully standardized models for identification and authentication

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | FSA           |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC008: All tokens used for client authentication MUST be signed using asymmetrical encryption

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC009: When generic services/functions are nationally prescribed for use, APIs MUST use these generic services/functions

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

#### Examples

Examples of generic services/functions could be:

- Patient Consent
- Addressing
- Authorization models

## SOAP

### SC-S001: APIs SHOULD use WS-Security to ensure message confidentiality and integrity for adding security tokens

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC-S002: APIs SHOULD use the SAML Token Security Model

SAML is commonly used in SOAP APIs.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

## RESTful

### SC-R001: APIs MUST comply with RFC 7523 or its successor for client authentication and for requesting OAuth 2 access tokens

[RFC 7523](https://datatracker.ietf.org/doc/rfc7523/) describes the JSON Web Token (JWT) Profile for OAuth 2.0 Client
Authentication and Authorization Grants.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC-R002: APIs SHOULD use OpenID Connect to achieve Single-Sign-On when requesting OAuth access tokens

As far as existing regulations allow.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### SC-R003: JWT tokens used for client authentication and authorization grants MUST comply with RFC 7515 and RFC 7518, or its successors

[RFC 7515](https://datatracker.ietf.org/doc/rfc7515/) describes the JSON Web Signature (JWS), a data structure
representing a digitally signed or MACed (Message Authentication Codes) message.

[RFC 7518](https://datatracker.ietf.org/doc/rfc7518/) describes the JSON Web Algorithms (JWA).

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |