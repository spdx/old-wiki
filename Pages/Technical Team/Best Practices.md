This is a place holder for working on the Best Practices document.

Best Practices

\_\_TOC\_\_

# Introduction

This wiki page represents a collection of best practices for editing and
review. Best practices will be taken from here, at appropriate
intervals, and made into an SPDX Technical report.

# Interpreting the Specification

Clarify and help with what is in the spec. Structure sections around the
spec?

# Tools

Best practices around using the SPDX tools

# Contributing to SPDX

how to provide feedback, get involved, etc

Jack: This should be moved to the website.

# Producing

SPDX Version: 1.2 PURPOSE: The SPDX specification is meant to stand on
its own and to make clear how a field is to be populated. Still, there
are times when more clarification is required. This tech note provides
clarification with regard to certain fields about which questions of
arisen. Some of these clarifications may be rolled into future versions
of the specification.

## Package Name (4.1)

The package name should be exclusive of version number. Field 4.2
Package Version is intended for version number and the package name
should not redundantly specify this information.

##### Example

Correct

  -   
    Package Name: glibc
    Package Version: 2.11.1

Incorrect

  -   
    Package Name: glibc **2.11.1**
    Package Version: 2.11.1

## Package Supplier (4.4); Package Originator (4.5); Source Information (4.10)

The first two fields are intended to where the package came from and
what entity created it. In many cases these will be one in the same, but
it is possible that the supplier may have gotten the package from
another source.

##### Example:

Wind River supplies the Linux kernel.

  -   
    Package Supplier: Wind River
    Package Originator: linux.org

Source Information is a freeform field, which, like many such fields in
SPDX is there to allow the document creator to provide information they
feel would be useful or important, but which my not fit neatly into the
specification.

## Package Download Location (4.6)

The intent of this field is to indicate the URL of the location from
which the package is actually obtained. Generally this should be the
originating site of the package, but in cases where the package was
obtained from a mirror site, the URL of the mirror should be used. The
format for the URL should follow RFC conventions, specifically RFC3986
or any newer one that may eventually augment or obsolete it.

In SPDX 2.0, when the codebase for an SPDX analysis is taken from a
Version Control System (VCS) best practice is to provide the specific
point in the VCS history from which the code was pulled. The Package
Download Location specifies syntax for several VCS systems (git, svn,
bzr, hg)

## Concluded License (4.11); Declared License (4.13)

In cases where there is a contradiction between the Declared License and
some other license present, the concluded license should represent that
contradiction, and best practice would be to explain further in the 4.14
Comments on License field.

**LEGAL TEAM SHOULD REVIEW THIS**

##### Example:

A GPL 2 package that contains files licensed under Apache 2.0.

  -   
    Declared License: GPL-2.0
    Concluded License: GPL-2.0 and Apache-2.0
    Comments on License: Several Apache licensed files (A, B, and C) are
    included in the packages causing an incompatibility with the
    licensing of the package.

## Extracted Text (5.2)

To clarify, or reinforce, the text included here, should be the exact
text in that is included with the package and no more. Some early SPDX
tools included full text of the relevant license even though the full
text was not supplied in the actual package. The example in the
specification is one where full text is included, but if the text is
incomplete, so should be the text in the Extracted Text field.

##### Example:

A copying file in the top level of the directory says, “This software is
licensed under the Beer License.”

Correct:

  -   
    Extracted Text: This software is licensed under the Beer-ware
    License

Incorrect:

  -   
    “THE BEER-WARE LICENSE" (Revision 42):\<phk@FreeBSD.ORG\> wrote this
    file. As long as you retain this notice you can do whatever you want
    with this stuff. If we meet some day, and you think this stuff is
    worth it, you can buy me a beer in return Poul-Henning Kam

## File Name (6.1)

To clarify, the format for the file name should follow URI RFC
conventions, specifically RFC3986 or any newer one that may eventually
augment or obsolete it. Specifically, it uses the relative path
reference format of an URI, and is defined as being relative to the root
of the package from which the file came.

In RFC3986, section 4.2, a relative path reference must not start with a
slash character ("/"). Relative references also do not need to start
with a "./" (dot slash), although there is one format for which the
preceding "./" is necessary. In any case, RFC3986 is clear about how to
handle dot-segments, and in the case of "./", it is simply removed.

##### Example:

Correct:

  -   
    FileName: ./package/foo.c
    FileName: package/foo.c

Incorrect:

  -   
    FileName: /package/foo.c
    FileName: //package/foo.c

Note about RFC3986:

  -   
    *This document obsoletes \[RFC2396\], which merged "Uniform Resource
    Locators" \[RFC1738\] and "Relative Uniform Resource Locators"
    \[RFC1808\] in order to define a single, generic syntax for all
    URIs.*

## Author vs. Creator (3.1) vs. Reviewer (7.1)

**Author:** The author is used occasionally in the text of the
specification and generally refers to the creator(s) of the package.
There is no explicit field for the author information other than
copyright information and URL, which may or may not reflect the actual
original author. In section 2.2.1, there is also a reference to an "SPDX
Author"; this actually refers to the SPDX Creator.

**Creator:** The SPDX Creator is defined in section 3.1 and is used to
identify who (or what, in the case of a tool) created the SPDX file.

**Reviewer:** The SPDX Reviewer is detined in section 7.1 and is used to
identify who reviewed the content of the SPDX.

To put things into context, let's consider the following flow:

1.  An author creates a package and assigns a license to it, hopefully
    to each individual file, and also follows all of the best practices
    and obligations for the chosen or found licenses in the package.
2.  An SPDX creator analyzes the content of the package, extracts the
    pertinent information and assembles the SPDX file, whether manually
    or using a tool.
3.  An SPDX reviewer inspects the work of the SPDX creator, whether
    manually or using a tool. Consider the reviewer to be anything from
    another set of eyes, to a recognized reliable entity with some kind
    of sign-off authority.

The SPDX creator is a mandatory parameter - every file must have its
creator. However, not every SPDX file is reviewed.

## Use of Parentheses in License Tag Fields

In the RDF object model, licenses can be defined to be nested
disjunctive or conjunctive sets in a very flexible manner. However, when
using the Tag value format, it is not clear how, if at all, one could
use the parentheses to define more complex licensing scenarios. It is
not the intention to restrict either one of the formats, hence we view
these additional examples as acceptable:

**Examples:**

Correct

  -   
    LicenseConcluded: LGPL-2.0
    LicenseConcluded: (LGPL-2.0 or LicenseRef-2)
    LicenseConcluded: (LGPL-2.0 and (LicenseRef-2 or LicenseRef-3))
    LicenseConcluded: ((LicenseRef-2 or (LicenseRef-3 and LicenseRef-4))
    and LGPL-2.0)

Incorrect

  -   
    LicenseConcluded: (LGPL-2.0)
    LicenseConcluded: LGPL-2.0 or LicenseRef-2
    LicenseConcluded: (LGPL-2.0 and LicenseRef-2 or LicenseRef-3)

Conceptually, much like in the RDF format, there are no limits to the
depth of nested license sets, although practically, more than 2 levels
are improbable.

This applies to all license fields.

# Consuming

Best practices around the process of doing it. Examples of how this is
done.

# Notes from LinuxCon 2013 17 Sept 2013

What should be in a best practices, how does it relate to the spec?

Possibilities:

  - examples
  - particular questions (sort of like a FAQ)
  - Could start with things that are not well defined but end up in the
    specification
  - I need a field for X, its not there, what field could I use?
  - best practices around the specification and best practices around
    contributing to SPDX. Maybe two documents?
  - Snapshot best practices document at intervals and post on site. Use
    wiki for active discussions, new proposals, etc.,.
  - Should we have a getting started guide?
  - best practices for meta tagging like u-boot did. maybe link it in
    here but should be separate page. Could possibly include other
    information for developers supporting spdx and producing spdx
    friendly code. Look at things like U-boot, Mozilla, etc.,.

  

# Examples

This section contains examples of working with SPDX documents. The
examples, unless otherwise noted, will focus on illustrating a single
concept or use case. The following projects are used throughout the use
cases to make digesting the use cases easier as you will not have to
continually re-familiarize yourself with a new application each time.

  - GNU CPIO version 2.10 - <http://mirror.sdunix.com/gnu/cpio/>
  - GNU Time version 1.7 - <http://mirror.sdunix.com/gnu/time/>
  - SPDX Tool - <http://git.spdx.org/spdx-tools.git/>

  

