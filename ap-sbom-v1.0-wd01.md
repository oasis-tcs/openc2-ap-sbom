
![OASIS Logo](http://docs.oasis-open.org/templates/OASISLogo-v2.0.jpg)
-------

# Open Command and Control (OpenC2) Profile for Software Bill of Materials Retrieval Version 1.0

## Committee Specification Draft 01 /<br>Public Review Draft 01

## 13 May 2020

#### Technical Committee:
[OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/)

#### Chairs:
Joe Brule (jmbrule@radium.ncsc.mil), [National Security Agency](https://www.nsa.gov/) \
Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/)

#### Editor:
Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/)

#### Additional artifacts:
None

#### Related work:
This specification is related to:
* _Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.
* _Community-Drafted Documents on Software Bill of Materials_. https://www.ntia.gov/sbom
* Software Package Data eXchange (SPDX®). https://spdx.github.io/spdx-spec/.
* Software Identification (SWID). ISO/IEC 19770-2:2015. https://webstore.ansi.org/RecordDetail.aspx?sku=ISO%2fIEC+19770-2%3a2015.
* CycloneDX. https://cyclonedx.org/

#### Abstract:
Open Command and Control (OpenC2) is a concise and extensible language to enable the command and control of cyber defense components, subsystems and/or systems in a manner that is agnostic of the underlying products, technologies, transport mechanisms or other aspects of the implementation. Software Bill of Materials (SBoM) is an emerging set of standards for identifying and listing software components, information about those components, and supply chain relationships between them. This profile defines the Actions, Targets, Specifiers and Options that are consistent with the version 1.0 of the OpenC2 Language Specification ([OpenC2-Lang-v1.0]) in the context of Software Bill of Materials retrieval.

#### Status:
_Editor's Note - This is a working Draft_

This document was last revised or approved by the OASIS Open Command and Control (OpenC2) TC on the above date. The level of approval is also listed above. Check the "Latest stage" location noted above for possible later revisions of this document. Any other numbered Versions and other technical work produced by the Technical Committee (TC) are listed at https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=openc2#technical.

TC members should send comments on this specification to the TC's email list. Others should send comments to the TC's public comment list, after subscribing to it by following the instructions at the "Send A Comment" button on the TC's web page at https://www.oasis-open.org/committees/openc2/.

