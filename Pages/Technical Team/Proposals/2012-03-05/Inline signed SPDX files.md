Status: draft

## Issue

Currently there is no way to be sure that an SPDX file has not been
modified by a third party after it was produced. See also,
[issue 980](https://bugs.linuxfoundation.org/show_bug.cgi?id=980).

## Proposal

Modify the spec to state that allow SPDX producers **may**
cryptographically sign SPDX files using the PGP clear text signature
format. This format embeds a clear text version of the file to be signed
inside of a text based wrapper which contains the cryptographic
signature. SPDX consumers **must** accept signed SPDX files, but would
**not** be required to authenticate any signatures. SPDX producers would
have the option of signing SPDX files but would **not** be required to
do so.

## Example

### SPDX file

`   SPDXVersion: SPDX-1.0`  
`   DataLicense: PDDL-1.0`  
`   Creator: Person: Peter Williams`

### Signed SPDX file

`   -----BEGIN PGP SIGNED MESSAGE-----`  
`   Hash: SHA1`  
`   `  
`   SPDXVersion: SPDX-1.0`  
`   DataLicense: PDDL-1.0`  
`   Creator: Person: Peter Williams`  
`   -----BEGIN PGP SIGNATURE-----`  
`   Version: GnuPG v1.4.11 (Darwin)`  
`   `  
`   iQEcBAEBAgAGBQJPVZO9AAoJENTSLvN5TFz940UH/j2/dys3uK6VTqnNBi/yQQxQ`  
`   sp/+wBhJThQ4qzph2Zy4pmpjX4u9iwuaIvkOigYp/XR8sdJExQSSSxLxgkfPokRG`  
`   4dN8YRZyQ3fTVuCz5DPas9B4NCcZTn77nB8Gas4wzyli7Pqu3YKfq81sfIyxnC+G`  
`   /LIMidJ6JD9mvcLmgsbz5zDwmEFnafXcgocK0d9Fbhvx6MKPK7dFxdQ9oN1lV9Ej`  
`   hED+wpGIQSSdSJBc2udKAxPZHFQxOTHHr8flxC6bzq01xyjm0W2hDDd0jKRN/cqZ`  
`   o10Une5wEO/p7UqFDoNh++kLJeODJ2ZKLr4qwrGXODKLDd5F8ZdDB8deuIb/7RM=`  
`   =jdOZ`  
`   -----END PGP SIGNATURE-----`

##### Command sign an SPDX file

`   $ gpg --clearsign sample.spdx`

## Advantages

Embedding the signature in the the SPDX file has several advantages. The
combination of the data and its signature reduce the possibility that
the two will be accidentally separated as the SPDX data is passed from
person to person. Such a separation could happen if an SPDX signature
file is simply forgotten, or it could happen very easily if the name of
an SPDX file ever needs to be changed. Having that data together will
also make tooling easier to build because finding the signature data
will be less error prone. Embedding the signature prevents large classes
of mistakes from occurring and as such removes the need to cope with
them.

## Compatibility

This proposal will produce files that are not backwards compatible.
Specifically a signed filed will not be readable by SPDX-1.0 compliant
consumers. However, files produced by SPDX-1.0 compliant tools will
continue to be valid SPDX files and tools that support signing, as
described above, will be able to consume SPDX-1.0 files with no changes.

[Category:Technical](Category:Technical "wikilink")
