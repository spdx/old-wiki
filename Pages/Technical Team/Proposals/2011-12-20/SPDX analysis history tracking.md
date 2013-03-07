Status: proposed

## Issue

Currently there is no way track relationships between SPDX datasets.

For example, PostgreSQL project is most licensed under an MIT like
license but has some code in the contrib directory which is GPL. If i
want a PostgreSQL without any GPL obligations i can simply build it
without the contrib directory. I can start with publicly available SPDX
dataset for PostgreSQL, remove all files in the contrib directory from
the dataset and save it as the SPDX dataset for my PostgreSQL w/o GPL
project.

If i do this there is no way for someone else to know that my SPDX data
is derived from the public PostgreSQL SPDX data. If any issues are found
in the public SPDX data they might effect my SPDX data also. Or if
someone found problems in my SPDX data it would be useful to track that
issue back to the original source and fix it there.

## Proposal

Add an optional property to `SpdxDocument` which would specify another
`SpdxDocument` from which it was derived. The
[`isVersionOf`](http://dublincore.org/usage/terms/history/#isVersionOf-003)
property in the Dublin Core vocabulary is widely used and has the
correct semantics.

### Example (Turtle RDF)

`   <`<http://example.com/spdx/postgresql-sans-contrib-9.1.2>`> a :SpdxDocument;`  
`     dc:isVersionOf <`<http://postgresql.org/spdx/9.1.2>`>; :describesPackage`

### Example (Tag)

`   IsVersionOf: `<http://postgresql.org/spdx/9.1.2>

The addition of this property would allow the history a particular SPDX
dataset to be determined by following the isVersionOf properties of each
`SpdxDocument`. Differences between any two `SpdxDocument`s could be
determined by comparing the two dataset.

## Compatibility

This change is fully backwards compatible for consumers that ignore
properties they do not understand.

[Category:Technical](Category:Technical "wikilink")
