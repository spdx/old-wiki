Status: draft

## Issue

There are some licensing scenarios which are not expressable in SPDX.
For example, there is currently no way to express that a file can be
used under the licenses A and B or A and C.

## Use cases

The set of use cases we need to be able to describe in SPDX is:

1.  a single license
2.  choice of one from multiple single licenses
3.  multiple licenses (conjunctive)
4.  choice of one from multiple conjunctive license sets

## Proposal

Introduce a license set concept to cover all these use cases.
Specifically, a \`ConjunctiveLicenseSet\` and a
\`DisjunctiveLicenseSet\`. Members of these types of sets would be of
type \`License\`, \`ConjunctiveLicenseSet\` or
\`DisjunctiveLicenseSet\`. This would allow composing licensing
information in arbitrary conjunctive and disjunctive groupings.

The definition of \`License\` would not change. The \`DeclaredLicense\`
and \`DetectedLicense\` properties would be updated to allow their value
to be a \`License\`, \`ConjunctiveLicenseSet\`, or
\`DisjunctiveLicenseSet\`.

### Examples

#### Single license

`   `<Package>  
`     `<DeclaredLicense>  
`       `<rdf:Description rdf:about="license:GPL" />  
`     `</DeclaredLicense>  
`   `</Package>

#### Disjunctive licenses

`   `<Package>  
`     `<DeclaredLicense>  
`       `<ConjunctiveLicenseSet>  
`         `<licenses rdf:parseType="Collection">  
`           `<rdf:Description rdf:about="license:GPL" />  
`           `<rdf:Description rdf:about="license:BSD" />  
`         `</licenses>  
`       `</ConjunctiveLicenseSet>  
`     `</DeclaredLicense>  
`   `</Package>

#### Complex disjunctive licenses

`   `<Package>  
`     `<DeclaredLicense>  
`       `<DisjuntiveLicenseSet>  
`         `<licenses rdf:parseType="Collection">  
`           `<ConjunctiveLicenseSet>  
`             `<licenses rdf:parseType="Collection">  
`               `<rdf:Description rdf:about="license:GPL" />  
`               `<rdf:Description rdf:about="license:BSD" />  
`             `</licenses>  
`           `</ConjunctiveLicenseSet>  
`           `<ConjunctiveLicenseSet>  
`             `<licenses rdf:parseType="Collection">  
`               `<rdf:Description rdf:about="license:GPL" />  
`               `<rdf:Description rdf:about="license:Apache" />  
`             `</licenses>  
`           `</ConjunctiveLicenseSet>  
`         `</licenses>  
`       `</DisjuntiveLicenseSet>  
`     `</DeclaredLicense>  
`   `</Package>

## Changes

These changes are available in the
['composite-licensing'](https://github.com/pezra/spdx-spec/tree/compositeslicensing)
branch of <https://github.com/pezra/spdx-spec.git>. A full version of
the spec with these changes is attached, as is a patch file to implement
these changes.

[Category:Technical](Category:Technical "wikilink")
