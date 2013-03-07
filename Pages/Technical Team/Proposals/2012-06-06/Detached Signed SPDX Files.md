Status: draft

## Issue

Currently there is no way to be sure that an SPDX file has not been
modified by a third party after it was produced. See also,
[issue 980](https://bugs.linuxfoundation.org/show_bug.cgi?id=980).

## Proposal

Modify the spec to state that

1.  '''Signing Convention: '''SPDX producers '''may '''
    cryptographically sign SPDX files using the PGP detached signature
    format as specified in RFC 2440. This format does not modify the
    original SPDX, but rather creates a separate \<filename\>.sig or
    \<filename\>.sign file containing a signature for the original file.
2.  '''Signature File Naming Convention: '''The signature filename
    should be either \<filename\>.sig or \<filename\>.sign and be in the
    same directory as the SPDX file.
3.  '''Signature File Renaming: '''Renames of an SPDX file from
    \<filename1\> to \<filename2\> should also rename any
    \<filename1\>.sig or \<filename1\>.sign files to \<filename2\>.sig
    or \<filename2\>.sign respectively.
4.  '''Consumption Optional: '''SPDX consumers **may** accept or ignore
    SPDX signature files.
5.  '''Production Optional: '''SPDX producers would have the option of
    signing SPDX files but would **not** be required to do so.

## Example

### SPDX file

`   SPDXVersion: SPDX-1.0`  
`   DataLicense: PDDL-1.0`  
`   Creator: Person: Ed Warnicke`

### Signed SPDX file

`   -----BEGIN PGP SIGNATURE-----`  
`   Version: GnuPG/MacGPG2 v2.0.17 (Darwin)`  
`   Comment: GPGTools - `<http://gpgtools.org>  
`   iEYEABECAAYFAk9WSn0ACgkQpqzn7Jq4hlCfYACbBelTUtjOGAYrSBXEODD9Ukpo`  
`   vuAAn2gLkGsGOntkUTERnISOyOoBJxlT`  
`   =JxE7`  
`   -----END PGP SIGNATURE -----`

### Command sign an SPDX file

`   $ gpg --armor --output example.spdx.sign --detach-sig example.spdx`

## Advantages

Detaching the signature in the SPDX file has several advantages.

1.  '''Leverage Existing Tools: '''It allows underlying tools that are
    used to process the formats into which SPDX is normally encoded (RDF
    tools, Tag Tools, XML Tools, etc) to continue to function normally.
2.  '''Tooling Simplication: '''It makes tooling for SPDX easier because
    it allows issues of file authentication to be considered
    orthogonally from other issues. A tool maker who \*just\* wants to
    focus on processing SPDX data does not need to worry about knowing
    how to unpack a wrapper.
3.  '''Community Standard: '''It follows the convention already being
    followed by kernel.org, mavencentral, the apache foundation, and
    most packagers.

## Disadvantages

Detaching the signature in the SPDX file could lead to

1.  '''Misplaced Signatures: '''Separation of the signature file from
    the SPDX file makes it possible for the signature to become
    separated from the SPDX file
2.  '''Signature Correlation: '''Separation of the signature file from
    the SPDX file introduces the need to correlate signature files with
    SPDX files.

<div>

## Responses to Disadvantages

1.  '''Misplaced Signatures -- Existing Archive Formats: '''SPDX
    signature files can be passed along with SPDX data files by simple
    archiving in a common archive format like .zip, providing all of the
    benefits of inline signatures, while retaining the advantages of
    detached signatures. This solution is proposed in
    [Technical\_Team/Proposals/2012-Mar-11\_SPDX\_File\_Aggregation](Technical_Team/Proposals/2012-Mar-11_SPDX_File_Aggregation "wikilink")
2.  '''Signature Correlation - Signature File Naming Convention: '''The
    SPDX signature file naming and placement conventions in the proposal
    eliminate concerns about correlation.

</div>

## Compatibility

This proposal will produce files that are trivially backwards
compatible. Specifically a signed filed will be readable by SPDX-1.0
compliant consumers and any tool capable of reading it's underlying
encoding format (RDF, XML, Tag). By making the issue of signing
orthogonal, we maintain separation of concerns.

[Category:Technical](Category:Technical "wikilink")