This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the OASIS IPR Policy, the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page (https://www.oasis-open.org/committees/openc2/ipr.php).

Note that any machine-readable content ([Computer Language Definitions](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsCompLang)) declared Normative for this Work Product is provided in separate plain text files. In the event of a discrepancy between any such plain text file and display content in the Work Product's prose narrative document(s), the content in the separate plain text file prevails.

#### URI patterns:
Initial publication URI:  
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/csprd01/ap-sbom-v1.0-csprd01.html

Permanent "Latest stage" URI:  
https://docs.oasis-open.org/openc2/ap-sbom/v1.0/ap-sbom-v1.0.html

(Note: Publication URIs are managed by OASIS TC Administration; please don't modify.)

#### Citation format:
When referencing this specification the following citation format should be used:

**[OpenC2-SBOM-v1.0]**

_Open Command and Control (OpenC2) Profile for Software Bill of Materials Retrieval Version 1.0_. Edited by Duncan Sparrell. 26 May 2020. OASIS Committee Specification Draft 01 / Public Review Draft 01. https://docs.oasis-open.org/openc2/ap-sbom/v1.0/csprd01/ap-sbom-v1.0-csprd01.html. Latest stage: https://docs.oasis-open.org/openc2/ap-sbom/v1.0/ap-sbom-v1.0.html.

-------

## Notices
Copyright © OASIS Open 2020. All Rights Reserved.

All capitalized terms in the following text have the meanings assigned to them in the OASIS Intellectual Property Rights Policy (the "OASIS IPR Policy"). The full [Policy](https://www.oasis-open.org/policies-guidelines/ipr) may be found at the OASIS website.

This document and translations of it may be copied and furnished to others, and derivative works that comment on or otherwise explain it or assist in its implementation may be prepared, copied, published, and distributed, in whole or in part, without restriction of any kind, provided that the above copyright notice and this section are included on all such copies and derivative works. However, this document itself may not be modified in any way, including by removing the copyright notice or references to OASIS, except as needed for the purpose of developing any document or deliverable produced by an OASIS Technical Committee (in which case the rules applicable to copyrights, as set forth in the OASIS IPR Policy, must be followed) or as required to translate it into languages other than English.

The limited permissions granted above are perpetual and will not be revoked by OASIS or its successors or assigns.

This document and the information contained herein is provided on an "AS IS" basis and OASIS DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION HEREIN WILL NOT INFRINGE ANY OWNERSHIP RIGHTS OR ANY IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.

OASIS requests that any OASIS Party or any other party that believes it has patent claims that would necessarily be infringed by implementations of this OASIS Committee Specification or OASIS Standard, to notify OASIS TC Administrator and provide an indication of its willingness to grant patent licenses to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this specification.

OASIS invites any party to contact the OASIS TC Administrator if it is aware of a claim of ownership of any patent claims that would necessarily be infringed by implementations of this specification by a patent holder that is not willing to provide a license to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this specification. OASIS may include such claims on its website, but disclaims any obligation to do so.

OASIS takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this document or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any effort to identify any such rights. Information on OASIS' procedures with respect to rights in any document or deliverable produced by an OASIS Technical Committee can be found on the OASIS website. Copies of claims of rights made available for publication and any assurances of licenses to be made available, or the result of an attempt made to obtain a general license or permission for the use of such proprietary rights by implementers or users of this OASIS Committee Specification or OASIS Standard, can be obtained from the OASIS TC Administrator. OASIS makes no representation that any information or list of intellectual property rights will at any time be complete, or that any claims in such list are, in fact, Essential Claims.

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs. OASIS welcomes reference to, and implementation and use of, specifications, while reserving the right to enforce its marks against misleading uses. Please see https://www.oasis-open.org/policies-guidelines/trademark for above guidance.

-------

# Table of Contents
[[TOC will be inserted here]]

-------

# 1 Introduction

_The content in this section is non-normative, except where it is marked normative._

This document is the specification for
the OpenC2 actuator profile
of a device with the
capability to return a Software Bill Of Materials (SBOM) when queried.

OpenC2 is a suite of specifications
that enables command and control of cyber defense systems and components.
OpenC2 typically uses a request-response paradigm
where a _Command_ is encoded by a _Producer_ (managing application)
and transferred to a _Consumer_ (managed device or virtualized function)
using a secure transfer protocol,
and the Consumer can respond with status and any requested information.

OpenC2 allows the application producing the commands
to discover the set of capabilities supported
by the managed devices.
These capabilities permit the managing application
to adjust its behavior to take advantage of the features exposed by the managed device.
The capability definitions can be easily extended in a noncentralized manner,
allowing standard and non-standard capabilities to be defined with semantic and syntactic rigor.

_EDITOR's NOTE: Add words about SBOM and about AP's in general and this one specifically_

## 1.1 IPR Policy
This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the [OASIS IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr), the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page ([https://www.oasis-open.org/committees/openc2/ipr.php](https://www.oasis-open.org/committees/openc2/ipr.php)).

## 1.2 Terminology
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [[RFC2119](#rfc2119)] and [[RFC8174](#rfc8174)] when, and only when, they appear in all capitals, as shown here.

## 1.3 Normative References

EDITOR's NOTE: This section needs work

###### [OpenC2-Lang-v1.0]
_Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.
###### [RFC2119]
Bradner, S., "Key words for use in RFCs to Indicate Requirement Levels", BCP 14, RFC 2119, DOI 10.17487/RFC2119, March 1997, http://www.rfc-editor.org/info/rfc2119.
###### [RFC8174]
Leiba, B., "Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words", BCP 14, RFC 8174, DOI 10.17487/RFC8174, May 2017, http://www.rfc-editor.org/info/rfc8174.

## 1.4 Non-Normative References

EDITOR's NOTE: This section needs work

###### [RFC3552]
Rescorla, E. and B. Korver, "Guidelines for Writing RFC Text on Security Considerations", BCP 72, RFC 3552, DOI 10.17487/RFC3552, July 2003, https://www.rfc-editor.org/info/rfc3552.

## 1.5 Document Conventions

EDITOR's NOTE: This section needs work

## 1.6 Overview

EDITOR's NOTE: This section needs work

## 1.7 Goal

EDITOR's NOTE: This section needs work

# 2. OpenC2 Language Binding

_This section is normative_

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


# 3 Safety, Security, and Data Protection Considerations

EDITOR's NOTE: This section needs work

(Note: OASIS strongly recommends that Technical Committees consider issues that might affect safety, security, privacy, and/or data protection in implementations of their specification and document them for implementers and adopters. For some purposes, you may find it required, e.g. if you apply for IANA registration.

While it may not be immediately obvious how your specification might make systems vulnerable to attack, most specifications, because they involve communications between systems, message formats, or system settings, open potential channels for exploit. For example, IETF [[RFC3552](#rfc3552)] lists “eavesdropping, replay, message insertion, deletion, modification, and man-in-the-middle” as well as potential denial of service attacks as threats that must be considered and, if appropriate, addressed in IETF RFCs.

In addition to considering and describing foreseeable risks, this section should include guidance on how implementers and adopters can protect against these risks.

We encourage editors and TC members concerned with this subject to read _Guidelines for Writing RFC Text on Security Considerations_, IETF [[RFC3552](#rfc3552)], for more information.

Remove this note before submitting for publication.)

-------

# 4 Conformance

EDITOR's NOTE: This section needs work

(Note: The [OASIS TC Process](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsConfClause) requires that a specification approved by the TC at the Committee Specification Public Review Draft, Committee Specification or OASIS Standard level must include a separate section, listing a set of numbered conformance clauses, to which any implementation of the specification must adhere in order to claim conformance to the specification (or any optional portion thereof). This is done by listing the conformance clauses here.
For the definition of "conformance clause," see [OASIS Defined Terms](https://www.oasis-open.org/policies-guidelines/oasis-defined-terms-2017-05-26#dConformanceClause).

See "Guidelines to Writing Conformance Clauses":  
http://docs.oasis-open.org/templates/TCHandbook/ConformanceGuidelines.html.

Remove this note before submitting for publication.)


-------

# Annex A? Appendix A? Examples

EDITOR's NOTE: This section needs work

# Appendix A. Acknowledgments

EDITOR's NOTE: This section needs work

(Note: A Work Product approved by the TC must include a list of people who participated in the development of the Work Product. This is generally done by collecting the list of names in this appendix. This list shall be initially compiled by the Chair, and any Member of the TC may add or remove their names from the list by request.  
Remove this note before submitting for publication.)

The following individuals have participated in the creation of this specification and are gratefully acknowledged:

**OpenC2 TC Members:**

| First Name | Last Name | Company |
| :--- | :--- | :--- |
Philippe | Alcoy | Arbor Networks
Alex | Amirnovin | Viasat
Kris | Anderson | Trend Micro
Darren | Anstee | Arbor Networks

-------

# Appendix B. Revision History

EDITOR's NOTE: This section needs work

| Revision | Date | Editor | Changes Made |
| :--- | :--- | :--- | :--- |
| specname-v1.0-wd01 | yyyy-mm-dd | Editor Name | Initial working draft |
