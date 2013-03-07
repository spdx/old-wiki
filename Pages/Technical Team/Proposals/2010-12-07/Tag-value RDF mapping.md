Status: draft

## Issue

The mechanism and details of how the tag-value format relates to the rdf
model are not clear. Also there are many special cases regarding now
following lines are parsed based on the tag. These issues combined with
the lack of an overview section on the tag-value format make it hard to
understand how the tag-value files should be produced.

'''''\<KES\>: *'it is one tag per data value all on the same line,
unless it is indicated as a multiple line field, in which case XML like
syntax was discussed as a way to be used to delimit it. Not sure why
this is so confusing? Are you looking at the WIKI or the .pdf? (WIKI
could be the source of the confusion due to its formatting
limiations...??? **)***

## Proposal

The direct relationship between the tags and rdf properties will be
stated explicitly. All simple tag names match rdf property name without
the spdx vocabulary prefix.

Arbitrary rdf properties will be allows to be tags when they are
enclosed in angle brackets ("\<", "\>"). This will support forward
compatibility and innovation by allowing vendor or communities to
introduce new data into spdx files.

'''\<KES\> ***Whoa, the only place we have buy in from the lawyers is in
the comment field. Introducing this notation, needs to be thought out, -
also this conflicts with the XML notation used to denote multiline
fields**'.*

A uniform way declare new resources (entities) and link to them will be
introduced. A new resource would be declared by enclosing the type of
the resource and it's uri, either full or a
[CURIE](http://www.w3.org/TR/2007/WD-curie-20070307/) or node-id if it
is a blank node, in square brackets ("\[", "\]"). The resource type will
be Package, File, Project or License

***\<KES\>** Positional order will give it, I'm not sure this is adding
value*

A uniform way to handle multiline values will be introduced. Any tag
value that started with double quote ('"') would extend until a second,
unescaped, double quote was encountered. If the content of the value
included a double quote it could be escaped by prefixing it with a back
slash character ("\\"). This will allow parsers to handle multiline
values on unrecognized fields which dramatically improves forward
compatibility.

Values would will be treated as literals unless the SPDX processor is
aware that the tag is declared as an owl:ObjectProperty. For
owl:ObjectProperty fields the SPDX processor can resolve the value into
a resource by first looking at the blank node ids in the document, if
the value does not match any of the declared node ids it should be
treated as a [CURIE](http://www.w3.org/TR/2007/WD-curie-20070307/) or
URI. For the purpose of CURIE resolution the following prefixes will be
defined: license (the SPDX license repo prefix), doap

The document itself will describe an SPDXDoc resource. All tags before
the first section header will be considered related to that SPDXDoc. An
SDPX tag-value file will contain exactly one Package resource. Any File
resources defined in the file well be assumed to be members the Files
list of the package described by the SPDX file.

### Example 1: Simple SPDX file with non-standard license

`   SPDXVersion: SPDX-1.0`  
`   CreatedBy: Tool: spdx-gen 1.0`

`   [Package `<http://oss.net/foo-1.0.tar.gz>`]`  
`   DeclaredLicense: FullLicense-1`  
`   DeclaredLicense: license:GPL2`  
`   Description: "This`  
`   is along`  
`   multiline value"`  
`   `  
`   `  
`   [License FullLicnse-1]`  
`   LicenseText: "`  
`   Some terms and conditions`  
`   "`  
`   `  
`   `  
`   This is what the current syntax would have us show for a package header.`  
`   It is fairly easily parseable, line breaks denote end of field,unless a `<text>`, `</text>` is encountered.`  
`   `  
`   There is no package field or tag at this point in the spec.   Assumption is one package per SPDX file`  
`   If we want to extend, then it could be done that all the files in a package must be listed before going`  
`   to the DeclaredName of next package.  Issue discussed before was file names, but we could say that all`  
`   files between DeclareName, and the next, belong to that DeclaredName.`  
`   `  
`   DeclaredName: Foo 1.0`  
`   MachineName: foo-1.0.tar.gz`  
`   SHA1: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`  
`   SPDXVerifier: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`  
`   URL: `<http://oss.net/foo-1.0.tar.gz>  
`   SourceInfo: links to specific version of libbar.o (2.57)`  
`   DeclaredLicense: FullLicense-1`  
`   DeclaredLicense: GPL-2.0`  
`   DetectedLicense: GPL-2.0`  
`   DetectedLicense: FullLicense-1`  
`   DetectedLicense: LGPL-2.0+`  
`   DetectedLicense: FullLicense-2`  
`   DeclaredCopyright: unknown`  
`   ShortDesc: `<text>` This is a`  
`   short multi line description`  
`   `</text>  
`   Description: `<text>` This is a`  
`   much longer,  (well sort of)`  
`   multi line description to be worked with`  
`   `</text>

### Example 2: Simple SPDX file with vendor specific tag

`   SPDXVersion: SPDX-1.0`  
`   CreatedBy: Tool: spdx-gen 1.0`  
`   `  
`   [Package `<http://oss.net/foo-1.0.tar.gz>`]`  
`   DeclaredLicense: license:GPL2`  
`   Description: "This`  
`   is a long`  
`   multiline value"`  
`   <`<http://example.org/sha256-signature>`>: "ac44f9eecaf832..."`

### Example 3: Simple SPDX file with files

`   SPDXVersion: SPDX-1.0`  
`   CreatedBy: Tool: spdx-gen 1.0`  
`   `  
`   [Package `<http://oss.net/foo-1.0.tar.gz>`]`  
`   DeclaredLicense: license:GPL2`  
`   Description: "This`  
`   is along`  
`   multiline value"`  
`   `  
`   [File `<http://oss.net/foo-1.0.tar.gz#foo.c>`]`  
`   Type: source`  
`   DetectedLicense: license:GPL2`  
`   `  
`   [File `<http://oss.net/foo-1.0.tar.gz#bar.c>`]`  
`   Type: source`  
`   DetectedLicense: license:GPL2`

### Example 4: Simple SPDX file with file and artifact info

`   SPDXVersion: SPDX-1.0`  
`   CreatedBy: Tool: spdx-gen 1.0`  
`   `  
`   [Package `<http://oss.net/foo-1.0.tar.gz>`]`  
`   DeclaredLicense: license:GPL2`  
`   Description: "This`  
`   is along`  
`   multiline value"`  
`   `  
`   [File `<http://oss.net/foo-1.0.tar.gz#foo.c>`]`  
`   Type: source`  
`   DetectedLicense: license:GPL2`  
`   ArtifactOf: JRandomProject`  
`    `  
`   [doap:Project JRandomProject]`  
`   doap:name: J Random Project`  
`   doap:homepage: `<http://oss.org/j-random-project>

[Category:Technical](Category:Technical "wikilink")
