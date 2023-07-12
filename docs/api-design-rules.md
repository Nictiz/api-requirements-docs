# API design rules

Design rules focus on the technical implementation of the APIs.

## Compliance with national API design rules

The [Dutch National API strategy](https://docs.geostandaarden.nl/api/API-Strategie/) by Geonovum contains
[design rules](https://publicatie.centrumvoorstandaarden.nl/api/adr/) that were considered when writing this chapter.
Unfortunately, these rules would exclude the use of FHIR, which is the most considered base for any RESTful transaction
in healthcare. It also focuses on the use of RESTful interfaces, while SOAP is still used for APIs as well, especially
with IHE-profiles, like XDS, XCA, etc.

## Generic

### DR001: Interfaces MUST be defined in English

Healthcare APIs are used internationally, which is why a lot are already available in English. Conforming to this will
help with uniformity and attract non-Dutch developers.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### DR002: Developers MUST only apply standard HTTP methods

The HTTP specification ([RFC 7231](https://datatracker.ietf.org/doc/html/rfc7231)) and the later introduced PATCH method
specification ([RFC 5789](https://datatracker.ietf.org/doc/html/rfc5789)) offer a set of standard methods, where every
method is designed with explicit semantics. Adhering to the HTTP specification is crucial since HTTP clients and
middleware applications rely on standardized characteristics. Therefore, resources must be retrieved or manipulated
using standard HTTP methods.

|                                 |                      |
|---------------------------------|----------------------|
| **Applicable roles**            | API server developer |
| **Standardization levels**      | TSA, FSA             |
| **Status**                      | Final                |
| **Since version**               | 1.0.0                |
| **Dutch National API strategy** | API-03               |

#### Sub-requirements

- **DR002.001**: HTTP GET method **MUST** be used to retrieve a resource representation for the given URI
    - Data is only retrieved and never modified.
- **DR002.002**: HTTP POST method **MUST** be used to create a resource
    - The receiver generates a new URI.
- **DR002.003**: HTTP PUT method **MUST** be used to create a resource with the given URI or replace (full update) a
resource when the resource already exists
- **DR002.004**: HTTP PATCH method **MUST** be used to partially update an existing resource
    - The request only contains the resource modifications instead of the full resource representation.
- **DR002.005**: HTTP DELETE method **MUST** be used to remove a resource with the given URI

| Method   | Operation     | Description                                                                                                                               |
|----------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| `GET`    | Read          | Retrieve a resource representation for the given URI. Data is only retrieved and never modified.                                          |
| `POST`   | Create        | Create a resource. The receiver generates a new URI.                                                                                      |
| `PUT`    | Create/update | Create a resource with the given URI or replace (full update) a resource when the resource already exists.                                |
| `PATCH`  | Update        | Partially updates an existing resource. The request only contains the resource modifications instead of the full resource representation. |
| `DELETE` | Delete        | Remove a resource with the given URI.                                                                                                     |

#### Examples

The following table shows some examples of the use of standard HTTP methods:

| Request              | Description                      |
|----------------------|----------------------------------|
| `GET /Patient`       | Retrieves a list of patients.    |
| `GET /Patient/12`    | Retrieves an individual patient. |
| `POST /Patient`      | Creates a new patient.           |
| `PUT /Patient/12`    | Modifies Patient #12 completely. |
| `PATCH /Patient/12`  | Modifies Patient #12 partially.  |
| `DELETE /Patient/12` | Deletes Patient #12.             |

HTTP also defines other methods, e.g., `HEAD`, `OPTIONS` and `TRACE`. For this design rule, these operations are left
out of scope.

### DR003: Developers MUST adhere to HTTP safety and idempotency semantics for operations

The HTTP protocol ([RFC 7231](https://datatracker.ietf.org/doc/html/rfc7231)) specifies whether an HTTP method should be
considered safe and/or idempotent. These characteristics are important for clients and middleware applications because
they should be considered when implementing caching and fault tolerance strategies.

Request methods are considered *safe* if their defined semantics are essentially read-only, i.e., the client does not
request, and does not expect, any state change on the origin server because of applying a safe method to a target
resource. A request method is considered *idempotent* if the intended effect on the server of multiple identical
requests with that method is the same as the effect for a single such request.

|                                 |                      |
|---------------------------------|----------------------|
| **Applicable roles**            | API server developer |
| **Standardization levels**      | TSA, FSA             |
| **Status**                      | Final                |
| **Since version**               | 1.0.0                |
| **Dutch National API strategy** | API-01               |

#### Sub-requirements

- **DR003.001**: HTTP `GET` method **MUST** behave as safe
- **DR003.002**: HTTP `GET` method **MUST** behave as idempotent
- **DR003.003**: HTTP `HEAD` method **MUST** behave as safe
- **DR003.004**: HTTP `HEAD` method **MUST** behave as idempotent
- **DR003.005**: HTTP `OPTIONS` method **MUST** behave as safe
- **DR003.006**: HTTP `OPTIONS` method **MUST** behave as idempotent
- **DR003.007**: HTTP `POST` method **MUST NOT** behave as safe
- **DR003.008**: HTTP `POST` method **MUST NOT** behave as idempotent
- **DR003.009**: HTTP `PUT` method **MUST NOT** behave as safe
- **DR003.010**: HTTP `PUT` method **MUST** behave as idempotent
- **DR003.011**: HTTP `PATCH` method **MUST NOT** behave as safe
- **DR003.012**: HTTP `PATCH` method **MUST NOT** behave as idempotent
- **DR003.013**: HTTP `DELETE` method **MUST NOT** behave as safe
- **DR003.014**: HTTP `DELETE` method **MUST** behave as idempotent

The following table describes which HTTP methods must behave as safe and/or idempotent:

| Method    | Safe | Idempotent |
|-----------|------|------------|
| `GET`     | Yes  | Yes        |
| `HEAD`    | Yes  | Yes        |
| `OPTIONS` | Yes  | Yes        |
| `POST`    | No   | No         |
| `PUT`     | No   | Yes        |
| `PATCH`   | No   | No         |
| `DELETE`  | No   | Yes        |

### DR004: Server communication MUST remain stateless

One of the key constraints of the REST architectural style is stateless communication between client and server. It
means that every request from client to server must contain all the information necessary to understand the request. The
server cannot take advantage of any stored session context on the server as it didn't memorize previous requests.
Session state must therefore reside entirely on the client.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

To properly understand this constraint, it's important to make a distinction between two distinct kinds of state:

- *Session state*: information about the interactions of an end-user with a particular client application within the
  same user session, such as the last page being viewed, the login state or form data in a multi-step registration
  process. Session state must reside entirely on the client (e.g., in the user's browser).
- *Resource state*: information that is permanently stored on the server beyond the scope of a single user session, such
  as the user's profile, a product purchase or information about a building. Resource state is persisted on the server
  and must be exchanged between client and server (in both directions) using representations as part of the request or
  response payload. This is where the term *REpresentational State Transfer (REST)* originates from.

> It's a misconception that there should be no state at all. The stateless communication constraint should be seen from
the server's point of view and states that the server should not be aware of any session state.

Stateless communication offers many advantages, including:

- *Simplicity* is increased because the server doesn't have to memorize or retrieve the session state while processing
  requests
- *Scalability* is improved because not having to incorporate the session state across multiple requests enables higher
  concurrency and performance
- *Observability* is improved since every request can be monitored or analysed in isolation without having to incorporate
  session context from other requests
- *Reliability* is improved because it simplifies the task of recovering from partial failures since the server doesn't
  have to maintain, update or communicate the session state. One failing request does not influence other requests
  (depending on the nature of the failure of course).

In the context of REST APIs, the server must not maintain or require any notion of the functionality of the client
application and the corresponding end-user interactions. To achieve full decoupling between client and server, and to
benefit from the advantages mentioned above, no session state must reside on the server. Session state must therefore
reside entirely on the client.

> The client of a REST API could be a variety of applications such as a browser application, a mobile or desktop
application or even another server serving as a backend component for another client. REST APIs should therefore be
completely client agnostic.

### DR005: Content relationship MUST be predictably implemented

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

#### Sub-requirements

- **DR005.001**: When using several content relationships within an API, adding more relationships **MUST** adhere to
  the same implementation choices
    - For example, if a child resource is already available through stacking of endpoint, another child resource must be
      made available in the same manner.

### DR006: Operations MUST be predictably implemented

An API can be made more accessible using operations.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

#### Sub-requirements

- **DR006.001**: The operations in one API **MUST** all be implemented in the same way
    - For example, if an operation is called with a prefix, the same prefix must be used for every other operation on
      the same API.

### DR007: API version MUST be accessible through the API

The version of an API can be useful in development and debugging.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | OA, TSA, FSA         |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

#### Sub-requirements

- **DR007.001**: The API version **MAY** be made accessible through the URL-path
    - For example, `/v1/api/...`
- **DR007.002**: The API version **MAY** be made accessible through a HTTP header
    - For example, in `Accept` (request) and `Content-Type` (response).
- **DR007.003**: The API version **MAY** be made accessible through a separate request
    - For example, in response to `/api/version`
- **DR007.004**: The API version **MAY** be made accessible through the API in a way not covered in this specification

### DR008: APIs MUST at least support the DEFLATE and gzip compression algorithms

The use of compression algorithms can reduce communication size. This is especially useful when transferring large data
objects. The algorithms DEFLATE and gzip are widely used in HTTP communication.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR009: APIs MUST support the use of HTTP Accept-Encoding and Content-Encoding header fields for negotiating compression

The `Accept-Encoding` and `Content-Encoding` header fields are used to negotiate the compression algorithms. The API
client will use the `Accept-Encoding` header field to communicate which compression algorithms are supported. The API
server will use the `Content-Encoding` header field to confirm which compression algorithm is used.

|                            |                                            |
|----------------------------|--------------------------------------------|
| **Applicable roles**       | API client developer, API server developer |
| **Standardization levels** | TSA, FSA                                   |
| **Status**                 | Final                                      |
| **Since version**          | 1.0.0                                      |

### DR011: JSON formatted content SHOULD comply to RFC 8259 or its successor

The design of JSON is described by IETF in [RFC 8259](https://datatracker.ietf.org/doc/rfc8259/). Any use of JSON
**SHOULD** be compliant with this RFC or its successor.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR012: When describing an API where data is being transferred to another party, the NOTIFIED PULL exchange pattern SHOULD be used rather than the PUSH exchange pattern

This way, the receiving party can decide when or how the transferred data is received and processed.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### DR013: System APIs SHOULD be designed independent of specific use cases and types of client systems or users

Making the System APIs independent of a specific use case encourages the reuse of these APIs.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR014: Process APIs SHOULD be designed to reuse System APIs

Process APIs make use of the System APIs. It is encouraged to reuse already existing System APIs.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR015: Experience APIs SHOULD be based on Process APIs

Experience APIs are by definition based on Process APIs, this **SHOULD** always be the case.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR016: System APIs SHOULD be based on the operations, messaging, or resource paradigm rather than the document paradigm

To be fully atomic the document paradigm **SHOULD** be avoided in system APIs.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

## SOAP

### DR-S001: APIs MAY use MTOM/XOP for formatting binary data

When a SOAP message contains a large binary object, it can be optimized for processing by using MTOM/XOP. APIs **MAY**
use MTOM/XOP to create a multipart MIME to link from the SOAP body to a mime part which holds the binary data.

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.0.0         |

### DR-S002: API clients MUST support MTOM/XOP formatting of binary data

Design rule DR-S001 determined that an API **MAY** use MTOM/XOP when it believes it is necessary to optimize processing
of the message. To be able to use these APIs, API clients **MUST** support MTOM/XOP as well.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API client developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

## RESTful

The REST architectural style is centred around the concept of a resource. A resource is the key abstraction of
information, where every piece of information is named by assigning a globally unique URI (Uniform Resource Identifier).
Resources describe *things*, which can vary between physical objects (e.g., a building or a person) and more abstract
concepts (e.g., a permit or an event).

### DR-R001: APIs MUST use nouns to name resources

Because resources describe things (and thus not actions), resources are referred to using nouns (instead of verbs) that
are relevant from the perspective of the user of the API.

|                                 |               |
|---------------------------------|---------------|
| **Applicable roles**            | API specifier |
| **Standardization levels**      | TSA, FSA      |
| **Status**                      | Final         |
| **Since version**               | 1.0.0         |
| **Dutch National API strategy** | API-05        |

#### Examples

A few correct examples of nouns as part of FHIR:

- Patient
- Observation
- AllergyIntolerance

### DR-R002: APIs MUST consistently use either singular nouns or plural nouns to name collection resources

Resources can be grouped into collections, which are resources in their own right and can typically be paged, sorted and
filtered. Most often all collection members have the same type, but this is not necessarily the case. A resource
describing multiple things is called a collection resource. Collection resources typically contain references to the
underlying singular resources. The path segment describing the name of the collection resource **MUST** be written using
a noun (thing) instead of a verb (action).

|                            |               |
|----------------------------|---------------|
| **Applicable roles**       | API specifier |
| **Standardization levels** | TSA, FSA      |
| **Status**                 | Final         |
| **Since version**          | 1.2.0         |

#### Examples

Example of how to collect a collection of resources in FHIR:

- `https://api.example.org/Patient`
- `https://api.example.org/Observation?code=http://loinc.org|29463-7`

Example of using plural nouns to name collection resources:

- `https://api.example.org/patients`
- `https://api.example.org/observations`

### DR-R003: APIs MUST hide irrelevant implementation details

An API should not expose implementation details of the underlying application. The primary motivation behind this design
rule is that an API design must focus on usability for the client, regardless of the implementation details under the
hood. The API, application and infrastructure need to be able to evolve independently to ease the task of maintaining
backwards compatibility for APIs during an agile development process.

|                                 |                      |
|---------------------------------|----------------------|
| **Applicable roles**            | API server developer |
| **Standardization levels**      | TSA, FSA             |
| **Status**                      | Final                |
| **Since version**               | 1.0.0                |
| **Dutch National API strategy** | API-53               |

#### Examples

A few examples of implementation details:

- The API design should not necessarily be a 1-to-1 mapping of the underlying domain or persistence model
- The API should not expose information about the technical components being used, such as development
  platforms/frameworks or database systems
- The API should offer client-friendly attribute names and values, while persisted data may contain abbreviated terms or
  serializations which might be cumbersome for consumption

### DR-R004: APIs MUST support both JSON and XML formatting

JSON and XML both have their advantages and disadvantages. API clients can focus on either standard for all their API
calls when all APIs support both. Therefore, APIs MUST support both JSON and XML formatting.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

#### Sub-requirements

- **DR-R004.001**: APIs **MUST** be able to convert consistently between JSON and XML formatting
    - Converting from one to the other and back to the first **MUST** result in the exact same resource.

### DR-R005: API clients MUST at least support JSON or XML formatting

As described in DR-R004, both JSON and XML will be supported from the APIs. API clients **MUST** therefore at least
support one of the two formats. In the end this means the focus can be on either XML or JSON for all calls to available
APIs.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API client developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR-R006: APIs MAY support BSON formatting

BSON are used to communicate JSON in a binary object. This is an innovative technology that could improve performance in
larger JSON objects. APIs **MAY** therefore support BSON formatting.

|                            |                      |
|----------------------------|----------------------|
| **Applicable roles**       | API server developer |
| **Standardization levels** | TSA, FSA             |
| **Status**                 | Final                |
| **Since version**          | 1.0.0                |

### DR-R007: APIs MUST use the Accept header for content negotiation

The HTTP header `Accept` is used to communicate which content types can be understood by the API clients.

|                            |                                            |
|----------------------------|--------------------------------------------|
| **Applicable roles**       | API server developer, API client developer |
| **Standardization levels** | TSA, FSA                                   |
| **Status**                 | Final                                      |
| **Since version**          | 1.0.0                                      |

#### Sub-requirements

- **DR-R007.001**: The API client **MUST** use the `Accept` header to communicate which content types the client is able
  to understand
- **DR-R007.002**: The API server **MUST** use the `Accept` header value to decide the response content type

### DR-R008: APIs MUST use the Content-Type header for content negotiation

The HTTP header `Content-Type` is used to communicate which content type is used in communication between client and
server.

|                            |                                            |
|----------------------------|--------------------------------------------|
| **Applicable roles**       | API server developer, API client developer |
| **Standardization levels** | TSA, FSA                                   |
| **Status**                 | Final                                      |
| **Since version**          | 1.0.0                                      |

#### Sub-requirements

- **DR-R008.001**: The API server **MUST** use the `Content-Type` header to communicate the content type
- **DR-R008.002**: The API client **MUST** use the `Content-Type` header value to decide how to process the response