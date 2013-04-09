**The SPDX License List (SPDX-LL) is a list of commonly found open
source software licenses for the purposes of being able to easily and
efficiently identify such licenses in an SPDX document. The SPDX License
List includes a standardized short identifier, full name, vetted license
text, other basic information, and a canonical permanent URL for each
license. By providing a short identifier, users can efficiently refer to
a license without having to redundantly reproduce the full license.**

**By including a license on this list, the SPDX workgroup makes no
judgement about its suitability or desirability. The list is meant only
to standardize references to commonly used, open source licenses, not to
promote or discourage the use of any license.**

This page describes the current principles for the inclusion of a
license on the SPDX-LL, as well as an explanation of the fields
contained on the list.

  - You may propose additional licenses be added to the SPDX License
    List by following the process at: [SPDX License List: Process for
    requesting new licenses to be
    added](http://spdx.org/content/spdx-license-list-process-requesting-new-licenses-be-added).
  - Guidelines for what constitutes a license match to the SPDX License
    List when generating an SPDX file can be found here: [SPDX License
    List Match
    Guidelines.](http://spdx.org/content/spdx-license-list-license-matching-guidelines)

## License Inclusion Principles

### Background Principles

The Software Package Data Exchange® (SPDX®) specification is a standard
format for communicating the components, licenses, and copyrights
associated with open source software packages. Use of this standard
streamlines license identification across the supply chain while
reducing redundant work.

The goal of SPDX is not to evaluate licensing information or to provide
legal interpretations. The goal is solely to reliably and consistently
communicate and share licensing information so that organizations using
software components will have the information necessary to conduct their
independent analysis and evaluation. Establishing a consistent,
reliable, and reusable way to communicate license information for
software components will then facilitate open source license compliance
along the supply chain.

Although SPDX has traditionally focused on open source licensing,
software may contain a mix of open-source licensed,
commercially-licensed, freeware licensed, and other varieties of
licensed packages. Thus, it is feasible that a future version of the
standard may develop a standardized method of identifying non-open
source licenses contained within software packages.

Because the present focus of SPDX is the collection and presentation of
the open-source software licenses contained in a software package, any
license that is a candidate for inclusion on the SPDX License List must
be an "open source" license.

### Open Source Definition

The terms "free software," "open source software," or their variants
(FOSS, FLOSS, libre software, etc.) are defined differently by different
organizations. At a minimum all definitions of open source or free
software include the characteristic that the source code be made
available for inspection and modification and that the source code may
be freely distributed. However, there are a number of other
characteristics that vary depending on the policy focus of the defining
organization. Even though the various definitions of open source
software differ in some respects, there are certain fundamental
characteristics commonly incorporated in all these definitions.

The SPDX Legal Team uses the definition promulgated by the Open Source
Initiative (OSI) as the basis for analyzing candidate licenses for
inclusion on the SPDX License List. That definition provides as follows:

Introduction

Open source doesn't just mean access to the source code. The
distribution terms of open-source software must comply with the
following criteria:

1.  Free Redistribution. The license shall not restrict any party from
    selling or giving away the software as a component of an aggregate
    software distribution containing programs from several different
    sources. The license shall not require a royalty or other fee for
    such sale.
2.  Source Code. The program must include source code, and must allow
    distribution in source code as well as compiled form. Where some
    form of a product is not distributed with source code, there must be
    a well-publicized means of obtaining the source code for no more
    than a reasonable reproduction cost preferably, downloading via the
    Internet without charge. The source code must be the preferred form
    in which a programmer would modify the program. Deliberately
    obfuscated source code is not allowed. Intermediate forms such as
    the output of a preprocessor or translator are not allowed.
3.  Derived Works. The license must allow modifications and derived
    works, and must allow them to be distributed under the same terms as
    the license of the original software.
4.  Integrity of The Author's Source Code. The license may restrict
    source-code from being distributed in modified form only if the
    license allows the distribution of "patch files" with the source
    code for the purpose of modifying the program at build time. The
    license must explicitly permit distribution of software built from
    modified source code. The license may require derived works to carry
    a different name or version number from the original software.
5.  No Discrimination Against Persons or Groups. The license must not
    discriminate against any person or group of persons.
6.  No Discrimination Against Fields of Endeavor. The license must not
    restrict anyone from making use of the program in a specific field
    of endeavor. For example, it may not restrict the program from being
    used in a business, or from being used for genetic research.
7.  Distribution of License. The rights attached to the program must
    apply to all to whom the program is redistributed without the need
    for execution of an additional license by those parties.
8.  License Must Not Be Specific to a Product. The rights attached to
    the program must not depend on the program's being part of a
    particular software distribution. If the program is extracted from
    that distribution and used or distributed within the terms of the
    program's license, all parties to whom the program is redistributed
    should have the same rights as those that are granted in conjunction
    with the original software distribution.
9.  License Must Not Restrict Other Software. The license must not place
    restrictions on other software that is distributed along with the
    licensed software. For example, the license must not insist that all
    other programs distributed on the same medium must be open-source
    software.
10. License Must Be Technology-Neutral. No provision of the license may
    be predicated on any individual technology or style of interface.

''Available on the world wide web at <http://opensource.org/osd> (March
14, 2013). ''

### Candidate License Analysis

Determining whether a candidate license is deemed to be open source for
purpose of inclusion on the SPDX License List requires the SPDX Legal
Team to engage in a case-by-case evaluation of each candidate license.
Any candidate license that substantially complies with the open source
definition will be added to the SPDX License List. Nevertheless, the
SPDX Legal Team does not require (1) strict compliance with all elements
of the OSI Definition or (2) strict compliance with any particular
element of the OSI Definition. Rather, it treats each of the elements of
the definition as a factor to be balanced in light of the totality of
the candidate license and SPDX's goals and objectives. Consequently, the
SPDX Legal Team will determine whether and to what degree the candidate
license addresses each of the elements of the open source definition.
The SPDX Legal Team may also analyze “environmental” factors outside the
open source definition, such as whether a candidate license is already
included on the OSI license list or other such lists, whether the
candidate license is in common use, or whether a commonly used open
source project uses it (particularly where such open source project is a
dependency on which other projects rely).

The SPDX Legal Team may prepare a memorandum explaining its reasoning,
analysis, and conclusions with respect to a candidate license as a means
of developing precedent and publish the same on the SPDX website.
Nevertheless, the SPDX Legal Team is not required to do so.

**Explanation of SPDX License List fields:**

The following information describes how each field on the license list
(whether on the webpage or within the spreadsheet) is treated.

**A) Full Name of License**

  - The full license name my omit certain word, such as "the," for
    alphabetical sorting purposes
  - No commas in full name of license
  - Do not spell out “version” – use “v” or nothing to indicate license
    version (for space reasons)
  - Use lower case v and no period or space b/w v and the number
  - Remove any license abbreviations from parenthesis after full license
    name

