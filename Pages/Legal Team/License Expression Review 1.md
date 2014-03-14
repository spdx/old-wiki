## Overview

The SPDX Legal group will be holding a special break out session to
review a number of software examples where the current 2013 SPDX
licensing language syntax (i.e., license list + AND/OR operators) may
not be sufficient to represent the licensing terms of the software
generally. For instance the group will be looking at the many various
kinds of special exception terms, the use of the ‘+’ in license names
and programs derived from multiple source and library files, where each
is potentially under a different license. The group will report back to
the Legal and Tech working groups with its findings.

## The Problem

SPDX data creators utilize an informally defined mechanism to represent
the licensing terms of various different copyrightable software items
such as source files, programs, libraries, packages, images, fonts,
documentation and so forth. The current mechanism informally consists of
the following parts:

1.  a license list with standard short names (e.g., constants such as
    GPL-2.0, BSD-2-Clause )
2.  a mechanism to define custom licenses - i,e., licenses not found on
    the standard license list (e.g., LicenseRef-23)
3.  a simple collection of boolean expression operators (e.g., AND and
    OR). Potential others may be needed (e.g., WITH-EXCEPTION, +)
4.  Use of parenthesis to establish order of precedence - e.g., (MIT AND
    (GPL-2.0 OR BSD-2-Clause))

I refer to the current approach as informal because different parts were
designed separately and all the parts have never been summarized
holistically - i.e., that is, viewed as a single system. Some of these
parts are define in the SPDX spec (e.g. operators AND and OR,
LicenseRefs) while others are maintained in a separate license list
(e.g., constants LGPL-2.0, BSD-2-Clause, GPL-2.0+) and yet other parts
have been used but never formally defined (e.g., use of parenthesis).

What is missing is:

  - A formal description of a well thought out license expression
    language with more rigorous consideration and presentation of how
    the different components (e.g., operators and operands) can be
    combined to represent the licensing terms of most copyrightable
    software items (e.g., programs, images, packages, ...). For example,
    the creation of a single document that presents a holistic overview
    of the licensing expression mechanism with many insightful examples
    of source files, image files, libraries and packages and so forth.
  - A process by which additions, deletions and modifications can be
    made to the a formal license expression language over time enabling
    it to formally evolve.
  - A process to test (validate) the current (and future) constructs of
    a license expression language to ensure they are sufficiently
    expressive to represent most software licensing situations.

The existing informal mechanism currently used largely evolved based on
intuition of various anecdotal situations. The objective here is to
pursue a more thoughtful and disciplined approach of what a an
effectively expressive licensing mechanism might include. The licensing
expression language after all is one of the most important conceptual
components of the SPDX specification.

## Observations/Considerations (with Examples)

This section provides a brainstorming blackboard to record a myriad of
observations and considerations to collectively help us understand the
various issues and facilitate the selection of issues to focus on. Think
of it as a broad casting feedback net where a fair amount of stuff
caught in the net may be discarded.

  - There are various different GPL special exceptions not represented
    in the license list. What is the criteria for adding them to the
    license list? What about special exceptions for other licenses.
  - GPL-3.0, a particularly important license, has several additional
    optional terms, Section 7 (a)-(f), that are not represented in the
    license list. Should they be represented in the list? Should they be
    represented as exceptions?
  - What precisely is the GPL-2.0-only issue that Bradley Kuhn has
    raised. Examples?
  - Do we need a formal definition of what exactly a license on the
    license list is. For example:
      - Does it have to be an Open source license? What is the
        definition of an Open Source license (on the OSI list? Satisfies
        the OSI's ten requirements for an open source license?)
      - Is the list used largely for identification purposes? Should the
        list include friend commercial licenses that are widely used?
      - Does GPL-2.0+ really represent a license or is it more
        representative of as multi-license choice such as: GPL-2.0 OR
        GPL-3.0?
      - Should we allow the + to be applied to any license? For example,
        EPL-1.0+?
      - Do we make a clear distinction between a file license notice and
        a license? Although a notice can (and often does) represent a
        single license, notices be dynamically expressive where a
        license tends to be a more rigid entity.
  - Although we do want to resist removing licenses from the license
    list, it may be required under certain circumstances in order to get
    to a better place in the medium to long run. The inclusion of the
    LicenseListVersion field in the SPDX spec 1.2 does allow this to be
    done in a relatively clean way.
  - What is the right level of description for a package license? What
    does a package license mean? Should the concluded license be the
    conjunction of all the licenses found in the package? What if a
    package license is not compatible with one of more of the licenses
    of the files in the package?

## Requirements (Proposal/Draft)

Here we present a list of "potential" requirements for a licensing
expression language should support. For the sake of completeness, we
include requirements that are potentially already supported in the
current informal approach. Some potential requirements include:

  - Define the concept of a license expression operator (e.g., OR and
    AND)
  - Define the concept of a license expression operand as either a
    single license constant (e.g., LGPL-2.1, LicenseRef-23) or cont
  - Define the notion of a license expression. For example, a license
    expression can consist of a single operand license constant or an
    expression constructed by applying one or more operators
  - Effectively (and potentially elegantly) represent the myriad of
    different special exception cases (e.g., GPL-2.0+ with Bison
    Exception, )
  - Disjunctive license expression support - ability to define a
    multiple license choices (currently supported by OR operator)
  - Conjunctive License support - ability to define a situation where
    multiple licenses apply (currently supported by AND operator)
  - Provide an effective way to allow one to describe custom licenses
    (e.g., LicenseRef approach).
  - Supporting the licensing of images and fonts. For example, does the
    license list include licenses to cover non source items found in
    software.
  - Need to give the formal mechanism a formal name (e.g. SPDX Licensing
    Expression Language (SLEL)) so that it has a more formal existence
    and standing.

## Examples

Example file notices that are not easily represented using the current
license list and just AND/OR can be found here: [ File Notice
Examples](FileNoticeExamples "wikilink")

## Maintainer

10/2013 - Mark Gisi - Contact Mark if you cannot edit this wiki but
would like to contribute to the discussion (Mark.Gisi AT WindRiver dot
COM).
