# Health Information Standards compliance

## IS001: In order to be fully standardized, an API specification MUST be approved by an authoritative body

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | FSA           |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

## IS002: In order to be fully standardized, an API implementation MUST be approved by an authoritative body during a formal testing and qualification process

An API implementation is fully standardized when it is approved by a national standardization organization, or by the
national branch of an international standardization organization. Approval is given only as the result of a formal test
or qualification process. Proof must be provided for any compliance claim made by the API server developer.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | FSA                  |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

## IS003: All API input and output data SHOULD comply with ZIB specifications

If no ZIB specification is available that governs the contents of certain API input or output but the input or output
data represents general health and care concept, the API specifier **MAY** submit a ZIB change request to the
[Nictiz ZIB centre](https://nictiz.nl/wat-we-doen/activiteiten/zibs/).

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | FSA           |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **IS003.001**: API input data, such as parameters and post data, **SHOULD** comply with ZIB specifications where
  applicable
    - Applicable refers to input or output data that represents general health and care concepts.
- **IS003.002**: API output data, such as resources, documents or procedure results **SHOULD** comply with ZIB
  specifications where applicable