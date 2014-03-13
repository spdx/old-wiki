The file ![spdx-rdf-terms.zip](spdx-rdf-terms.zip "spdx-rdf-terms.zip")
contains an HTML file describing the RDF terms for the current SPDX 2.0
model.

This set of terms definitions assumes the following changes to the
model:

  - Move usage from element to relationship
  - Add usage enumerations
  - Add license comment to element
  - Add copyright to element
  - Annotation and Review are identical classes - shall we just abandon
    Annotation, or should we make it richer?
  - Verification code for an element needs definition - proposal to add
    name

The following list describes incompatibilities with SPDX 1.2:

  - packageVerificationCode replaced by verificationCode (could
    depricate, or could keep this in addition)
  - removed hasFile from package (replaced by a relationship)
  - removed describesPackage from SpdxDocument (replaced by a
    relationship) - could keep and deprecate?
  - removed file licenseInfoInFile - replaced by declared license
  - removed artifactOf - replaced by relationship
  - removed fileDependency - replaced by relationship
  - SpdxDocument has a bunch of extra stuff due to the subclass of
    SpdxElement

[Category:Technical](Category:Technical "wikilink")
