# API Lifecycle management and versioning

## LM001: API specifications MUST be marked deprecated when they are no longer recommended for use

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **LM001.001**: An API specifier **MUST** mark an API specification as deprecated (in the Dutch API library for
  healthcare) when it is no longer recommended for use
    - Specifications marked as deprecated are still supported but support may end soon.
- **LM001.002**: An API specifier **MUST** mark an API specification as deprecated for a period of at least one year,
  before it MAY be marked retired
- **LM001.003**: API server developers **SHOULD** replace the use of deprecated API specifications with newer versions
  or alternative API specifications
- **LM001.004**: API server developers **MUST** mark API implementations as deprecated (in the Dutch API library for
  healthcare) when they are based on a deprecated API specification

## LM002: API specifications MUST be marked retired when they are no longer supported

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### Sub-requirements

- **LM002.001**: An API specifier **MUST** mark an API specification as retired (in the Dutch API library for
  healthcare) when it is no longer supported
- **LM002.002**: API server developers **MUST** replace the use of retired API specifications with newer versions or
  alternative API specifications
- **LM002.003**: API server developers **MUST** mark API implementations as retired when they are based on a retired API
  specification

## LM003: API implementations MUST be marked deprecated when they are no longer recommended for use

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### Sub-requirements

- **LM003.001**: An API server developer **MUST** mark an API implementation as deprecated (in the Dutch API library for
  healthcare) when it is no longer recommended for use
    - Implementations marked as deprecated are still supported but support may end soon.
- **LM003.002**: An API server developer **MUST** mark an API implementation as deprecated for a period of at least one
  year, before it MAY be marked retired
- **LM003.003**: API server deployers **SHOULD** replace deprecated API implementations with newer versions or
  alternative API implementations
- **LM003.004**: API server deployers **MUST** mark an API deployment as deprecated (in the Dutch API library for
  healthcare) when it is based on a deprecated implementation

## LM004: API implementations MUST be marked retired when they are no longer supported

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### Sub-requirements

- **LM004.001**: An API server developer **MUST** mark an API implementation as retired (in the Dutch API library for
  healthcare) when it is no longer supported
- **LM004.002**: API server deployers **MUST** replace the use of retired API implementations with newer versions or
  alternative API implementations
- **LM004.003**: API server deployers **MUST** mark API deployments as retired (in the Dutch API library for healthcare)
  when they are based on a retired API implementation

## LM005: API deployments MUST be marked deprecated when they are no longer recommended for use

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **LM005.001**: An API server deployer **MUST** mark an API deployment as deprecated (in the Dutch API library for
  healthcare) when it is no longer recommended for use
    - Deployments marked as deprecated are still supported but support may end soon.
- **LM005.002**: An API server deployer **MUST** mark an API deployment as deprecated for a period of at least one year,
  before it MAY be marked retired
- **LM005.003**: API client developers **SHOULD** replace the use of deprecated API employments with newer versions or
  alternative API implementations

## LM006: API deployments MUST be marked retired when they are no longer supported

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API server deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **LM006.001**: An API server deployer **MUST** mark an API deployment as retired (in the Dutch API library for
  healthcare) when it is no longer supported
- **LM006.002**: API client developers **MUST** replace the use of retired API deployments with newer versions or
  alternative API deployments

## LM007: An API client MUST be designed to handle non-breaking changes

This includes at least the non-breaking changes described in
[Non-breaking changes](./definitions-and-scope.md#non-breaking-changes).

Non-breaking changes are changes that cannot be expected to break a client application. Adding optional parts to an API
is never considered a breaking change.

|                            |                     |
|----------------------------|---------------------|
| **Applicable roles**       | API client deployer |
| **Standardization levels** | OA, TSA, FSA        |
| **Status**                 | Final               |
| **Since version**          | 1.0.0               |

### Sub-requirements

- **LM007.001**: An API client **MUST** be designed to handle addition of new endpoints
- **LM007.002**: An API client **MUST** be designed to handle addition of new resources or operations to existing
  endpoints
- **LM007.003**: An API client **MUST** be designed to handle addition of new fields in responses
- **LM007.004**: An API client **MUST** be designed to handle addition of new optional request fields or parameters
- **LM007.005**: An API client **MUST** be designed to handle addition of new required request fields that have default
  values
- **LM007.006**: An API client **MUST** be designed to handle addition of optional query parameters
- **LM007.007**: An API client **MUST** be designed to handle changes to the order of fields returned within a response
- **LM007.008**: An API client **MUST** be designed to handle addition of an optional request header
- **LM007.009**: An API client **MUST** be designed to handle removal of redundant request header
- **LM007.010**: An API client **MUST** be designed to handle changes to the overall response size
- **LM007.011**: An API client **MUST** be designed to handle changes to error messages

## LM008: An API specification MUST comply with Semantic Versioning specification (SemVer) version 2.0.0

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | OA, TSA, FSA  |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |