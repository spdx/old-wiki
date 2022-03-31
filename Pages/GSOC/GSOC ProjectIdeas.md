  
<span style="font-size:150%">**Welcome to the 2022 SPDX Google Summer of
Code Project Page**</span>

See the [proposal
template](https://rtgdk.github.io/spdx-gsoc-proposal.html) if you are
interested in submitting a Google Summer of Code proposal.

Should you have questions please do not hesitate to contact one of the
mentors directly.

  
\_\_TOC\_\_

  

## What is SPDX ?

First and foremost we are a community dedicated to solving the issues
and problems around Open Source licensing and compliance. The SPDX work
group (part of the Linux Foundation) consists of individuals, community
members, and representatives from companies, foundations and
organizations who use or are considering using the SPDX standard. The
work group operates much like a meritocratic, consensus-based community
project; that is, anyone with an interest in the project can join the
community, contribute to the specification, and participate in the
decision-making process. We come from many different backgrounds
including open source developers, lawyers, consultants and business
professionals, many of who have been involved with license compliance
and identification for years.

As part of this effort we have developed a set of collateral that can be
used:

  - [License List and Short Identifiers](https://spdx.org/using-spdx)
  - [SPDX Specification for generating SPDX Documents in multiple
    formats](https://spdx.org/using-spdx)
  - [A set of basic tools for working with SPDX
    Documents](https://spdx.org/tools)
  - [License Identifiers in source](https://spdx.org/using-spdx)

## Why choose an SPDX Project?

Contributing to one of the SPDX projects below will provide a valuable
contribution to developers and/or users of open source software. We
believe you will find the projects both technically challenging and
rewarding. In essence we believe you will be able to look back one day
and I say I was part of that effort.

  

# Getting Involved

Beyond working with your mentor(s) we highly encourage students who
select one of these projects to get involved with the SPDX community via
our technical working group. Interaction with the technical team is
primarily done via its mailing list and on gitter (see resources). There
is however a weekly call you could join as well. .

## Resources

  - [SPDX website](http://spdx.org)
  - [SPDX Specification](https://spdx.org/specifications)
  - [SPDX Workgroup Tools webpage](https://spdx.org/tools)
  - [SPDX tech mailing
    list](https://lists.spdx.org/mailman/listinfo/spdx-tech)

# Ideas for 2022 Projects

## SBOM Conformance Checker

The goal of this project is to create a simple tool that checks whether
an SBOM (in SPDX format) conforms to NTIA's minimum elements guidance.

### Description

The SPDX Specification defines a number of fields (elements) that may
appear in an SBOM (Software Bill of Materials). Not all of them are
mandatory, however, so SBOMs in SPDX format can vary greatly.

While researching the attributes that have to be present in an SBOM,
NTIA came up with a guidance about the minimum elements that must appear
therein:
<https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf>

It would, therefore, be useful to have a tool that can determine whether
an SBOM stored in SPDX format fulfills all such minimum obligations.

The tool should make use of the already existing libraries for reading
SPDX documents

### Technologies

Python

### Duration

This will be a short (175 hours) project. It might be extended to a long
(350 hours) project if integration with the existing SPDX handling tools
(e.g., the Validation tool) is also implemented.

### Mentors

Dick Brooks, Kate Stewart

## Private license management system

A web-based system for managing license texts; similar to the SPDX
License List but oriented towards other private collections of licenses.

### Description

The goal of the project would be to create a simple web application for
people to upload license texts and automatically create a license
repository. The initial rough "functional specifications" describe it as
mainly an input form, where the information is entered. There will be
some automatic processing (e.g., canonicalization, duplicate avoidance,
etc.), a review/approval (and naming) step, and then publishing in a
specified format.

It should be noted that the specification is not yet finalized regarding
naming namespaces, way to publish licenses, etc. If the SPDX project has
already advanced in these definitions, this project will obviously
implement the decisions taken.

### Technologies

Python (any framework) for the back-end; JavaScript (any framework) for
the minimal front-end.

### Duration

This can be either a short (175 hours) project, implementing only the
basic functionality; or a long (350 hours) one, implementing more
functionality and automation.

### Mentors

Alexios Zavras; more TBD

## SBOM combiner

The project will result in a simple command-line tool that will be able
to “combine” information from a number of SBOMs into a comprehensive
SBOM that includes all the information of the provided ones. An actual
use case would be the generation of an SBOM for an actual software
delivery that is comprised by a number of components, each one of which
has its own correct SBOM.

### Description

The primary purpose of this tool would be to stitch together smaller
component-level SPDX documents and amalgamate them into one top-level
SPDX document representing a "sum of parts" piece of software. As an
initial pass for implementation, the component-level SBOMs would have to
be provided by the caller until the tool was advanced enough to fetch
SPDX Documents referenced by ExternalDocumenRef reliably.

### Technologies

Python (preferably); or Go.

### Duration

This will be a short (175 hours) project.

### Mentors

Rose Judge; others TBD

## Update of Java SPDX libraries to handle latest spec

### Description

The SPDX Project maintains a library, written in Java, for working with
SPDX data. The development of the library does not always follow the
development of the specification immediately. Since the specification
has evolved and a newer version is expected to be published right before
the timeframe of the project, it would be useful to have the standard
Java libraries capable of handling the latest spec.

The project will involve obviously understanding deeply the existing
libraries and extending them to handle the latest additions of the
specification (to the point of the published version).

### Technologies

Java; see <https://github.com/spdx/Spdx-Java-Library>

### Duration

This will be a short (175 hours) project.

### Mentors

TBD

## Update of Go SPDX libraries to handle latest spec

### Description

The SPDX Project maintains a library, written in Go, for working with
SPDX data. The development of the library does not always follow the
development of the specification immediately. Since the specification
has evolved and a newer version is expected to be published right before
the timeframe of the project, it would be useful to have the standard Go
libraries capable of handling the latest spec.

The project will involve obviously understanding deeply the existing
libraries and extending them to handle the latest additions of the
specification (to the point of the published version).

### Technologies

Go; see <https://github.com/spdx/tools-golang>

### Duration

This will be a short (175 hours) project.

### Mentors

TBD

## SPDX Golang RDF Saver

### Description

SPDX already has a Golang library to save RDF triples into a file/string
using the gordf project: <https://github.com/spdx/gordf>

The aim of this GSoC project would be to write an adapter in the SPDX
Golang Tools (the tools-golang repository at
<https://github.com/spdx/tools-golang>) that would take an SPDX Document
struct (see
<https://github.com/spdx/tools-golang/blob/main/spdx/document.go>) as an
input, and serialize it and its child elements into RDF triples to be
consumed by the aforementioned gordf rdf-writer.

### Technologies

Golang; RDF

### Duration

This will be a short (175 hours) project. If the project requires less
than 175 hours, remaining time can be spent on additional improvements
to the Golang tools.

### Mentors

Rishabh Bhatnagar; Steve Winslow as secondary / backup

## Update of Python SPDX libraries to handle latest spec

### Description

The SPDX Project maintains a library, written in Python, for working
with SPDX data. The development of the library does not always follow
the development of the specification immediately. Since the
specification has evolved and a newer version is expected to be
published right before the timeframe of the project, it would be useful
to have the standard Python libraries capable of handling the latest
spec.

The project will involve obviously understanding deeply the existing
libraries and extending them to handle the latest additions of the
specification (to the point of the published version).

### Technologies

Python; see <https://github.com/spdx/tools-python>

### Duration

This will be a short (175 hours) project.

### Mentors

TBD

## More to come...

Mentors: please fill out the following template for any projects you
wish to propose.

`=== Project Name ===`  
`add overview of project here`  
`====Skills Needed====`  
`what skills should the student have to do the coding exercises`  
`====Duration===`  
`whether this is a short or a long project`  
`====Background Information====`  
`context for the project and references to be studied`  
`====Available Mentors====`  
`list individuals who are willing to mentor and provide information about the project proposal.`

# Historical info

[GSOC/PastProjectIdeas](GSOC/PastProjectIdeas "wikilink")
