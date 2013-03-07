Status: rejected

Alternative to
[Technical\_Team/Proposals/2010-10-21/artifactOf](Technical_Team/Proposals/2010-10-21/artifactOf "wikilink")

## Issue

The origin of a file is an important fact that is not described by and
spdx file.

## Proposal

Define a property of File whose value is name of the project in which
this file originated. Define a property of File whose value is URL of
the project in which this file originated.

## Additions to spec

5.6 OSS Project

5.6.1 Purpose: Identify the name of the open source package or project
where this file originated.

5.6.2 Intent: By providing the open source package, the reader can
better identify the source and use it to do further research if needed.

5.6.3 Cardinality: Optional, single instance

5.6.4 Tag: "Project"

5.6.5 RDF: /RDF/SPDXDoc/Describes/File/Project

5.6.6 Data Format: Freeform text string

5.6.7 Example: Project: jUnit

5.7 OSS Project URL

5.7.1 Purpose: Identify the project home page of the open source package
or project where this file originated.

5.7.2 Intent: By providing the URL for the open source package, the
reader can uniquely identify the source and use it to do further
research if needed.

5.7.3 Cardinality: Optional, single instance

5.7.4 Tag: "ProjectURL"

5.7.5 RDF: /RDF/SPDXDoc/Describes/File/ProjectURL

5.7.6 Data Format: URL

5.7.7 Example: Project: <http://www.junit.org>

[Category:Technical](Category:Technical "wikilink")
