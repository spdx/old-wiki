Usage Relationship Proposal The current Merged Model proposal (as of 21
Nov. 2013) includes a Usage property in the SPDX element and separate
SPDXElementRelationship object with a relationship type property.

This proposal is to move the Usage property to the
SPDXRelationshipObject.

## Background

During the usage case reviews against the proposed models at Linux
Collab Summit 2012, we decided to add a Usage property to the
SPDXElement. This was a key addition to supporting several use cases
(including 9.1 Yocto builds, 9.2.1 Building only license compliant
artifacts, 10.4 application ships with documentation + media +
software). At the time, we though of the usage as an attribute of the
SPDXElement.

During a follow-up discussion on the model, it was pointed out that
usage has more to with a relationship than the element itself. In other
words, an SPDX element all by itself does not have a usage. The usage is
only meaningful in the context of "what is using it".

If we change the definition of Usage to be the "Intended Use" by the
author of the SPDXEelement, having a property associated with the
element itself makes sense. From a license obligation perspective,
however, it is more important to capture how an element is actually
used. This can only be done if the usage is part of the relationship
object.

In the current SPDX 1.2 spec, there is an implied relationship between
SPDX File and the SPDX Package. To capture the usage of files within a
package, we could make that relationshp explicit in SPDX 2.0 by added
relationships between the file and the package.

Once Usage is added to the relationship, the relationship type
properties has a lot of overlap with relationship type.

## Proposal Specifics

  - Remove Usage from SPDXElement
  - Add Usage to SPDXElementRelationship
  - Remove RelationshipType from SPDXElementRelationship
  - Update the Usage to merge in the relationship types and Usage
  - Make the relationship between the SPDX Package and SPDX files
    explicit (no update to the model, but would be an implementation
    requirement)

## Variations on a Theme

Following are some alternatives to the above proposal

  - Retain a Usage property in SPDX element renaming to "IntendedUsage"
    (also retain a Usage property in SPDXElementRelationship)
  - Retain the RelationshipType in SPDXElement and add a Usage property
    as well. Would need to distinguish the definition of these two
    properties.
