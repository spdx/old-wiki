Status: obsolete (the [unary `+`
operator](https://spdx.org/spdx-specification-21-web-version#h.jxpfx0ykyb60)
allows you to declare this. See also more recent discussion in [Legal
Team/or-later-vs-unclear-disambiguation](Legal_Team/or-later-vs-unclear-disambiguation "wikilink"))

## Issue

There is not a way to express that the user may choose, at their
discretion, to following the terms and conditions of a specified license
or any later version of that license. In some ways this is similar to a
simple disjunctive licensing declaration. However, the set of licenses
changes over time so separate way of expressing this licensing
information is required.

## Use cases

The set of use cases we need to be able to describe in SPDX is:

  - A standard license of a particular version (such as GPL version 2)
    and every later version of that license
  - A non-standard license of a particular version and every later
    version of that license.
  - Unversioned license declaration (such as "GPL").

## Proposal

Introduce a license set, `LicenseOrLaterVersion` that explicitly
represents a specify license all its later versions. It would be left to
tools and/or humans to determine the actual licenses that should be
included in this set at any specific point in time.

The definition of \`License\` would not change. The \`DeclaredLicense\`
and \`DetectedLicense\` properties would be updated to allow their value
to be a \`License\` or \`LicenseOrLaterVersion\`.

KES: Still not clear why the "+" notation already in the short form
licenses is not sufficient. It seems its either a shortform or a once
of. Shortform has "+", and non standard licenses are copied verbatim and
this is not needed.

## Examples

### License or later version

` `<Package>  
`   `<DeclaredLicense>  
`     `<LicenseOrLaterVersion>  
`       `<BaseLicense rdf:resource="license:GPLv2" />  
`     `</LicenseOrLaterVersion>  
`   `</DeclaredLicense>  
` `</Package>

## Changes

These changes are available in the
['or-later-version-licensing](https://github.com/pezra/spdx-spec/tree/or-later-version-licensing)
branch of <https://github.com/pezra/spdx-spec.git>. A full version of
the spec with these changes is attached, as is a patch file to implement
these changes.

[Category:Technical](Category:Technical "wikilink")
