A desire has been expressed to be able to have SPDX be capable of
expressing

1.  [Provenance](Technical_Team/SDPX_2.0_Provenance "wikilink") (we can
    know precisely who said what and when about a package)
2.  Hiearchy and Aggregation ( package A contains packages B, C, etc)
3.  How software flows through a supply chain (upstream to packager,
    through several intermediate vendors to consumer)

A rough example of this thought is shown in the diagram below, showing
how the coreutils package might be represented:

![spdxdoodle-0.jpg](spdxdoodle-0.jpg "spdxdoodle-0.jpg")

The simple story behind this diagram is this:

1.  The upstream maintainer of coreutils provides an SPDX file which
    1.  Provides information for the copyrighted entity that is the
        package as a whole
    2.  Provides embedded information for the copyrighted entity that is
        each file in the package (same format, just embedded and clearly
        down hiearchy)
    3.  Provides a coreutils.spdx.sig file with the signature for the
        coreutils.spdx file (so we can authenticate it)
2.  This coreutils.spdx file is in the coreutils.tar.gz for the upstream
3.  The rpm (or deb) packager creates a coreutils.spdx (distinct from
    the one for the upstream) in the rpm file which:
    1.  Provides information for the copyrighted entity that is the rpm
        (or deb) package as a whole
    2.  Provides embedded information for the copyrighted entity that is
        each file (such as patch files) contained in the rpm (or deb)
        package
    3.  For the coreutils.tar.gz file (also contained in the rpm or deb
        package), provides it's SPDX information by \*referencing\* the
        coreutils.spdx in the coreutils.tar.gz file.
    4.  Optionally provides and Annotation section to 'annotate' some of
        the information provided by the coreutils upstream.

Diagram for a Concrete proposal (very very rough) for structure (note,
notes that say 'Concrete' or 'Referential' are just indicating an 'or'
in the doc structure):

![spdxdoodle2-1.jpg](spdxdoodle2-1.jpg "spdxdoodle2-1.jpg")

