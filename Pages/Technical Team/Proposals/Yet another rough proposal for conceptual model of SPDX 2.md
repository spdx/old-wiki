This conceptual model is an attempt to incrementally add hierarchy and
provenance capabilities to the existing SPDX model. Many of the [use
cases](Technical_Team/Use_Cases/2.0 "wikilink") have been considered but
further analysis is necessary to ensure that this model covers all
scenarios.

![conceptual-model-0.png](conceptual-model-0.png
"conceptual-model-0.png")

This model supports BOM structures by allowing the assertion that a file
in one package is the same entity as, or was built from, another package
or one or more files in another package. Reuse is supported by allowing
an SPDX file to include other SPDX files verbatim. Provenance of files
in the packages is supported by allowing explicit statements about who
possesses right for a files and under what licenses they allow copying.
The ability of a license declaration in an SPDX data set to supersede a
declaration in an included dataset allows for revision of the data while
maintaining a clear history of the data.

Reuse of SPDX data by inclusion of other SPDX files means that an SPDX
file would contain an rdf or tag-value encoded dataset for the
package(s) it directly describes, and additionally any number of other
SPDX files for components it contains. Those sub-packages might, in
turn, include other SPDX files.

![file-layout-0.png](file-layout-0.png "file-layout-0.png")

Provenance of the SPDX data is supported by allowing each SPDX dataset
to be cryptographically signed. Those signed datasets are included
verbatim so their sources are easily identified. Datasets are signed at
each level and those signatures enclose all the sub datasets so all the
analysis is covered by the signature.

[Category:Technical](Category:Technical "wikilink")
