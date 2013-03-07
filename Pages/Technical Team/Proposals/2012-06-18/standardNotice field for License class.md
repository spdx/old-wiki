Status: open

## Issue

See [bug \#1049](https://bugs.linuxfoundation.org/show_bug.cgi?id=1049)

Standard licensing notices need to be published in a machine readable
way to facilitate the implementation of license text matching
guidelines.

## Proposal

Add a \`standardNotice\` property to the License class whose value is a
string. The cardinality of this property would be "Optional, zero or
one"

## Detailed Changes

  - No changes are required in the Tag-Value section of the spec
  - The follow text would be added the RDF terms document in the
    properties section of the the [License class
    details](http://spdx.org/rdf/terms#License):

`   * standardNotice`  
`      Cardinality: Optional, zero or one`

  - The following text would be added to the RDF terms document
    immediately before the [supplier
    section](http://spdx.org/rdf/terms#supplier) and an appropriate
    entry would be added to the properties index:

`  Property: standardNotice`  
`  `  
`  The block of text specified in the license as the preferred`  
`  way to declare that a work is covered by the terms of this`  
`  license.`  
`  `  
`  Status: stable`  
`  `  
`  Domain: License`  
`  `  
`  Range: xsd:string`

  - The license list web site generator would be updated to add a
    "Standard Notice" section after the "Text" section in the details
    pages of license for which one is known and would annotate the
    notice text with RDFa to make that information machine readable.

[Category:Technical](Category:Technical "wikilink")