**B) License Identifier (aka "SPDX Short Identifier")**

  - Short identifier to be used to identify a license match to licenses
    contained on the SPDX-LL in the context of an SPDX file
  - Identifier should have no spaces in it
  - Identifier consists of a short name, abbreviation, or acronym for
    the license
  - Where applicable, license abbreviation will be followed by a dash
    and then the version number, in X.Y format

**C) Source/url**

  - Include url for license author’s website
  - If the license is OSI approved, also include url for OSI license
    page
  - Other website that has text version of license, if neither of the
    first two options are available
  - Link to license in native language is used where specified (e.g.
    French for CeCILL). Link to English version where multiple,
    equivalent official translations (e.g. EUPL)

**D) Notes**

  - Include date of release, if found, for licenses with multiple
    versions, using European date format: day – month – year
  - Only factual information should be included here, e.g. the license
    has been deprecated.
  - Does not contain information (or links to information) that includes
    any kind of interpretation or comment about the license (even if
    written by the license author)

**E) OSI Approved**

  - If the license is OSI approved, this field will indicate "yes,"
    otherwise left blank

**F) Standard License Header**

  - Should only include text intended to be put in the header of source
    files or other files as specified in the license or license appendix
    when specifically delineated
  - Indicate if there is any variation in the header (i.e. for files
    developed by a contributor versus when applying license to original
    work)
  - Do not include NOTICE info intended for a separate notice file
  - Leave this field blank if there is no standard header as
    specifically defined in the license

**G) Text**

  - Full license text or, in the spreadsheet, reference to separate .txt
    file named by SPDX Short Identifier that contains full license text

Any additional information or columns contained in the spreadsheet
version of the SPDX-LL are not part of the official SPDX License List
and are included for tracking or informational purposes only.

[Category:Legal](Category:Legal "wikilink")
