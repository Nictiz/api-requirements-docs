# Notational Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://datatracker.ietf.org/doc/rfc2119/).

## Abbreviations used in this specification

The following abbreviations are used in this specification:

| Abbreviation | Description                                                                                                                                                                                           |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| API          | Application Programming Interface: used to allow two or more applications to 'talk to each other'                                                                                                     |
| BSON         | Binary JSON: an optimized version of JSON                                                                                                                                                             |
| CDA          | Clinical Document Architecture: an HL7 standard                                                                                                                                                       |
| CORBA        | Common Object Request Broker Architecture: a standard defined by the Object Management Group (OMG) that enables software components to communicate over a network                                     |
| DCOM         | Distributed Component Object Model: a Microsoft technology that allows Microsoft 'COM components' to communicate over a network                                                                       |
| DEFLATE      | A standard for data compression                                                                                                                                                                       |
| EHR          | Electronic Health Record                                                                                                                                                                              |
| FHIR         | Fast Healthcare Interoperability Resources: an HL7 standard                                                                                                                                           |
| FSA          | 'Fully standardized API' level of standardization                                                                                                                                                     |
| GDPR         | General Data Protection Regulation: European privacy law                                                                                                                                              |
| GraphQL      | A query language for APIs                                                                                                                                                                             |
| gRPC         | A remote procedure call framework that leverages the HTTP/2 protocol                                                                                                                                  |
| GZIP         | A standard for data compression                                                                                                                                                                       |
| HIE          | Health Information Exchange                                                                                                                                                                           |
| HTTP         | Hyper Text Transfer Protocol: the protocol that fuels the internet                                                                                                                                    |
| IETF         | Internet Engineering Taskforce: the organization that creates standards for the internet                                                                                                              |
| IHE          | Integrating the Healthcare Enterprise: a worldwide organization for improving system interoperability in healthcare                                                                                   |
| JSON         | JavaScript Serialized Object Notation: a standard for formatting data                                                                                                                                 |
| LZ4          | A standard for data compression                                                                                                                                                                       |
| MedMij       | Dutch standard for exchanging health data between Personal Health Record systems and healthcare provider systems                                                                                      |
| NEN          | Royal Netherlands Standardization Institute                                                                                                                                                           |
| NHS          | National Health Service: government funded national health services in the UK                                                                                                                         |
| NUTS         | A Dutch foundation that develops technical standards for Health Information Exchange                                                                                                                  |
| OA           | 'Open API' level of standardization                                                                                                                                                                   |
| OASIS        | Organization for the Advancement of Structured Information Standards: an international consortium that promotes the adoption of open standards in computing                                           |
| OAuth        | A standard/framework for authorization                                                                                                                                                                |
| OIDC         | OpenID Connect: a standard for authentication                                                                                                                                                         |
| PACS         | Picture Archiving and Communication System                                                                                                                                                            |
| RFC          | Request For Comments: a purely technical document published by the Internet Engineering Taskforce (IETF) or other standardization organizations. An RFC can be informational, or it can be a standard |
| SDK          | Software Development Kit                                                                                                                                                                              |
| SemVer       | Semantic Versioning: a specification for versioning                                                                                                                                                   |
| SOAP         | Simple Object Access Protocol: a remote procedure call framework on top of HTTP                                                                                                                       |
| TLS          | Transport Layer Security: a standard used to secure electronic communications                                                                                                                         |
| TSA          | 'Technically standardized API' level of standardization                                                                                                                                               |
| TSV          | Taskforce Samen Vooruit: a collaboration of vendors that develops and promotes Health Information Exchange standards for Dutch healthcare                                                             |
| URI          | Uniform Resource Identifier: a unique sequence of characters that identifies a logical or physical resource used by web technologies                                                                  |
| Wabvpz       | Wet Aanvullende Bepalingen Verwerking Persoonsgegevens in de Zorg: a Dutch law that contains additional privacy regulations for the electronic exchange of healthcare data                            |
| WGBO         | Wet op de Geneeskundige Behandel Overeenkomst: a Dutch law that regulates the relationship between patients and care providers                                                                        |
| WS-Security  | A set of standards for web service security                                                                                                                                                           |
| XDS          | Cross Enterprise Document Exchange: an IHE integration profile                                                                                                                                        |
| ZIB          | Zorg Informatie Bouwsteen: the Dutch version of Health and Care Information Models (HCIM)                                                                                                             |

## Requirement identification

Requirements have unique and permanent numbers. In the event of requirements being deprecated or restructured, they are
removed from the list. Therefore, gaps in the sequence can occur. New requirements will always get a new and higher
number. When the new requirement supersedes an existing requirement, this will be referenced in the new requirement by
adding a header "Supersedes:".

## Requirement status

Requirement status is described using the key words "Draft", "Final", "Superseded" and "Deprecated". These key words are
to be interpreted as follows:

- **Draft**: The requirement is a suggestion and is yet to be approved by key stakeholders.
- **Final**: The requirement is approved by key stakeholders and is to be used for conformity assessment.
- **Superseded**: The requirement has a known better alternative, but the requirement itself is not going away.
- **Deprecated**: The requirement is no longer to be used for conformity assessment.

## Versioning of this specification

This specification follows the [Semantic Version 2.0.0](https://semver.org/) (SemVer) specification for versioning. This
means that:

- This specification has a version consisting of three parts: MAJOR.MINOR.PATCH
- The MAJOR number is at least incremented each time requirements are added or changed in such a way that API
  specifications, API implementations or API deployments that complied with the previous MAJOR version of this
  specification, don't comply with the latest version
- The MINOR number is at least incremented each time requirements are added or changed in such a way that API
  specifications, API implementations and API deployments that complied with the previous MINOR version of this
  specification, still comply with the new version
- The PATCH number is incremented each time textual changes occur that have no influence on the actual meaning of the
  requirements in this specification