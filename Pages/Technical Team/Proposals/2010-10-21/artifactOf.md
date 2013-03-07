Status: adopted

Alternative to
[Technical\_Team/Proposals/2010-10-21/File\_origin](Technical_Team/Proposals/2010-10-21/File_origin "wikilink")

## Issue

The origin of a file is an important fact that is not described by and
spdx file.

## Proposal

Define a property of File whose value is a DOAP Project. The DOAP
Project will contain the project name and homepage URL when they are
known. It also might also included more complete information regarding a
project, if such information is known. For more information regarding
DOAP see
[Wikipedia](http://en.wikipedia.org/wiki/Description_of_a_Project) and
[Schemapedia](http://schemapedia.com/schemas/doap)

Multiple instances of this property are allowed because the exact origin
of a file may be unclear. If a file was first created in a project A and
then copied and modified in project B the file version of the file in
project be would be an artifact of both projects A and B.

## Additions to spec

5.6 ArtifactOf

5.6.1 Purpose: Identify the project(s) of which this file is a part.

5.6.2 Intent: By providing data regarding the project(s) where this file
originated or occurs the reader can better identify the source and use
it to do further research if needed.

5.6.3 Cardinality: Optional, 0 or more.

5.6.4 Tag: "ArtifactOf"

5.6.5 RDF: /RDF/SPDXDoc/Describes/File/ArtifactOf

5.6.6 Data Format:

The value of this property is a doap:Project. For the RDF/XML format it
may be any valid doap:Project resource, including a URI reference. For
the tag value format project information is limited to name and
homepage. These tags are are semantically equivalent to doap:name and
doap:homepage properties, respectively. Either name or homepage may be
omitted in the tag value format.

5.6.7 Example:

`   ArtifactOf.name: JUnit`  
`   ArtifactOf.homepage: `<http://www.junit.org>

[Category:Technical](Category:Technical "wikilink")
