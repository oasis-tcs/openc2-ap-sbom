
![OASIS Logo](http://docs.oasis-open.org/templates/OASISLogo-v3.0.png)

-------

# OpenC2 Actuator Profile for Software Bill of Materials Retrieval Version 1.0

## WIP for WD for Committee Specification Draft 01

## 25 May 2023

&nbsp;

<!-- URI list start (commented out except during publication by OASIS TC Admin)

#### This stage:
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/csd01/ap-sbom-v1.0-csd01.md (Authoritative) \
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/csd01/ap-sbom-v1.0-csd01.html \
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/csd01/ap-sbom-v1.0-csd01.pdf

#### Previous stage:
N/A

#### Latest stage:
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/ap-sbom-v1.0.md (Authoritative) \
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/ap-sbom-v1.0.html \
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/ap-sbom-v1.0.pdf

URI list end (commented out except during publication by OASIS TC Admin) -->

#### Technical Committee:
[OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/)

#### CoChairs:
- Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](https://www.sfractal.com/)
- Michael Rosa (mjrosa@cyber.nsa.gov), [National Security Agency](https://www.nsa.gov/)

#### Editor:
Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/)

#### Additional artifacts:
This prose specification is one component of a Work Product that also includes:
* JADN schemas: 
   - list file names once we have them
* Other parts (list titles and/or file names)
* `(Note: Any normative computer language definitions that are part of the Work Product, such as XML instances, schemas and Java(TM) code, including fragments of such, must be (a) well formed and valid, (b) provided in separate plain text files, (c) referenced from the Work Product; and (d) where any definition in these separate files disagrees with the definition found in the specification, the definition in the separate file prevails. Remove this note before submitting for publication.)`

#### Related work:
This specification is related to:
* _Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.
* _Open Command and Control (OpenC2) Architecture Specification Version 1.0_. Edited by Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2arch/v1.0/oc2arch-v1.0.html
* _Specification for JSON Abstract Data Notation (JADN) Version 1.0_. Edited by David Kemp. Latest stage: https://docs.oasis-open.org/openc2/jadn/v1.0/cs01/jadn-v1.0-cs01.html

#### Abstract:
Open Command and Control (OpenC2) is a concise and extensible language to enable the command and control of cyber defense components, subsystems and/or systems in a manner that is agnostic of the underlying products, technologies, transport mechanisms or other aspects of the implementation. Software Bill of Materials (SBoM) is an emerging set of standards for identifying and listing software components, information about those components, and supply chain relationships between them. This profile defines the Actions, Targets, Specifiers and Options that are consistent with the version 1.0 of the OpenC2 Language Specification ([OpenC2-Lang-v1.0]) in the context of Software Bill of Materials retrieval.

#### Status:
This document was last revised or approved by the OASIS Open Command and Control (OpenC2) TC on the above date. The level of approval is also listed above. Check the "Latest stage" location noted above for possible later revisions of this document. Any other numbered Versions and other technical work produced by the Technical Committee (TC) are listed at https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=openc2#technical.

TC members should send comments on this specification to the TC's email list. Others should send comments to the TC's public comment list, after subscribing to it by following the instructions at the "[Send A Comment](https://www.oasis-open.org/committees/comments/index.php?wg_abbrev=)" button on the TC's web page at https://www.oasis-open.org/committees/openc2/.

This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the OASIS IPR Policy, the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page (https://www.oasis-open.org/committees/openc2/ipr.php).

Note that any machine-readable content ([Computer Language Definitions](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsCompLang)) declared Normative for this Work Product is provided in separate plain text files. In the event of a discrepancy between any such plain text file and display content in the Work Product's prose narrative document(s), the content in the separate plain text file prevails.

#### Key words:
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in BCP 14 [[RFC2119](#rfc2119)] and [[RFC8174](#rfc8174)] when, and only when, they appear in all capitals, as shown here.

#### Citation format:
When referencing this specification the following citation format should be used:

**[AP-SBOM-v1.0]**

_OpenC2 Actuator Profile for Software Bill of Materials Retrieval Version 1.0_. Edited by Duncan Sparrell. 19 August 2021. OASIS Committee Specification Draft 01. https://docs.oasis-open.org/openc2/ap-sbom/v1.0/csd01/ap-sbom-v1.0-csd01.html. Latest stage: https://docs.oasis-open.org/openc2/ap-sbom/v1.0/ap-sbom-v1.0.html.

#### Notices
Copyright © OASIS Open 2023. All Rights Reserved.

Distributed under the terms of the OASIS [IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr).

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs.

For complete copyright information please see the full Notices section in an Appendix below.

-------

# Table of Contents
[[TOC will be inserted here]]

-------
# Agreements in Principle
Editor's Placeholder:

This section is for agreements-in-principle
that actual text needs to added once
(1) move to new template complete and
(2) actual text put in right places and agreed to.

## split into 2 Commands
The SBOM AP must handle the following conditions:

- "one" SBOM available in one format in one serialization
- multiple SBOMs available (eg one for application, one for container application runs in)
- multiple formats available (eg CycloneDX, SPDX, SWID) 
    + {strike out SWID}
- multiple serializations available - now including JSON
    + {only json for now}
- multiple versions of application (eg SBOM for before patch and for after patch)
- multiple versions of SBOM (eg SBOM updated with new information even though application itself didn't change)
- SBOMs may be present on device (and hence returnable with another query command) or SBOMs may be elsewhere (eg a URI)
    + allow for multiple answers

There are more choices than when the AP was first conceived so
a proposal to change a different approach was discussed and approved in prinicple
The current draft contains a single query that asks
for a single sbom
qualified by prioritized list of preferred format/serializations
(and no JSON serializations were available at that time).

Proposal accepted to split into two queries:
(1) querying what SBOMs available where
    + allow for multiple answers
    + no filtering for now
(2) query to return a specific SBOM in a specific format in a specific serialization
    + only json for now

Proposal (to be discussed):
A distinction will be made between the SBOM AP and the PAC AP:
* SBOM AP will be for SBOMs resident on the device (or links to those SBOMs) FOR THE SOFTWARE ON THAT DEVICE
* PAC AP will be for SBOMs resident in the PAC (or links to those SBOMs) FOR SOFTWARE ON OTHER DEVICES

This allows simplification for SBOM AP and obviates the need for filtering on the sbom-list query.
I.e. the SBOM AP will always return all SBOMs to the sbom-list query.
This will remove Q3, Q4, and Q5 that were previously in Appendix E 
because they all contain filters more appropriate for PAC AP.
Commands in examples were simplified as well.

Examples implementing the above changes are now available in Appendix E.

-------

# 1 Introduction

<!-- All text is normative unless otherwise labeled -->


Here is a customized command line which will generate HTML from this markdown file (named openc2-file.md):

pandoc -f gfm -t html openc2-file.md -c styles/markdown-styles-v1.7.3.css --toc --toc-depth=5 -s -o openc2-file.html --metadata title="Title of Specification Version 1.0"

OASIS staff are currently using pandoc 2.6 from https://github.com/jgm/pandoc/releases/tag/2.6.

This also requires the presence of a .css file containing the HTML styles (like styles/markdown-styles-v1.7.3.css).

Note this command generates a Table of Contents (TOC) in HTML which is located at the top of the HTML document, and which requires additional editing in order to be published in the expected OASIS style. This editing will be handled by OASIS staff during publication.
A TC may use other ways to generate HTML from markdown, which may generate a TOC in a different way.

## 1.1 Changes from earlier versions

<!-- Optional section -->

## 1.2 Glossary

<!-- Optional section with suggested subsections -->

### 1.2.1 Definitions of terms

_This section is normative._

* **Action**: The task or activity to be performed (e.g., 'deny').
* **Actuator**: The function performed by the Consumer that executes the Command (e.g., 'Stateless Packet Filtering').
* **Argument**: A property of a Command that provides additional information on how to perform the Command, such as date/time, periodicity, duration, etc.
* **Command**: A Message defined by an Action-Target pair that is sent from a Producer and received by a Consumer.
* **Consumer**: A managed device / application that receives Commands. Note that a single device / application can have both Consumer and Producer capabilities.
* **Message**: A content- and transport-independent set of elements conveyed between Consumers and Producers.
* **Producer**: A manager application that sends Commands.
* **Response**: A Message from a Consumer to a Producer acknowledging a Command or returning the requested resources or status to a previously received Command.
* **Specifier**: A property or field that identifies a Target or Actuator to some level of precision.
* **Target**: The object of the Action, i.e., the Action is performed on the Target (e.g., IP Address).

### 1.2.2 Acronyms and abbreviations
_This section is non-normative_

| Term | Expansion |
|:---|:---|
| IPR | Intellectual Property Rights |
| JADN | JSON Abstract Data Notation |
| JSON | JavaScript Object Notation |
| OASIS | Organization for the Advancement of Structured Information Standards |
| RFC | Request for Comment |
| TC | Technical Committee |
| URI | Uniform Resource Identifier |

### 1.2.3 Document conventions

# 2. OpenC2 Language Binding

_This section is normative_

** Editor's Note ** add text here to reference JADN files and refer back to (or better yet, repeat) JADN wins statement earlier in this doc

This section defines the set of Actions, Targets, Specifiers, and Arguments that are meaningful in the context of an SBOM. This section also describes the appropriate format for the status and properties of a Response frame. This section is organized into three major subsections; Command Components, Response Components and Commands.

Extensions to the Language Specification are defined in accordance with [[OpenC2-Lang-v1.0]](#openc2-lang-v10), Section 3.1.5, where:

1. The unique name of the SBOM schema is `oasis-open.org/openc2/v1.0/ap-sbom`
2. The namespace identifier (nsid) referring to the SBOM schema is:  `sbom`
3. The definitions of and conformance requirements for these types are contained in this document

## 2.1 OpenC2 Command Components
The components of an OpenC2 Command include Actions, Targets, Actuators and associated Arguments and Specifiers. Appropriate aggregation of the components will define a Command-body that is meaningful in the context of an SBOM.

This specification identifies the applicable components of an OpenC2 Command. The components of an OpenC2 Command include:

* Action:  A subset of the Actions defined in the OpenC2 Language Specification that are meaningful in the context of a SBOM.
    * This profile SHALL NOT define Actions that are external to Version 1.0 of the [OpenC2 Language Specification](#openc2-lang-v10)
    * This profile MAY augment the definition of the Actions in the context of a SBOM
    * This profile SHALL NOT define Actions in a manner that is inconsistent with version 1.0 of the OpenC2 Language Specification
* Target:  A subset of the Targets and Target-Specifiers defined in Version 1.0 of the OpenC2 Language Specification that are meaningful in the context of SBOM and one Target (and its associated Specifier) that is defined in this specification
* Arguments:  A subset of the Arguments defined in the Language Specification and a set of Arguments defined in this specification
* Actuator:  A set of specifiers defined in this specification that are meaningful in the context of SBOM

### 2.1.1 Actions
Table 2.1.1-1 presents the OpenC2 Actions defined in version 1.0 of the Language Specification which are meaningful in the context of an SBOM. The particular Action/Target pairs that are required or are optional are presented in [Section 2.3](#23-openc2-commands).

**Table 2.1.1-1. Actions Applicable to SBOM**

**_Type: Action (Enumerated)_**

| ID | Name | Description |
| :--- | :--- | :--- |
| 3 | **query** | Initiate a request for information. Used to communicate the supported options and determine the state or settings |

### 2.1.2 Targets
Table 2.1.2-1 summarizes the Targets defined in Version 1.0 of the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) as they relate to SBOM functionality. Table 2.1.2-2 summarizes the Targets that are defined in this specification.

#### 2.1.2.1 Common Targets
Table 2.1.2-1 lists the Targets defined in the OpenC2 Language Specification that are applicable to SBOM. The particular Action/Target pairs that are required or are optional are presented in [Section 2.3](#23-openc2-commands).

**Table 2.1.2-1. Targets Applicable to SBOM**

**_Type: Target (Choice)_**

| ID | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| 9 | **features** | Features | A set of items such as Action/Target pairs, profiles versions, options that are supported by the Actuator. The Target is used with the query Action to determine an Actuator's capabilities |
| 10 | **sbom** | Sbom | Properties of a SBOM |

The semantics/ requirements as they pertain to common targets:
* fill in if we have any

#### 2.1.2.2 SBOM Targets
The list of common Targets is extended to include the additional Targets defined in this section and referenced with the SBOM namespace.

**Table 2.1.2-2. Targets Unique to SBOM**

**_Type: Target (Choice)_**

| ID | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| 1024 | **fillin** | Rule-ID | Immutable identifier assigned when a rule is created. Identifies a rule to be deleted |

update per https://github.com/oasis-tcs/openc2-usecases/tree/master/Cybercom-Plugfest/TestData/sbom

### 2.1.3 Command Arguments
Arguments provide additional precision to a Command by including information such as how, when, or where a Command is to be executed. Table 2.1.3-1 summarizes the Command Arguments defined in Version 1.0 of the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) as they relate to SBOM functionality. Table 2.1.3-2 summarizes the Command Arguments that are defined in this specification.

#### 2.1.3.1 Common Arguments
Table 2.1.3-1 lists the Command Arguments defined in the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) that are applicable to SBOM.

**Table 2.1.3-1. Command Arguments applicable to SBOM**

**_Type: Args (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 4 | **response_requested** | Response-Type | 0..1 | The type of Response required for the Action: `none`, `ack`, `status`, `complete` |

proposal to delete "none" as it doesn't make sense on either Query

#### 2.1.3.2 SBOM Arguments
The list of common Command Arguments is extended to include the additional Command Arguments defined in this section and referenced with the SBOM namespace.

**Table 2.1.3-2. Command Arguments Unique to SBOM**

**_Type: Args (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| n | **N** | N | 0..1 | need to add the sbom formats per plugfest examples |

The semantics/requirements as they relate to SBOM arguments:

* fill in about the choice of formats and list order is preference order

### 2.1.4 Actuator Specifiers
An Actuator is the entity that provides the functionality and performs the Action. The Actuator executes the Action on the Target. In the context of this profile, the Actuator is the SBOM and the presence of one or more Specifiers further refine which Actuator(s) shall execute the Action.

Table 2.1.4-1 lists the Specifiers that are applicable to the SBOM Actuator. [Annex A](#annex-a-sample-commands) provides sample Commands with the use of Specifiers.

The Actuator Specifiers defined in this document are referenced under the SBOM namespace.

**Table 2.1.4-1. SBOM Specifiers**

**_Type: Specifiers (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **hostname** | String | 0..1 | [[RFC1123]](#rfc1123) hostname (can be a domain name or IP address) for a particular device with SBOM functionality |
| 2 | **named_group** | String | 0..1 | User defined collection of devices with SBOM functionality |
| 3 | **asset_id** | String | 0..1 | Unique identifier for a particular SBOM |
| 4 | **asset_tuple** | String | 0..10 | Unique tuple identifier for a particular SBOM consisting of a list of up to 10 strings |

## 2.2 OpenC2 Response Components
Response messages originate from the Actuator as a result of a Command.

Responses associated with required Actions MUST be implemented. Implementations that include optional Actions MUST implement the RESPONSE associated with the implemented Action. Additional details regarding the Command and associated Response are captured in [Section 2.3](#23-openc2-commands). Examples are provided in [Annex A](#annex-a-sample-commands).

### 2.2.1 Common Results
Table 2.2.1-1 lists the Response Results properties defined in the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) that are applicable to SBOM.

**Table 2.2.1-1. Response Results Applicable to SBOM**

**_Type: Results (Map [1..*])_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **versions** | Version | 0..* | List of OpenC2 language versions supported by this Actuator |
| 2 | **profiles** | ArrayOf(Nsid) | 0..1 | List of profiles supported by this Actuator |
| 3 | **pairs** | Action-Targets | 0..* | List of targets applicable to each supported Action |
| 4 | **rate_limit** | Number | 0..1 | Maximum number of requests per minute supported by design or policy |

### 2.2.2 SBOM Results
The list of common Response properties is extended to include the additional Response properties defined in this section and referenced with the SBOM namespace.

**Table 2.2.2-1. SBOM Results**

**_Type: OpenC2-Response (Map)_**

| ID | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| 1024 | **fillin** | fillin | fillin |

### 2.2.3 Response Status Codes
Table 2.2.1-2 lists the Response Status Codes defined in the OpenC2 Language Specification that are applicable to SBOM.

**Table 2.2.1-2. Response Status Codes**

**_Type: Status-Code (Enumerated.ID)_**

| Value | Description |
| :--- | :--- |
| 102 | Processing. Command received but action not necessarily complete. |
| 200 | OK. |
| 400 | Bad Request. Unable to process Command, parsing error. |
| 500 | Internal Error. For "response_requested" value "complete", one of the following MAY apply:<br> * Cannot access file or path<br> * Rule number currently in use<br> * Rule not updated |
| 501 | Not implemented. For "response_requested" value "complete", one of the following MAY apply:<br> * Target not supported<br> * Option not supported<br> * Command not supported |

## 2.3 OpenC2 Commands

An OpenC2 Command consists of an Action/Target pair and associated Specifiers and Arguments. This section enumerates the allowed Commands and presents the associated Responses.

Table 2.3-1 defines the Commands that are valid in the context of the SBOM profile. An Action (the top row in Table 2.3-1) paired with a Target (the first column in Table 2.3-1) defines a valid Command. The subsequent subsections provide the property tables applicable to each OpenC2 Command.

**Table 2.3-1. Command Matrix**

|   | Allow | Deny | Query | Delete | Update |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **features** |   |   | valid |   |   |
| **sbom** |   |   | valid |   |   |

Table 2.3-2 defines the Command Arguments that are allowed for a particular Command by the SBOM profile. A Command (the top row in Table 2.3-2) paired with an Argument (the first column in Table 2.3-2) defines an allowable combination. The subsection identified at the intersection of the Command/Argument provides details applicable to each Command as influenced by the Argument.

**Table 2.3-2. Command Arguments Matrix**

|   | Allow _target_ | Deny _target_ | Query features | Delete SBOM:rule_number | Update file |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **response_requested** | [2.3.1](#231-allow) | [2.3.2](#232-deny) | [2.3.3.1](#2331-query-features) | [2.3.4.1](#2341-delete-SBOMrule_number) | [2.3.5.1](#2351-update-file) |
add stuff for sbom

### 2.3.1 Query
The valid Target type, associated Specifiers, and Options are summarized in [Section 2.3.3.1](#2331-query-features). Sample Commands are presented in [Annex A](#annex-a-sample-commands).

#### 2.3.3.1 Query features
The 'query features' Command MUST be implemented in accordance with Version 1.0 of the [[OpenC2-Lang-v1.0]](#openc2-lang-v10).

#### 2.3.3.1 Query sbom
The 'query sbom' Command MUST be implemented in accordance with fill-in-here


Refer to [Annex A](#annex-a-sample-commands) for sample Commands.

-------

# 3 Conformance statements
_This section is normative_
This section identifies the requirements for twenty-two conformance profiles as they pertain to two conformance targets. The two conformance targets are OpenC2 Producers and OpenC2 Consumers (as defined in [Section 1.8](#18-purpose-and-scope) of this specification).

## 3.1 Clauses Pertaining to the OpenC2 Producer Conformance Target
All OpenC2 Producers that are conformant to this specification MUST satisfy Conformance Clause 1 and MAY satisfy one or more of Conformance Clauses 2 through 11.

### 3.1.1 Conformance Clause 1: Baseline OpenC2 Producer
An OpenC2 Producer satisfies Baseline OpenC2 Producer conformance if:
* 3.1.1.1 **MUST** support JSON serialization of OpenC2 Commands that are syntactically valid in accordance with the property tables presented in [Section 2.1](#21-openc2-command-components)
* 3.1.1.2 All serializations **MUST** be implemented in a manner such that the serialization validates against and provides a one-to-one mapping to the property tables in [Section 2.1](#21-openc2-command-components) of this specification
* 3.1.1.3 **MUST** support the use of a Transfer Specification that is capable of delivering authenticated, ordered, lossless and uniquely identified OpenC2 messages
* 3.1.1.4 **SHOULD** support the use of one or more published OpenC2 Transfer Specifications which identify underlying transport protocols such that an authenticated, ordered, lossless, delivery of uniquely identified OpenC2 messages is provided as referenced in [Section 1](#1-introduction) of this specification
* 3.1.1.5 **MUST** be conformant with Version 1.0 of the OpenC2 Language Specification
* 3.1.1.6 **MUST** implement the 'query features' Command in accordance with the normative text provided in Version 1.0 of the OpenC2 Language Specification
* 3.1.1.7 **MUST** implement the 'response_requested' Command Argument as a valid option for any Command
* 3.1.1.8 **MUST** conform to at least one of the following conformance clauses in this specification:
   * Conformance Clause 2
   * Conformance Clause 3
   * Conformance Clause 4
   * Conformance Clause 5


## 3.2 Clauses Pertaining to the OpenC2 Consumer Conformance Target
All OpenC2 Consumers that are conformant to this specification MUST satisfy Conformance Clause 12 and MAY satisfy one or more of Conformance Clauses 13 through 22.

### 3.2.1 Conformance Clause 12: Baseline OpenC2 Consumer
An OpenC2 Consumer satisfies Baseline OpenC2 Consumer conformance if:
* 3.2.1.1 **MUST** support JSON serialization of OpenC2 Commands that are syntactically valid in accordance with the property tables presented in [Section 2.1](#21-openc2-command-components)
* 3.2.1.2 All serializations **MUST** be implemented in a manner such that the serialization validates against and provides a one-to-one mapping to the property tables in [Section 2.1](#21-openc2-command-components) of this specification
* 3.2.1.3 **MUST** support the use of a Transfer Specification that is capable of delivering authenticated, ordered, lossless and uniquely identified OpenC2 messages
* 3.2.1.4 **SHOULD** support the use of one or more published OpenC2 Transfer Specifications which identify underlying transport protocols such that an authenticated, ordered, lossless, delivery of uniquely identified OpenC2 messages is provided as referenced in [Section 1](#1-introduction) of this specification
* 3.2.1.5 **MUST** be conformant with Version 1.0 of the OpenC2 Language Specification
* 3.2.1.6 **MUST** implement the 'query features' Command in accordance with the normative text provided in version 1.0 of the OpenC2 Language Specification
* 3.2.1.7 **MUST** implement the 'response_requested' Command Argument as a valid option for any Command
    * 3.2.1.7.1 All Commands received with a 'response_requested' argument set to 'none' **MUST** process the Command and **MUST NOT** send a Response. This criteria supersedes all other normative text as it pertains to Responses
    * 3.2.1.7.2 All Commands received without the 'response_requested' argument **MUST** process the Command and Response in a manner that is consistent with "response_requested":"complete"
* 3.2.1.8 **MUST** conform to at least one of the following conformance clauses in this specification:
    * Conformance Clause 13
    * Conformance Clause 14
    * Conformance Clause 15
    * Conformance Clause 16


-------

# Appendix A. References

<!-- Required section -->

This appendix contains the normative and informative references that are used in this document.

While any hyperlinks included in this appendix were valid at the time of publication, OASIS cannot guarantee their long-term validity.

## A.1 Normative References

The following documents are referenced in such a way that some or all of their content constitutes requirements of this document.

(Reference sources:
For references to IETF RFCs, use the approved citation formats at:  
http://docs.oasis-open.org/templates/ietf-rfc-list/ietf-rfc-list.html.  
For references to W3C Recommendations, use the approved citation formats at:  
http://docs.oasis-open.org/templates/w3c-recommendations-list/w3c-recommendations-list.html.  
Remove this note before submitting for publication.)

###### [OpenC2-Lang-v1.0]
_Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html
<!--
###### [OpenC2-HTTPS-v1.0]
_Specification for Transfer of OpenC2 Messages via HTTPS Version 1.0_. Edited by David Lemire. Latest stage: http://docs.oasis-open.org/openc2/open-impl-https/v1.0/open-impl-https-v1.0.html
###### [OpenC2-SLPF-v1.0]
_Open Command and Control (OpenC2) Profile for Stateless Packet Filtering Version 1.0_. Edited by Joe Brule, Duncan Sparrell, and Alex Everett. Latest stage: http://docs.oasis-open.org/openc2/oc2slpf/v1.0/oc2slpf-v1.0.html
-->
###### [RFC2119]
Bradner, S., "Key words for use in RFCs to Indicate Requirement Levels", BCP 14, RFC 2119, DOI 10.17487/RFC2119, March 1997, http://www.rfc-editor.org/info/rfc2119.
###### [RFC8174]
Leiba, B., "Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words", BCP 14, RFC 8174, DOI 10.17487/RFC8174, May 2017, http://www.rfc-editor.org/info/rfc8174.

## A.2 Informative References

###### [RFC3552]
Rescorla, E. and B. Korver, "Guidelines for Writing RFC Text on Security Considerations", BCP 72, RFC 3552, DOI 10.17487/RFC3552, July 2003, https://www.rfc-editor.org/info/rfc3552.

-------

# Appendix B. Safety, Security and Privacy Considerations

<!-- Optional section -->

(Note: OASIS strongly recommends that Technical Committees consider issues that might affect safety, security, privacy, and/or data protection in implementations of their specification and document them for implementers and adopters. For some purposes, you may find it required, e.g. if you apply for IANA registration.

While it may not be immediately obvious how your specification might make systems vulnerable to attack, most specifications, because they involve communications between systems, message formats, or system settings, open potential channels for exploit. For example, IETF [[RFC3552](#rfc3552)] lists “eavesdropping, replay, message insertion, deletion, modification, and man-in-the-middle” as well as potential denial of service attacks as threats that must be considered and, if appropriate, addressed in IETF RFCs.

In addition to considering and describing foreseeable risks, this section should include guidance on how implementers and adopters can protect against these risks.

We encourage editors and TC members concerned with this subject to read _Guidelines for Writing RFC Text on Security Considerations_, IETF [[RFC3552](#rfc3552)], for more information.

Remove this note before submitting for publication.)

-------

# Appendix C. Acknowledgments

<!-- Required section -->

Note: A Work Product approved by the TC must include a list of people who participated in the development of the Work Product. This is generally done by collecting the list of names in this appendix. This list shall be initially compiled by the Chair, and any Member of the TC may add or remove their names from the list by request. Remove this note before submitting for publication.

## C.1 Special Thanks

<!-- This is an optional subsection to call out contributions from TC members. If a TC wants to thank non-TC members then they should avoid using the term "contribution" and instead thank them for their "expertise" or "assistance". -->

Substantial contributions to this document from the following individuals are gratefully acknowledged:

* David Kemp, NSA
* David Lemire, HII
* Duncan Sparrell, sFractal Consulting
* Mike Rosa, NSA


## C.2 Participants

<!-- A TC can determine who they list here, however, TC Observers must not be listed. It is common practice for TCs to list everyone that was part of the TC during the creation of the document, but this is ultimately a TC decision on who they want to list and not list. -->

The following individuals have participated in the creation of this specification and are gratefully acknowledged:

**OpenC2 TC Members:**

| First Name | Last Name | Company |
| :--- | :--- | :--- |
Philippe | Alman | Something Networks
Alex | Amirnovman | Company B
Kris | Anderman | Mini Micro
Darren | Anstman | Big Networks

-------

# Appendix D. Revision History

<!-- Optional section -->

| Revision | Date | Editor | Changes Made |
| :--- | :--- | :--- | :--- |
| specname-v1.0-wd01 | yyyy-mm-dd | Editor Name | Initial working draft |

-------

# Appendix E. Command Examples
This appendix contains example commands and example responses
to/from a device with SBOM AP functionality.

The following subsections contain:
Q1. query requesting list of sboms
    - device is "simple" device
      - ie not a device running different software stacks in different cpu's
R1a. response to Q1
    - when only one sbom
    - sbom on device
R1b.  response to Q1
    - when several sboms
    - sboms only on device
R1c.  response to Q1
    - when only one sbom
    - sbom only a URI elsewhere
R1d.  response to Q1
    - when only one sbom
    - sbom in several places
Q2.  query requesting specific sbom after response R1a
R2a.  response to Q2


### Example Q1: query requesting list of sboms:
``` json
{
  "action": "query",
  "target": "sbom_list"
}
```
### Example R1a: response to query 1 when only one sbom and sbom is on device
``` json
{
  "status": 200,
  "results": {
    "sbom_list": [{
            "id": ["twinkly_maha",
                    "58156134-5547-4e4a-968f-88a33cfafc2c"],
            "filename": "twinkly_maha.0.9.0-cyclonedx-sbom.1.0.0.json",
            "location": "localhost",
            "version": "1.0.0",
            "format": ["cyclonedx", "1.4"],
            "serialization": "json",
            "supplier": ["sFractal.com",
                    "1783512b-1cae-4cfa-a183-3e30408bbc14"],
            "created_at": "build",
            "author": ["Duncan at sFractal",
                    "4d50d859-a5f7-45fa-9935-77b294aa445a"],
            "timestamp": "2021-10-12T07:20:50.52Z",
            "notes": "this SBOM has known unknowns"
            }
    ]
    }
}
```

### R1b.  response to Q1 when several sboms, sboms only on device
note some fields optional and weren't available in this example (and saves page space).
Ie fields might not be returned due to filter request, but they also might not be returned
because they just weren't there.

``` json
{
  "status": 200,
  "results": {
    "sbom_list": [{
            "id": ["twinkly_maha",
                    "58156134-5547-4e4a-968f-88a33cfafc2c"],
            "filename": "twinkly_maha.0.9.0-cyclonedx-sbom.1.0.0.json",
            "location": "localhost",
            "version": "1.0.0",
            "format": ["cyclonedx", "1.4"],
            "serialization": "json"
        },
        {
            "id": ["twinkly_maha",
                    "564694c2-3b10-488a-9e50-5b2d0a2443d1"],
            "filename": "twinkly_maha.0.9.0-spdx-sbom.1.0.0.json",
            "location": "localhost",
            "version": "1.0.0",
            "format": ["spdx", "2.3"],
            "serialization": "json"
        },
        {
            "id": ["debian.buster_slim",
                    "caff7de1-c0a8-4913-a4c6-8993db102428"],
            "filename": "debian.buster_slim-cyclonedx-bom.json",
            "location": "localhost",
            "version": "1.0.0",
            "format": ["cyclonedx", "1.4"],
            "serialization": "json"
        }
    ]
    }
}
```

### R1c.  response to Q1 when only one sbom is is only a URI elsewhere
``` json
{
  "status": 200,
  "results": {
    "sbom_list": [{
            "id": ["twinkly_maha",
                    "b1d09495-3d12-4642-a111-3ed733a3c6a9"],
            "filename": "twinkly_maha.0.9.0-cyclonedx-sbom.1.0.0.json",
            "location": "https://twinklymaha.example.com/.well-known/sbom/twinkly_maha.0.9.0-cyclonedx-sbom.1.0.0.json",
            "version": "1.0.0",
            "format": ["cyclonedx", "1.4"],
            "serialization": "json"
            }
    ]
    }
}
```

### R1d.  response to Q1 when only one sbom, in several places
``` json
{
  "status": 200,
  "results": {
    "sbom_list": [{
            "id": ["twinkly_maha",
                    "b1d09495-3d12-4642-a111-3ed733a3c6a9"],
            "filename": "twinkly_maha.0.9.0-cyclonedx-sbom.1.0.0.json",
            "location": "https://twinklymaha.example.com/.well-known/sbom/twinkly_maha.0.9.0-cyclonedx-sbom.1.0.0.json",
            "version": "1.0.0",
            "format": ["cyclonedx", "1.4"],
            "serialization": "json"
        },
        {
            "id": ["twinkly_maha",
                    "564694c2-3b10-488a-9e50-5b2d0a2443d1"],
            "filename": "twinkly_maha.0.9.0-spdx-sbom.1.0.0.json",
            "location": "localhost",
            "version": "1.0.0",
            "format": ["spdx", "2.3"],
            "serialization": "json"
        }
    ]
    }
}
```

### Example Q2 - query requesting one specific sbom:
``` json
{
  "action": "query",
  "target": {
    "sbom": {
        "uuid": "58156134-5547-4e4a-968f-88a33cfafc2c"
    }
  }
}
```

### Example R2a - response to query Q2
``` json
{
  "status": 200,
  "results": {
    "sbom": {
        "need to put an valid example sbom here"
    }
  }
}
```

-------

# Appendix F. Notices

<!-- Required section. Do not modify. -->

Copyright © OASIS Open 2023. All Rights Reserved.

All capitalized terms in the following text have the meanings assigned to them in the OASIS Intellectual Property Rights Policy (the "OASIS IPR Policy"). The full [Policy](https://www.oasis-open.org/policies-guidelines/ipr) may be found at the OASIS website.

This document and translations of it may be copied and furnished to others, and derivative works that comment on or otherwise explain it or assist in its implementation may be prepared, copied, published, and distributed, in whole or in part, without restriction of any kind, provided that the above copyright notice and this section are included on all such copies and derivative works. However, this document itself may not be modified in any way, including by removing the copyright notice or references to OASIS, except as needed for the purpose of developing any document or deliverable produced by an OASIS Technical Committee (in which case the rules applicable to copyrights, as set forth in the OASIS IPR Policy, must be followed) or as required to translate it into languages other than English.

The limited permissions granted above are perpetual and will not be revoked by OASIS or its successors or assigns.

This document and the information contained herein is provided on an "AS IS" basis and OASIS DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION HEREIN WILL NOT INFRINGE ANY OWNERSHIP RIGHTS OR ANY IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.

As stated in the OASIS IPR Policy, the following three paragraphs in brackets apply to OASIS Standards Final Deliverable documents (Committee Specification, Candidate OASIS Standard, OASIS Standard, or Approved Errata).

\[OASIS requests that any OASIS Party or any other party that believes it has patent claims that would necessarily be infringed by implementations of this OASIS Standards Final Deliverable, to notify OASIS TC Administrator and provide an indication of its willingness to grant patent licenses to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this deliverable.\]

\[OASIS invites any party to contact the OASIS TC Administrator if it is aware of a claim of ownership of any patent claims that would necessarily be infringed by implementations of this OASIS Standards Final Deliverable by a patent holder that is not willing to provide a license to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this OASIS Standards Final Deliverable. OASIS may include such claims on its website, but disclaims any obligation to do so.\]

\[OASIS takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this OASIS Standards Final Deliverable or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any effort to identify any such rights. Information on OASIS' procedures with respect to rights in any document or deliverable produced by an OASIS Technical Committee can be found on the OASIS website. Copies of claims of rights made available for publication and any assurances of licenses to be made available, or the result of an attempt made to obtain a general license or permission for the use of such proprietary rights by implementers or users of this OASIS Standards Final Deliverable, can be obtained from the OASIS TC Administrator. OASIS makes no representation that any information or list of intellectual property rights will at any time be complete, or that any claims in such list are, in fact, Essential Claims.\]

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs. OASIS welcomes reference to, and implementation and use of, specifications, while reserving the right to enforce its marks against misleading uses. Please see https://www.oasis-open.org/policies-guidelines/trademark for above guidance.
