## Use cases from 1.0 discussions

[Technical Team/Old/Sandbox for Sharing
Examples](Technical_Team/Old/Sandbox_for_Sharing_Examples "wikilink")

## Use Cases to consider for SPDX 2.0 - working draft

Source code for SPDX-tools are available at:
<https://github.com/goneall/SPDX-Tools>

Use case details:
<http://pad.ubuntu.com/spdx-tech--use-case-embedded-java-jar>

(The way I am thinking about the use cases is there are 2 different
groups of use cases which I am calling scenarios. From what I can think
of the same solutions should work for both scenarios, but there may be
value in keeping these 2 scenarios in mind while working through the
detailed use cases)

High level general use case Scenarios: A: Embedded Packages (a typical
"Audit" scenario)

  - Actors:
      - Package Supplier: person or entity supplying the package
        represented by the highest lievel SPDX document
      - Package Consumer: person or entity using the package represented
        by the highest level SPDX document

Use Cases:

  - embedded java jar
  - embedded source distribution
  - embedded source with unused contrib library
  - embedded build tools

B: Package Supply Chain

  - Actors:
      - Package Originator: Original supplier of a package represented
        by an SPDX document - likely (but not always) the creator
      - Intermediate Packager: person or entity that redistributes an
        original package with its own SPDX document
      - End Package Consumer: The consumer of the final package in the
        supply chain - note that the same entity or person can be both
        an End Package Consumer and an Intermediate Packager
  - Use Cases:
      - simple redistribution
      - package aggregation
      - modified redistribution
      - patches provided to existing (already distributed) package
      - appstore

Use Case: embedded source Givens:

1.  Given a pre-existing source tarball (commons-logging-1.1.1.tar.gz)
    with an SPDX document is available for re-use
2.  Given: To build MyApp which re-uses it, commons-logging-1.1.1.tar.gz
    gets expanded somewhere into the MyApp source tree

Problem: Create an SPDX analysis of MyApp that can reference the
pre-existing SPDX document for commons-logging-1.1.1.tar.gz without
having to repeat all the info (e.g. every File node...) which was
already in the consumed SPDX document.

Discussion:

A package supplier includes another open source package in source form
(e.g. Apache Jakarta Commons Logging). The source code is unmodified and
intended to be compiled into the final solution by the Package Consumer.
The source code is in a distinct archive file (e.g.
commons-logging-1.1.1.tar.gz). The archive source file would be
represented as a single file in the highest level SPDX document. The
archive file would contain an SPDX document representing the embedded
source files.

Variation: the source code would be in its own distinct subdirectory
(e.g. source/java/org/apache/commons/logging/\*). In this variation, the
highest level SPDX document would detail all files within the embedded
package and the "artifact-of" property would reference the embedded
package.

Comment: (BillSchineller) - the use case of the supplier handing off a
tarball with accompanying (inside or 'sidecar'...) SPDX analysis/doc is
the Given. But the reality is that the consumer must crack it open and
expand its contents into the source tree for the build/compile step.

Use Case: embedded source with unused contrib library

Similar to embedded source except there would be source file known to
not be compiled into the resultant binaries of the final package, for
example the zlib contrib directory. Solution suggestion: the excluded
files could be represented in the SPDX documents with an "unused"
property and the license properties for the files would still be
represented in the SPDX document (exact mechanism TBD)

Use Case: embedded build tools A Package Supplier includes build
utilities (source, scripts, or binaries) which are only used to build
the resultant packages. The specific build tool files are represented in
the SPDX document with the appropriate license and and artifact-of
property which points to the origin of the tools. Solution suggestion: A
property could designate that this file is used as a tool.

Use Case: simple redistribution

An Intermediate Packager redistributes an original package without
source code modification. Additional meta data may be supplied by the
Intermediate Packager. Example - Debian packaging.

Use Case: package aggregation

An Intermediate Packager aggregates several open source packages into a
single distribution. Additional meta data is added. Example - Linux
distribution, Android, Ubuntu, Debian

Use Case: modified redistribution

An Intermediate Package redistributes a package from the Package
Originator with some modifications to the original code. These
modifications may impact the resultant licensing

Use Case: application store - how built and manifest, and how products
handled Pass through provider (Android Market Place, Apple Store),
Facebook app? Downloadable components (clients that are downloadable and
resident).

Use Case: patches provided to existing (already distributed) package -
An existing package with a pre-existing spdx document is patched. The
patch may contain additional licensing information

[Category:Technical](Category:Technical "wikilink")
[Category:Archived](Category:Archived "wikilink")