Description of diagram

  - **Top:** Simple top level place to start
  - **SPDXFile**: File containing SPDX data
  - **SPDXElement:** The containing element for SPDX data for a given
    copyrightable work contained in the SPDXFile. It's SPDXElements all
    the way down.
  - **Specifier:** Not really a node, sort of a grouper of nodes to
    indicate those fields which specify the 'thing' the SPDX Element is
    about
  - **LicenseData**: not really a node, sort of a grouper of nodes to
    indicate those fields which specify what we know about the 'thing'
    this SPDX Element is about
  - **SPDXElements:** zero or more additional 'contained' SPDX Elements
    referring to contained things (like files, or contained tarballs
    etc).
  - **Annotations:** zero or more annotations indicating additional
    information about the contained SPDXElements (to handle the case
    where a contained SPDX Element represents a reference to a another
    SPDX file that is signed and thus we can't change directly) - Note,
    we need more thought here.
  - '''Creator (Annotation): '''Equivalent to SPDX 1.0 Creation
    Information Creator
  - '''Date (Annotation): '''Equivalent to SPDX 1.0 Creation Information
    Created
  - **Comment (Annotation):** Equivalent to SPDX 1.0 Creation
    Information Creator Comment
  - **AssertNewLicense (Annotation):** Reference to new License Data you
    wish to assert to override existing SPDX License Data. Generally
    used in situations when we have existing License Data from a more
    primary source but we believe we have reason to believe otherwise.
  - **Name**: Equivalent to SPDX 1.0 Formal Name
  - **Version:** Equivalent to SPDX 1.0 Package Version Information
  - **Supplier:** Equivalent to SPDX 1.0 Package Supplier
  - **Summary:** Equivalent to SPDX 1.0 Package Summary Description
  - **Description:** Equivalent to SPDX 1.0 Package Detailed Description
  - **URI (in SPDXElement-\>Specifier):** URI of the copyrightable thing
    being referenced, may point to a file, an archive, a package, etc.
  - '''URICheckSum( in SPDXElement-\>Specifier): '''Checksum for the
    thing URI points to
  - '''CopyrightText: '''Equivalent to SPDX 1.0 CopyrightText
  - '''LicenseText: '''Full text of license if LicenseShortForm isn't
    available
  - '''LicenseShortForm: '''License short form in lew of license text if
    available
  - '''SPDXFileURI: '''If the SPDX Element does not contain it's own
    concrete license data but references an external SPDX File... the
    URI of that SPDXFile
  - '''SPDXFileSigURI: '''If the SPDX Element references an external
    SPDXFile, the URI of the sig file for that SPDX file
  - **ACL:** I hate the name ACL, but basically it's a way of specifying
    that you are including or excluding some of the copyrightable bits
    that are covered by the referenced SPDX File.
  - '''Exclude (in ACL): '''Used to specify parts of the stuff
    referenced by the external SPDX file you are not bring in. So if I
    am using all of a package, but not foo.c or bar.c.
  - **ExcludeAll (in ACL):** Used to indicate that \*none\* of the
    referenced copyrightable items from the SPDX file are used except
    those explicitely included.
  - '''Include (in ACL): '''Used after an excludeall to indicate we are
    only using the specifically included files... say we are just using
    foobar.c for example.
  - **SPDXFileSig**: Separate file containing the signature for the
    octets of the SPDXFile

This can also be visualized with a UMLish diagram:

![spdxdoodle-2.jpg](spdxdoodle-2.jpg "spdxdoodle-2.jpg")

Mapping SPDX 1.0 Fields to Proposal

| SPDX 1.0                           | SPDX 2.0 Proposal                   | Notes                 |
| ---------------------------------- | ----------------------------------- | --------------------- |
| Section                            | Field                               | Element               |
| Document Information               | Version                             | SPDX                  |
| Document Information               | Data License                        |                       |
| Creation Information               | Creator                             | Annotation            |
| Creation Information               | Created                             | Annotation            |
| Creation Information               | Comment                             | Annotation            |
| Package Information                | Formal Name                         | Concrete Specifier    |
| Package Information                | Package Version Information         | Concrete Specifier    |
| Package Information                | Package File Name                   |                       |
| Package Information                | Package Supplier                    | Concrete Specifier    |
| Package Information                | Package Originator                  |                       |
| Package Information                | Package Download Location           |                       |
| Package Information                | Package Verification Code           |                       |
| Package Information                | Package Checksum                    |                       |
| Package Information                | Source Information                  |                       |
| Package Information                | Concluded License                   | License Data          |
| Package Information                | All Licenses Information From Files |                       |
| Package Information                | Declared License                    | License Data          |
| Package Information                | Comments on License                 |                       |
| Package Information                | Copyright Text                      |                       |
| Package Information                | Package Summary Description         | Concrete Specifier    |
| Package Information                | Package Detailed Description        | Concrete Specifier    |
| Other License Information Detected | Identifier Assigned                 |                       |
| Other License Information Detected | Extracted Text                      | License Data          |
| File Information                   | File Name                           | Referential Specifier |
| File Information                   | File Type                           |                       |
| File Information                   | File Checksum                       | Referential Specifier |
| File Information                   | Concluded License                   | License Data          |
| File Information                   | License Information in File         | License Data          |
| File Information                   | Comment on License                  |                       |
| File Information                   | Copyright Text                      |                       |
| File Information                   | Artifact of Project Name            |                       |
| File Information                   | Artifact of Project Homepage        |                       |
| File Information                   | Artifact of Project URI             |                       |
| Review Information                 | Reviewer                            | Annotation            |
| Review Information                 | Review Date                         | Annotation            |
| Review Information                 | Comments                            | Annotation            |

Stealing Java's archive URI syntax:

In the java world, they commonly use a URI syntax
\<archivename\>\!\<filename\> to indicate a particular file within an
archive, for example foo.tar.gz\!bar.c. I suggest we use this (as there
are no other widespread alternatives).

Archiving multiple SPDX files:

It may be desirable to archive together multiple SPDX files so that we
have full resolvability for a given package. In that case, those should
be rolled into a specific archive format (say foo.spdx.zip) with the
various spdx files, their sig files, and an index file. The index file
should map URIs (as specified the SPDX files) to filenames in the
archive (so we can resolve them).

Example:

<file://coreutils.tar.gz!coreutils.spdx>:
<file://upstream/coreutils.spdx>

<file://coreutils.tar.gz!coreutils.spdx.sig>
<file://upstream/coreutils.spdx.sig>

Note: We have to also solve the problem here of how to distinguish when
two spdx files contain the same URI (say relative to their archives) but
they actually need to be resolved to separate files in the rollup, say
if both upstream and the rpm (or deb) packager used
<file://coreutils.spdx>

[Category:Technical](Category:Technical "wikilink")
