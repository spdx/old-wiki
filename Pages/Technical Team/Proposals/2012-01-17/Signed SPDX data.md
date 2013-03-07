Status: rejected

## Issue

Currently there is no way to be sure that an SPDX file has not been
modified by a third party after it was produced. See also,
[issue 980](https://bugs.linuxfoundation.org/show_bug.cgi?id=980).

## Proposal

Modify the spec to allow SPDX producers to cryptographically sign SPDX
files with an x.509 certificate using the `multipart/signed` format.
This format embeds a clear text version of the file to be signed inside
of a text based wrapper which contains the cryptographic signature. SPDX
consumers would be required to accept signed SPDX files, but would
**not** be required to authenticate any signatures. SPDX producers would
have the option of signing SPDX files but would **not** be required to
do so.

The S/MIME and x.509 certificates are widely deployed, well tested and
standardized way to provide cryptographically secure message
authentication and non-repudiation. The relevant documents are
[RFC 3851](http://tools.ietf.org/html/rfc3851) and
[RFC 3850](http://tools.ietf.org/html/rfc3850). The resulting files are
easy to process using widely available tooling both programmatically and
manually.

The SPDX data would be embedded in the file in clear text which means
specific tooling is only needed when signature authentication is
required. Combining the signature and the SPDX data will simplify
tooling to authenticate files and reduce the chances that signatures
will be accedentally removed from an SPDX dataset.

## Compatibility

This proposal will produce files that are not backwards compatible.
Specifically a signed filed will not be readable by SPDX-1.0 compliant
consumers. However, files produced by SPDX-1.0 compliant tools will
continue to be valid SPDX files and tools that support signing, as
described above, will be able to consume SPDX-1.0 files with no changes.

[Category:Technical](Category:Technical "wikilink")
