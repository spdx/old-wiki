Status: draft

## Issue

In order to facilitate the delivery of multiple SPDX Data Files (and
possible
[Technical\_Team/Proposals/2012-06-06/Detached\_Signed\_SPDX\_Files](Technical_Team/Proposals/2012-06-06/Detached_Signed_SPDX_Files "wikilink"))
we need some standard way of grouping them together for simple transport
and delivery.

## Proposal

Modify the spec to state that

1.  '''Archive Format: '''When multiple SPDX Data Files need to be
    delivered together as a group, they should be archived in a Zip file
    format.
2.  '''Data & Signature File Grouping: '''When it is desirable to
    deliver one or more SPDX Data Files together with one or more
    related SPDX Data Signature files, the naming convention of
    [Technical\_Team/Proposals/2012-06-06/Detached\_Signed\_SPDX\_Files](Technical_Team/Proposals/2012-06-06/Detached_Signed_SPDX_Files "wikilink")
    should be followed.
3.  '''File Naming Convention: '''SPDX Archive files should be named
    \<filename\>.spdx.zip.

## Examples

### Example 1

`$ unzip -l example.spdx.zip`  
`Archive:  example.spdx.zip`  
`  Length     Date   Time    Name`  
` --------    ----   ----    ----`  
`        0  03-11-12 20:18   example.spdx`  
`        0  03-11-12 20:18   example.spdx.sign`  
` --------                   -------`  
`        0                   2 files`

### Example 2

`$ unzip -l example2.spdx.zip`  
`Archive:  example2.spdx.zip`  
`  Length     Date   Time    Name`  
` --------    ----   ----    ----`  
`        0  03-11-12 20:18   example.spdx`  
`        0  03-11-12 20:18   example.spdx.sign`  
`        0  03-11-12 20:21   example2.spdx`  
`        0  03-11-12 20:21   example2.spdx.sign`  
` --------                   -------`  
`        0                   4 files`

## Compatibility

Resulting \<filename\>.spdx.zip files will not be backward compatible
with SPDX 1.0 tooling. However, the SPDX Data Files they contain can be,
and can be easily extracted by ubiquitously available tools and libaries
are virtually every platform and in virtually every programming
language.

[Category:Technical](Category:Technical "wikilink")
