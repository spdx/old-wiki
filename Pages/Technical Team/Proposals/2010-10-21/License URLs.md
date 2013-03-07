Status: open

## Issue

URLs for licenses are not represented in SPDX.

## Proposal

Define property whose value is the URI of the license text as maintained
by the author of the license. Define property whose value is the URI of
alternate locations of the license text, for example the OSI page for
the license.

## Addition to spec

4.3 authorsUrl

Purpose: Provide links to web pages containing the license text as
maintained by the license author.

Cardinality: optional, 0 or more

Data format: xsd:anyURI

4.4 alternativeUrl

Purpose: Provide links to web pages containing the license text that are
maintained by organizations other than the license author. For example
the license page maintained by OSI.

Cardinality: optional, 0 or more

Data format: xsd:anyURI

[Category:Technical](Category:Technical "wikilink")
