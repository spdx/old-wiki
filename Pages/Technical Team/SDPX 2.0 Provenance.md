## Provenance

It is desirable to be able to know the provenance of SPDX data. This
means being able to reliably know who declared what SPDX information
when, and where applicable, for what reason.

Components of SPDX Provenance include

1.  Signing of SPDX Data

## SPDX Data Signing

Since SPDX Data can be represented in both RDF and Tag, and since there
is no standard mechanism for signing RDF or Tag data as such (as there
is in DSig for XML), we are left to fall back to signing the octets of
the file containing that SPDX data. This has a few implications:

1.  The signature must be a in a separate file from the SPDX file
    (Example: foo.spdx has foo.spdx.sig containing it's signature)
2.  The SPDX file, once signed, must not be changed by downstream
    consumers of the file (because to change its octets would be to
    invalidate the signature).

## SPDX Signing Proposal

SPDX files should optionally be signed using
[RFC 2440](http://www.ietf.org/rfc/rfc2440.txt) PGP ascii-armored
detached signatures.

## GPG Example

## Sign a file with GPG

`sjc-vpn2-814:~ hagbard$ gpg --armor --output example.txt.sig --detach-sig example.txt`

`You need a passphrase to unlock the secret key for`  
`user: "Ed Warnicke "`  
`1024-bit DSA key, ID 9AB88650, created 2001-09-09`

## See signature file

`sjc-vpn2-814:~ hagbard$ cat example.txt.sig`  
`-----BEGIN PGP SIGNATURE-----`  
`Version: GnuPG/MacGPG2 v2.0.17 (Darwin)`  
`Comment: GPGTools - `<http://gpgtools.org>  
  
`iEYEABECAAYFAk9NCpUACgkQpqzn7Jq4hlA3cACfUOxrlkISMjjLELGlLQuNn93h`  
`X6wAniliWFVoi7qfRGI79hwdLhajKcdI`  
`=0NsF`  
`-----END PGP SIGNATURE-----`

### Verify file with GPG

`sjc-vpn2-814:~ hagbard$ gpg --verify example.txt.sig example.txt`  
`gpg: Signature made Tue Feb 28 11:10:45 2012 CST using DSA key ID 9AB88650`  
`gpg: Good signature from "Ed Warnicke "`  
`gpg:                 aka "Ed Warnicke "`  
`Primary key fingerprint: 0B87 BC4A F6BF F571 FF9B  BF51 A6AC E7EC 9AB8 8650`

\==Implementation <Notes:==>

GPG is available for Linux, Mac, and Windows and provides PGP support.
PGP support is available via the Legion of the Bouncy Castle in Java,
and they provide an example
[DetachedSignatureProcessor](http://www.jarvana.com/jarvana/view/org/bouncycastle/bcpg-jdk15/1.45/bcpg-jdk15-1.45-javadoc.jar!/org/bouncycastle/openpgp/examples/DetachedSignatureProcessor.html)
in their openpgp examples section.

[Category:Technical](Category:Technical "wikilink")