## Converting 1.2 to 2.0

This examples shows a application with a SPDX 1.2 document and then a
version of it using 2.0 and explains how one would convert.

Example Project: SPDX Tools - <https://github.com/spdx/>

  

## Simple 2.0 Document

This is a simple use case illustrating an SPDX 2.0 Document. The GNU
Time program uses a small number of files so its "easy" to get your head
around and how an spdx document could be generated.

Example project: GNU Time 1.7 <http://mirror.sdunix.com/gnu/time/>

  

## Using the SPDX License List

These are various real world examples of how people are incorporating
the SPDX License List.

| Who    | Link                                               | Description                                                                                                                                        |
| ------ | -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| GitHub | <https://developer.github.com/v3/licenses/>        | GitHub projects use the short identifiers from the license list to represent the licensing of their project.                                       |
| Yota   | <http://docs.yottabuild.org/reference/module.html> | Yota projects use the short identifiers from the license list and links back to the license list text to represent the licensing of their project. |

These are working notes:

  - a site which provides a pick list of SPDX licenses, and based on
    choice stores the declared license for an OSS project
  - an API for a site that returns the declared license of a project
    (e.g. github repo) in terms of SPDX license identifier
  - a LICENSES.TXT file in a codebase that states the licensing for the
    code referencing SPDX license identifiers
  - a comment section in a source file that states the licensing for the
    file referencing SPDX license identifiers
  - Package Managers / Distros that state licensing in files specific to
    that package manager
      - a package manager (e.g. Rubygems) that encourages use of SPDX
        identifiers by validating .gemspec files ?
      - a distro that encourages use of SPDX identifiers in their spec
        files (e.g. Debian DEP-5 format, while not an SPDX doc, can/may
        use SPDX license identifiers)?

  

## Relationships and Multiple SPDX Documents in one

GNU CPIO 2.10 - <http://mirror.sdunix.com/gnu/cpio/> Has source, test
code, documentation and its not "overly" large.

This example shows a single SPDX document for an application. Within
that document are multiple SPDX documents with relationships that
clarify the context the files are used in. Basically it is broken down
as follows:

| SPDX Document      | Relationships Used | Description Notes                                                                                                                        |
| ------------------ | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| CPIO Application   | CONTAINS           | The application contains "bundles" of things. E.g. source that built it, test code, documentation, etc.,. This is the umbrella document. |
| CPIO Source        | GENERATES          | This source is used to build the application.                                                                                            |
| CPIO Documentation | DOCUMENTATION\_OF  | These documents describe the application and hows to use it.                                                                             |
| CPIO Test          | TEST\_CASE\_OF     | This is test code for the application.                                                                                                   |
| CPIO Project       | BUILD\_TOOL\_OF    | These are project files.                                                                                                                 |

  

## External SPDX Documents

These examples show an SPDX document referencing another SPDX document.

### JAR File

Example project: SPDX Tool - <http://git.spdx.org/spdx-tools.git/>

This example shows an executable jar with an SPDX referencing back to
another SPDX document that describes the source that built it.

Ex 2:

  - original java source files (on apache.org)
  - repackaged java source files (from a distro)

Ex 3:

  - original java source files
  - patched (modified) java source files (having added a security fix)

  

## Annotations (replaces Reviewer Comments)

Example project: GNU Time 1.7 <http://mirror.sdunix.com/gnu/time/>

This example shows document for a simple application with reviewer
comments added after the fact.

  

## File Types

Jack: Example showing use of all file types, especially when there are
"choices".

“SOURCE” | “BINARY” | “ARCHIVE” | “APPLICATION” | “AUDIO” | “IMAGE” |
“TEXT” | “VIDEO” | “DOCUMENTATION” | “SPDX” | “OTHER”

2.0 Spec allows for multiple filetypes

  - a .jar file containing compiled .class files could be described as
    BINARY and ARCHIVE
  - a .java file could be both SOURCE TEXT
  - a binary PDF file could be BINARY DOCUMENTATION
