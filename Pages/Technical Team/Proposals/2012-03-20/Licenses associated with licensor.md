Status: draft

## Issue

[Bug 1000](https://bugs.linuxfoundation.org/show_bug.cgi?id=1000)

To correctly fulfill the terms of some licenses you must know who the
licensor is. Currently SPDX has no way to represent this in the
situation where there are multiple licenses.

## Proposal

Modify the spec in the following ways

  - Introduce a `LicenseDeclaration` entity type. Any number of
    instances of this type of entity would be allowing in an SPDX
    dataset.
  - A `LicenseDeclaration` entity would have zero or more `licensor`
    properties whose values are `Agent`s.
  - A `LicenseDeclaration` entity would have exactly one `licensing`
    property whose values is a `AnyLicenseInfo`.
  - A `LicenseDeclaration` entity would have zero or more `declarer`
    properties whose values are `Agent`s.
  - Allow the value of the `licenseConcluded` property to be a
    `LicenseDeclaration` in addition to the currently allowed
    `AnyLicenseInfo`.

[Category:Technical](Category:Technical "wikilink")
