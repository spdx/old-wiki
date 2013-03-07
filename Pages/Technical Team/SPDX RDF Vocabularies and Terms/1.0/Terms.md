\_\_NOTOC\_\_

## SPDX Vocabulary Specification

  - Version:  
    1.0

  - Latest Version:  
    <http://spdx.org/rdf/terms>

  - Alternate Formats:

:\* [RDF/XML](http://spdx.org/rdf/terms.rdf)

:\* [Turtle](http://spdx.org/rdf/terms.ttl)

Copyright © 2010-2011 Linux Foundation and its Contributors. All other
rights are expressly reserved.

Licensed under the [Creative Commons Attribution License 3.0
unported](http://creativecommons.org/licenses/by/3.0/).

## Abstract

This specification describes the SPDX language, defined as a dictionary
of named properties and classes using W3C's RDF Technology.

SPDX is a designed to allow the exchange of data about software
packages. This information includes general information about the
package, licensing information about the package as a whole, a manifest
of files contained in the package and licensing information related to
the contained files.

The `spdx` prefix used in this document expands to
<http://spdx.org/rdf/terms#>. Any terms in this document without an
explicit prefix may be assumed to be in the `spdx` namespace.

## Other vocabularies used by this one

  - [DOAP](http://trac.usefulinc.com/doap)

## Classes

  - `SpdxDocument`
  - `CreationInfo`
  - `Package`
  - `ExtractedLicensingInfo`
  - `Checksum`
  - `PackageVerificationCode`
  - `File`
  - `Review`
  - `License`
  - `ConjunctiveLicenseSet`
  - `DisjunctiveLicenseSet`
  - `AnyLicenseInfo`
  - `SimpleLicenseInfo`

### Class: `SpdxDocument`

An `SdpxDocument` is a summary of the contents, provenance, ownership
and licensing analysis of a specific software package. This is,
effectively, the top level of SPDX information.

  - Status:  
    stable

  - Properties:

:\* `specVersion`  
Cardinality: Mandatory, one

:\* `dataLicense`  
Cardinality: Mandatory, one

:\* `creationInfo`  
Cardinality: Mandatory, one

:\* `describesPackage`  
Cardinality: Mandatory, one

:\* `hasExtractedLicensingInfo`  
Cardinality: Optional, zero or more

:\* `referencesFile`  
Cardinality: Mandatory, one or more

:\* `reviewed`  
Cardinality: Optional, zero or more.

### Class: `CreationInfo`

A `CreationInfo` provides information about the individuals,
organizations and tools involved in the creation of an `SpdxDocument`.

  - Status:  
    stable

  - Properties:

:\* `creator`  
Cardinality: Mandatory, one or more

:\* `created`  
Cardinality: Mandatory, one

:\* [`rdfs:comment`](http://www.w3.org/TR/rdf-schema/#ch_comment)  
Cardinality: Optional, zero or one

### Class: `Package`

A `Package` represents a collection of software files that are delivered
as a single functional component.

  - Status:  
    stable

  - Properties:

:\* `name`  
Cardinality: Mandatory, one

:\* `versionInfo`  
Cardinality: Optional, zero or one

:\* `packageFileName`  
Cardinality: Mandatory, one

:\* `supplier`  
Cardinality: Optional, zero or one

:\* `originator`  
Cardinality: Optional, zero or one

:\* `downloadLocation`  
Cardinality: Mandatory, one

:\* `packageVerificationCode`  
Cardinality: Mandatory, one

:\* `checksum`  
Cardinality: Optional, zero or one

:\* `sourceInfo`  
Cardinality: Optional, zero or one

:\* `licenseConcluded`  
Cardinality: Mandatory, one

:\* `licenseInfoFromFiles`  
Cardinality: Mandatory, one or more

:\* `licenseDeclared`  
Cardinality: Mandatory, one

:\* `licenseComments`  
Cardinality: Optional, zero or one

:\* `copyrightText`  
Cardinality: Mandatory, one

:\* `summary`  
Cardinality: Optional, zero or one

:\* `description`  
Cardinality: Optional, zero or one

:\* `hasFile`  
Cardinality: Mandatory, one or more

### Class: `ExtractedLicensingInfo`

An `ExtractedLicensingInfo` represents a license or licensing notice
that was found in the package. Any license text that is recognized as a
license may be represented as a `License` rather than an
`ExtractedLicensingInfo`.

  - Status:  
    stable

  - Properties:

:\* `licenseId`  
Cardinality: Mandatory, one

:\* `extractedText`  
Cardinality: Mandatory, one

### Class: `File`

A `File` represents a named sequence of information that is contained in
a software package.

  - Status:  
    stable

  - Properties:

:\* `fileName`  
Cardinality: Mandatory, one

:\* `fileType`  
Cardinality: Optional, zero or one

:\* `checksum`  
Cardinality: Mandatory, one

:\* `licenseConcluded`  
Cardinality: Mandatory, one

:\* `licenseInfoInFile`  
Cardinality: Mandatory, one or more

:\* `licenseComments`  
Cardinality: Optional, zero or one

:\* `copyrightText`  
Cardinality: Mandatory, one

:\* `artifactOf`  
Cardinality: Optional, zero or one

### Class: `Review`

A `Review` represents an audit and signoff by an individual,
organization or tool on the information in an `SpdxDocument`.

  - Status:  
    stable

  - Properties:

:\* `reviewer`  
Cardinality: Mandatory, one

:\* `reviewDate`  
Cardinality: Mandatory, one

:\* [`rdfs:comment`](http://www.w3.org/TR/rdf-schema/#ch_comment)  
Cardinality: Optional, zero or one

### Class: `License`

A `License` represents a software copyright license. This class is used
by the SPDX license list to represent standard licenses.

  - Status:  
    stable

  - Properties:

:\* `licenseId`  
Cardinality: Mandatory, one

:\* `licenseText`  
Cardinality: Mandatory, one

### Class: `Checksum`

A `Checksum` is value that allows the contents of a file to be
authenticated. Even small changes to the content of the file will change
it's checksum. This class allows the results of a variety of checksum
and cryptographic message digest algorithms to be represented.

  - Status:  
    stable

  - Properties:

:\* `algorithm`  
Cardinality: Mandatory, one

:\* `checksumValue`  
Cardinality: Mandatory, one

### Class: `PackageVerificationCode`

A `PackageVerificationCode` is a value that allows authentication of the
package. This differs from the `Checksum` in that it uses an algorithm
that allows the SPDX file to be embedded in the package. This
verification code is produced using a cryptographic hash algorithm
applied to a manifest of the package. Some files in the package (e.g.
the SPDX files) are explicitly excluded from the verification code. This
allows those excluded files to not impact the verification code.

  - Status:  
    stable

  - Properties:

:\* `packageVerificationCodeExcludedFile`  
Cardinality: Optional, zero or more

:\* `packageVerificationCodeValue`  
Cardinality: Mandatory, one

### Class: `ConjunctiveLicenseSet`

A `ConjunctiveLicenseSet` represents a set of licensing information all
of which apply.

This class refines
[`rdfs:Container`](http://www.w3.org/TR/rdf-schema/#ch_container).

  - Status:  
    stable

  - Properties:

:\* `member`  
Cardinality: Mandatory, two or more.

### Class: `DisjunctiveLicenseSet`

A `DisjunctiveLicenseSet` represents a set of licensing information
where only one license applies at a time. This class implies that the
recipient gets to choose one of these licenses they would prefer to use.

This class refines
[`rdfs:Container`](http://www.w3.org/TR/rdf-schema/#ch_container).

  - Status:  
    stable

  - Properties:

:\* `member`  
Cardinality: Mandatory, two or more.

### Class: `AnyLicenseInfo`

The `AnyLicenseInfo` class includes all resources that represent
licensing information.

  - Status:  
    stable
  - Members  
    All resources in any of the following classes:
      - `License`
      - `ExtractedLicensingInfo`
      - `ConjunctiveLicenseSet`
      - `DisjunctiveLicenseSet`

### Class: `SimpleLicenseInfo`

The `SimpleLicenseInfo` class includes all resources that represent
simple, atomic, licensing information.

  - Status:  
    stable
  - Members  
    All resources in any of the following classes:
      - `License`
      - `ExtractedLicensingInfo`

## Properties

  - `algorithm`
  - `artifactOf`
  - `checksum`
  - `checksumValue`
  - `copyrightText`
  - `created`
  - `creationInfo`
  - `creator`
  - `dataLicense`
  - `describesPackage`
  - `description`
  - `downloadLocation`
  - `extractedText`
  - `fileName`
  - `fileType`
  - `hasExtractedLicensingInfo`
  - `hasFile`
  - `licenseComments`
  - `licenseConcluded`
  - `licenseDeclared`
  - `licenseId`
  - `licenseText`
  - `licenseInfoFromFiles`
  - `licenseInfoInFile`
  - `member`
  - `name`
  - `originator`
  - `packageFileName`
  - `packageVerificationCode`
  - `packageVerificationCodeExcludedFile`
  - `packageVerificationCodeValue`
  - `referencesFile`
  - `reviewDate`
  - `reviewed`
  - `reviewer`
  - `sourceInfo`
  - `specVerison`
  - `summary`
  - `supplier`
  - `versionInfo`

### Property: `algorithm`

Identifies the algorithm used to produce the subject `Checksum`.

Currently, [SHA-1](http://www.itl.nist.gov/fipspubs/fip180-1.htm) is the
only supported algorithm. It is anticipated that other algorithms will
be supported at a later time.

  - Status:  
    stable
  - Domain:  
    `Checksum`
  - Range:  
    `spdx:checksumAlgorithm_sha1`

### Property: `artifactOf`

Indicates the project in which the file originated.

Tools must preserve `doap:hompage` and `doap:name` properties and the
URI (if one is known) of `doap:Project` resources that are values of
this property. All other properties of `doap:Projects` are not directly
supported by SPDX and may be dropped when translating to or from some
SPDX formats.

  - Status:  
    stable
  - Domain:  
    `File`
  - Range:  
    [`doap:Project`](http://usefulinc.com/ns/doap#Project)

### Property: `checksum`

The `checksum` property provides a mechanism that can be used to verify
that the contents of a `File` or `Package` have not changed.

  - Status:  
    stable
  - Domain:  
    Any of:
      - `Package`
      - `File`
  - Range:  
    Checksum

### Property: `checksumValue`

The `checksumValue` property provides a lower case hexidecimal encoded
digest value produced using a specific algorithm.

  - Status:  
    stable
  - Domain:  
    `Checksum`
  - Range:  
    [`xsd:hexBinary`](http://www.w3.org/TR/xmlschema-2/#hexBinary)

### Property: `created`

The date and time at which the `SpdxDocument` was created. This value
must in UTC and have 'Z' as its timezone indicator.

  - Status:  
    stable
  - Domain:  
    `CreationInfo`
  - Range:  
    [`xsd:dateTime`](http://www.w3.org/TR/xmlschema-2/#dateTime)

### Property: `copyrightText`

The text of copyright declarations recited in the `Package` or `File`.

  - Status:  
    stable
  - Domain:  
    Any of:
      - `Package`
      - `File`
  - Range:  
    Any of:
      - [`rdfs:Literal`](http://www.w3.org/TR/rdf-schema/#ch_literal)
      - `spdx:none`
      - `spdx:noassertion`

### Property: `creationInfo`

The `creationInfo` property relates an `SpdxDocument` to a set of
information about the creation of the `SpdxDocument`.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    `CreationInfo`

### Property: `creator`

The name and, optionally, contact information of a person, organization
or tool that created, or was used to create, the `SpdxDocument`.

Values of this property must conform to the agent and tool syntax.

  - Status:  
    stable
  - Domain:  
    `CreationInfo`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `dataLicense`

The licensing under which the `creator` of this SPDX document allows
related data to be reproduced.

The only valid value for this property is
<http://spdx.org/licenses/PDDL-1.0>. This is to alleviate any concern
that content (the data) in an SPDX file is subject to any form of
intellectual property right that could restrict the re-use of the
information or the creation of another SPDX file for the same
project(s). This approach avoids intellectual property and related
restrictions over the SPDX file, however individuals can still contract
one to one to restrict release of specific collections of SPDX files
(which map to software bill of materials) and the identification of the
supplier of SPDX files.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    <http://spdx.org/licenses/PDDL-1.0>

### Property: `describesPackage`

The `describesPackage` property relates an `SpdxDocument` to the package
which it describes.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    `Package`

### Property: `description`

Provides a detailed description of the package.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `downloadLocation`

The URI at which this package is available for download. Private (i.e.,
not publicly reachable) URIs are acceptable as values of this property.

The values <http://spdx.org/rdf/terms#none> and
<http://spdx.org/rdf/terms#noassertion> may be used to specify that the
package is not downloadable or that no attempt was made to determine its
download location, respectively.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:anyURI`](http://www.w3.org/TR/xmlschema-2/#anyURI)

### Property: `extractedText`

Verbatim license or licensing notice text that was discovered.

  - Status:  
    stable
  - Domain:  
    `ExtractedLicensingInfo`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `fileName`

The name of the file relative to the root of the package.

  - Status:  
    stable
  - Domain:  
    `File`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `fileType`

The type of the file.

  - Status:  
    stable
  - Domain:  
    `File`
  - Range:  
    One of:
      - `spdx:fileType_source` Indicates the file is a source code file.
      - `spdx:fileType_archive` Indicates the file is an archive file.
      - `spdx:fileType_binary` Indicates the file is not a text file.
        `filetype_archive` is preferred for archive files even though
        they are binary.
      - `spdx:fileType_other` Indicates the file did not fall into any
        of the other categories.

### Property: `hasExtractedLicensingInfo`

Indicates that a particular `ExtractedLicensingInfo` was defined in the
subject `SpdxDocument`.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    `ExtractedLicensingInfo`

### Property: `hasFile`

Indicates that a particular file belongs to a package.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    `File`

### Property: `licenseComments`

The `licenseComments` property allows the preparer of the SPDX document
to describe why the licensing in `spdx:licenseConcluded` was chosen.

  - Status:  
    stable
  - Domain:  
    Any of:
      - `Package`
      - `File`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `licenseConcluded`

The licensing that the preparer of this SPDX document has concluded,
based on the evidence, actually applies to the package.

  - Status:  
    stable
  - Domain:  
    Any of:
      - `Package`
      - `File`
  - Range:  
    Any of:
      - `AnyLicenseInfo`
      - `spdx:none`
      - `spdx:noassertion`

### Property: `licenseDeclared`

The licensing that the creators of the software in the package, or the
packager, have declared. Declarations by the original software creator
should be preferred, if they exist.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    Any of:
      - `AnyLicenseInfo`
      - `spdx:none`
      - `spdx:noassertion`

### Property: `licenseId`

A short name for the license that is at least 3 characters long and made
up of the characters from the set 'a'-'z', 'A'-'Z', '0'-'9', '+', '\_',
'.', and '-'. Formally, all `licenseId` values must match the regular
expression: `[-+_.a-zA-Z0-9]{3,}`

  - Status:  
    stable

  - Domain:

:\* `License`

:\* `ExtractedLicensingInfo`

  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `licenseText`

The full text of the license.

  - Status:  
    stable
  - Domain:  
    `License`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `licenseInfoFromFiles`

The licensing information that was discovered directly within the
package. There will be an instance of this property for each distinct
value of all `licenseInfoInFile` properties of all files contained in
the package.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    Any of:
      - `SimpleLicenseInfo`
      - `spdx:none`
      - `spdx:noassertion`

### Property: `licenseInfoInFile`

Licensing information that was discovered directly in the subject file.

  - Status:  
    stable
  - Domain:  
    `File`
  - Range:  
    Any of:
      - `SimpleLicenseInfo`
      - `spdx:none`
      - `spdx:noassertion`

### Property: `member`

A license, or other licensing information, that is a member of the
subject license set.

  - Status:  
    stable
  - Domain:  
    Any of:
      - `ConjunctiveLicenseSet`
      - `DisjunctiveLicenseSet`
  - Range:  
    `AnyLicenseInfo`
  - Refines:  
    [`rdfs:member`](http://www.w3.org/TR/rdf-schema/#ch_member)

### Property: `name`

The full name of the package including version information.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `originator`

The name and, optionally, contact information of the person or
organization that originally created the package.

Values of this property must conform to the agent and tool syntax.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string) or the
    individual `spdx:noassertion`

### Property: `packageFileName`

The base name of the package file name. For example,
`zlib-1.2.5.tar.gz`.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `packageVerificationCode`

A manifest based authentication code for the package. This allows
consumers of this data to determine if a package they have in hand is
identical to the package from which the data was produced. This
algorithm works even if the SPDX document is included in the package.
This algorithm is described in detail in the SPDX specification.

The package verification code algorithm is defined in section 4.7 of the
full specification.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    `PackageVerificationCode`

### Property: `packageVerificationCodeExcludedFile`

A file that was excluded when calculating the package verification code.
This is usually a file containing SPDX data regarding the package. If a
package contains more than one SPDX file all SPDX files must be excluded
from the package verification code. If this is not done it would be
impossible to correctly calculate the verification codes in both files.

  - Status:  
    stable
  - Domain:  
    `PackageVerificationCode`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `packageVerificationCodeValue`

The actual package verification code as a hex encoded value.

  - Status:  
    stable
  - Domain:  
    `PackageVerificationCode`
  - Range:  
    [`xsd:hexBinary`](http://www.w3.org/TR/xmlschema-2/#hexBinary)

### Property: `referencesFile`

Indicates that a particular file belongs as part of the set of analyzed
files in the `SpdxDocument`.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    `File`

### Property: `reviewDate`

The date and time at which the `SpdxDocument` was reviewed. This value
must be in UTC and have 'Z' as its timezone indicator.

  - Status:  
    stable
  - Domain:  
    `Review`
  - Range:  
    [`xsd:dateTime`](http://www.w3.org/TR/xmlschema-2/#dateTime)

### Property: `reviewed`

The `review` property relates a `SpdxDocument` to the review history.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    `Review`

### Property: `reviewer`

The name and, optionally, contact information of the person who
performed the review.

Values of this property must conform to the agent and tool syntax.

  - Status:  
    stable
  - Domain:  
    `Review`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `sourceInfo`

Allows the producer(s) of the SPDX document to describe how the package
was acquired and/or changed from the original source.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `specVersion`

Identifies the version of this specification that was used to produce
this SPDX document. Currently the only supported value is `SPDX-1.0`.

  - Status:  
    stable
  - Domain:  
    `SpdxDocument`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `summary`

Provides a short description of the package.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

### Property: `supplier`

The name and, optionally, contact information of the person or
organization that is the immediate supplier of this package to the
recipient. The supplier may be different than `originator` when the
software has been repackaged. For example if you get glibc from RedHat,
RedHat is the Package Supplier, but FSF is the `originator`.

Values of this property must conform to the agent and tool syntax.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string) or the
    individual `spdx:noassertion`

### Property: `versionInfo`

Provides an indication of the version of the package that is described
by this `SpdxDocument`.

  - Status:  
    stable
  - Domain:  
    `Package`
  - Range:  
    [`xsd:string`](http://www.w3.org/TR/xmlschema-2/#string)

## Individuals

  - `checksumAlgorithm_sha1`
  - `fileType_archive`
  - `fileType_binary`
  - `fileType_other`
  - `fileType_source`
  - `noassertion`
  - `none`

### Individual: `checksumAlgorithm_sha1`

Indicates the algorithm used was
[SHA-1](http://www.itl.nist.gov/fipspubs/fip180-1.htm)

  - Status:  
    stable

### Individual: `fileType_archive`

Indicates the file is an archive file.

  - Status:  
    stable

### Individual: `fileType_binary`

Indicates the file is not a text file. `spdx:filetype_archive` is
preferred for archive files even though they are binary.

  - Status:  
    stable

### Individual: `fileType_other`

Indicates the file is not a source, archive or binary file.

  - Status:  
    stable

### Individual: `fileType_source`

Indicates the file is a source code file.

  - Status:  
    stable

### Individual: `noassertion`

Indicates that the preparer of the SPDX document is not making any
assertion regarding the value of this field.

  - Status:  
    stable

### Individual: `none`

When this value is used as the object of a property it indicates that
the preparer of the `SpdxDocument` believes that there is no value for
the property. This value should only be used if there is sufficient
evidence to support this assertion.

  - Status:  
    stable

## Agent and Tool Identifiers

Fields that identify entities that have acted in relation to the SPDX
file are single line of text which name the agent or tool and,
optionally, provide contact information. For example, "Person: Jane Doe
(jane.doe@example.com)", "Organization: ExampleCodeInspect
(contact@example.com)" and "Tool: LicenseFind - 1.0". The exact syntax
of agent and tool identifications is described below in
[ABNF](http://tools.ietf.org/html/rfc4234).

`   agent = person / organization tool = "Tool: " name 0*1( " " DASH " " version) person =`  
`   "Person: " name 0*1contact-info organization = "Organization: " name 0*1contact-info name =`  
`   1*( UNRESERVED ) / U+0022 1*( VCHAR-SANS-QUOTE ) U+0022 contact-info = " (" email-addr ")"`  
`   email-addr = local-name-atom *( "." local-name-atom ) "@" domain-name-atom 1*( "." domain-`  
`   name-atom ) version = 1*VCHAR-SANS-QUOTE local-name-atom = 1*( ALPHA / DIGIT / ; Printable`  
`   US-ASCII "!" / "#" / ; characters not including "$" / "%" / ; specials. "&" / "'" / "*" /`  
``   "+" / "-" / "/" / "=" / "?" / "^" / "_" / "`" / "{" / "|" / "}" / "~" ) domain-name-atom =``  
`   1*( ALPHA / DIGIT / "-" ) DASH = U+2010 / U+2212 / ; hyphen, minus, em dash and U+2013 /`  
`   U+2014 ; en dash UNRESERVED = U+0020-U+0027 / ; visible unicode characters U+0029-U+0080 /`  
`   ; except '(' and dashes U+00A0-U+200F / U+2011-U+2027 / U+202A-U+2211 / U+2213-U+E01EF`  
`   VCHAR-SANS-QUOTE = U+0020-U+0021 / ; visible unicode characters U+0023-U+0080 / ; except`  
`   quotation mark U+00a0-U+E01EF`

[Category:Technical](Category:Technical "wikilink")
