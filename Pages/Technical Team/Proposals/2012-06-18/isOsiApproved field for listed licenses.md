Status: open

## Issue

See also: [bug
\#1050](https://bugs.linuxfoundation.org/show_bug.cgi?id=1050)

The legal working group track whether each license has been approved by
the OSI. That information should be published as part of the official
license list.

## Proprosal

Add a boolean `isOsiApproved` property to the `License` class to
indicated whether the OSI has approved the license. Update the license
list web site to display this information and annotate it with RDFa so
that the information is machine readable.

## **Detailed Changes**

  - Add the following text to the [License class definition
    section](http://spdx.org/rdf/terms#License) of the RDF terms
    documentation:

`    * isOsiApproved`  
`      Cardinality: Mandatory, one`

  - Add the following text to the properties section of the RDF terms
    documentation immediately preceding the `licenseComments` section:

`Property: isOsiApproved`  
  
`Indicates if the Open Source Initiative has approved the`  
`license as being an open source license. A link to the OSI`  
`license page for this license should be provided use the`  
`seeAlso property when this property is affirmative.`  
  
`Status:`  
`  stable`  
`Domain:`  
`  License`  
`Range:`  
`  xsd:boolean`

  - Updated license list web site generator to display "Is OSI approved"
    after the "Other web pages for this license" info in the header
    block of license details pages.

[Category:Technical](Category:Technical "wikilink")
