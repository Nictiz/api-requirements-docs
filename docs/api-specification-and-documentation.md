# API specification & documentation

## SD001: API documentation MUST be publicly and freely available

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **SD001.001**: API specification **MUST** contain enough information for a competent developer to create an API
  implementation or an API client without further information
- **SD001.002**: API specification **MAY** refer to other specifications to cover elements
- **SD001.003**: API specification **MUST** cover identification and authentication of people, organizations, and
  machines
    - This does not only apply to the technical standards and specifics used to authenticate entities but also to the
      identifying attributes that are used and how to obtain and secure them to create a network of trust.
- **SD001.004**: API specification **MUST** cover authorization/access control
    - This does not only apply to the technical standards and specifics used to authorize access to APIs, but also to
      the semantics of access tokens and requests for access tokens, such as the permitted values for permissions
      (OAuth2 scopes) and expiration requirements.
- **SD001.005**: API specification **MUST** cover protecting integrity and confidentiality
    - This applies to any specifics on protecting integrity and confidentiality at both transport and message levels,
      including specifics on the cryptographic algorithms, key distribution and PKIs used.
- **SD001.006**: API specification **MUST** cover addressing
    - This applies to specifics on addressing API endpoints and mechanisms used to distribute (updates to) addresses.
- **SD001.007**: API specification **MUST** cover content encoding
    - This applies to specifics on content encoding such as the compression algorithms used and character encoding.
- **SD001.008**: API specification **MUST** cover content formatting
    - Specifics on content formatting such as the use of MTOM/XOP and BSON but also healthcare-specific (data) formats.
- **SD001.009**: API specification **MUST** cover exchange patterns and exchange paradigms used
- **SD001.010**: API specification **MUST** cover API signature and semantics
    - All actions (methods) that are available through the API MUST be covered, as well as the legitimate data
      structures return (error) codes (the API signature), Including a full specification of all API requests and
      responses.
- **SD001.011**: API specification **MUST** cover use cases
    - How to (and how not to) use the API in specific use cases.
- **SD001.012**: API specification **MUST** cover references to other specifications
    - Most specifications reuse other specifications such as RFCs created by IETF or W3C or Dutch information standards
      created by Nictiz.
- **SD001.013**: API documentation **MUST** be freely available and accessible via a public website
- **SD001.014**: API documentation **MAY** refer to paid content published by standardization organizations
- **SD001.015**: Access to API documentation **MAY** require free registration
- **SD001.016**: API documentation **MAY** be copyright protected
- **SD001.017**: Distribution of API documentation without explicit permission of the API specifier **MAY** be
  restricted

## SD002: API documentation MUST provide examples of how to use the API

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **SD002.001**: API documentation **MUST** include examples for the most common use cases
- **SD002.002**: API documentation **MUST** clearly express the value of the API (for API client developers and API
  users) within the context of the most common use cases
- **SD002.003**: When a use case involves integration of two or more APIs, API documentation **MUST** provide examples
  of how to use these APIs in collaboration

## SD003: API documentation SHOULD provide examples of input and output data

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **SD003.001**: Documentation for all API methods **SHOULD** contain examples of input and output data, using a
  supported data format such as JSON or XML
- **SD003.002**: When the API server developer includes an SDK for easy access to the API, code samples **MUST** be
  provided for using the API through the SDK

## SD004: API documentation SHOULD include a FAQ page for API client developers

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **SD004.001**: A FAQ **SHOULD** be made available for developers that want to use the API(s)
- **SD004.002**: The FAQ **SHOULD** be written in an actual question-and-answer format
- **SD004.003**: Questions and answers **SHOULD** be written from the point of view of the API client developer
- **SD004.004**: Questions **SHOULD** include the most common problems and misconceptions that API client developers run
  into when using the API

## SD005: API documentation MAY specify cases in which API usage is not applicable

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **SD005.001**: API documentation **MAY** include cases in which API usage is not applicable or not supported
- **SD005.002**: When cases exist in which API usage is not applicable or not supported, API documentation **MUST**
  clearly state whether using the API in this way violates the API license agreement

## SD006: API server developers and deployers MAY be active on developer forums to assist API client developers and deployers with the correct usage of APIs

Using developer forums, experts can provide resolutions to common hiccups and increase participation and interest for API client developers.

|                            |                                           |
|----------------------------|-------------------------------------------|
| **Applicable roles**       | API server developer, API server deployer |
| **Standardization levels** | OA, TSA, FSA                              |
| **Status**                 | Final                                     |
| **Since version**          | 1.0.0                                     |

### Sub-requirements

- **SD006.001**: Server developers and deployers **MAY** be (are encouraged to be) active participants on relevant
  developer forums
- **SD006.002**: Solutions to problems provided through a developer forum **MAY** be provided without prejudice
- **SD006.003**: API documentation **MAY** refer to developer forums for knowledge sharing and assistance
- **SD006.004**: API server developers and deployers **MAY** provide their own developer forum

## SD007: API server developers MAY provide API client developers an SDK for easy access to deployed APIs

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### Sub-requirements

- **SD007.001**: If an SDK is provided, it **MUST** be documented to the extent that a competent developer has
  sufficient information to make use of the SDK without further information
    - Charges for using the SDK are accepted.
- **SD007.002**: If an SDK is provided, API client developers **MUST NOT** in any way be forced to use it
    - Any common coding language and/or development platform is accepted.

## SD008: API specifications SHOULD be machine readable and allow for automated code generation

Using machine-readable API specification allows for automated code generation and hence saves time and avoids errors
when writing API client code.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### Sub-requirements

- **SD008.001**: API server developers **SHOULD** provide machine-readable API specifications based on international
  standards
    - Such as OpenAPI (formerly known as Swagger) and/or FHIR StructureDefinitions/OperationDefinitions.

## SD009: API documentation SHOULD be published in English

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.2.0         |

### Sub-requirements

- **SD009.001**: API documentation **SHOULD** be available in English
- **SD009.002**: If API documentation is available in English, typical Dutch terminology and names of people and
  organizations **MUST** be written down in their original Dutch form
- **SD009.003**: If API documentation is available in English, domain concepts **MUST** be translated to their
  corresponding official English terms instead of using literal (word-for-word) translations

## SD010: When documentation claims compliance to standards, specifications, guidelines and practices, policies or law, documentation MUST provide (references to) evidence to back up these claims

Examples of evidence include official compliance certificates and statements (such as IHE integration statements and
Nictiz qualifications) and independent auditor reports (such as security audit reports).

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

## SD011: Content relationship MUST be described in API documentation

Some content cannot exist without its parent content. The API documentation must describe in which way the relationship
is managed and used.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

## SD012: API documentation MUST describe the availability and usage of operations

API operations can be extremely useful in specific use cases, describing the operations will make them even more useful.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

## SD013: API versioning policy MUST be documented

The versioning of APIs and its policy must be documented in a clear manner. Use of versioning makes developing and
debugging by API client developers easier.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

## SD014: API specifications MUST cover the rationale behind the exchange paradigm used by the API

Such as described in [Exchange paradigms](./definitions-and-scope.md#exchange-paradigms).

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | FSA           |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |