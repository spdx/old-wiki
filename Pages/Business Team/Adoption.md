DRAFT AS OF 28 August 2013 Currently it is a draft until we formulate
the plan at which time this sentence will be removed.

  

# Adoption

This page is being used to track the adoption of SPDX.

We will track adoption in three key areas:

  - SPDX License List
  - Generating or consuming SPDX Documents
  - Using SPDX meta tags in software

  

## License List

### Overview

The license list is a key component for SPDX. The SPDX License List
includes a standardized short identifier, full name for each license,
vetted license text, other basic information, and a canonical permanent
URL. By providing a short identifier, users can efficiently refer to a
license without having to redundantly reproduce the full license. For
more information on the License List see the [SPDX web
site](http://spdx.org/licenses/).

### Goals

We talked about one year goals. Should we have one and five?

  - \[proposal\] Tool adoption: 5 or more license management / open
    source tracking tools vendors utilize the SPDX license list
  - \[proposal\] Open Source Projects: 10 or more open source projects
    visibly utilize the SPDX license list in declaring licenses

### Metrics

For groups use one of the following. You can use multiple groups for an
entity.

  - Foundation (e.g. Linux Foundation, Free Software, Apache, Eclipse,
    etc).
  - Standards (e.g. OSI, W3C, etc).
  - Community (e.g. Community projects like Uboot, Kernel, Busy Box, GNU
    Compiler, etc).
  - Forge (e.g. Github, Sourceforge, etc).
  - Tools (e.g. open source community or company that has tools to
    generate or consume SPDX).
  - Company

| Entity                       | Group     | Notes                                                                                                    |
| :--------------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| Texas Instruments            | Company   | Using SPDX license identifiers on software BOMs delivered with products.                                 |
|                              |           |                                                                                                          |
| Wind River                   | Company   | Using SPDX license identifiers in Wind River Linux and we use internally as standard license references. |
|                              |           |                                                                                                          |
| Micro Focus                  | Company   | Using SPDX license identifiers internally as standard license references. (Tom Incorvia)                 |
|                              |           |                                                                                                          |
| Siemens                      | Company   | Using SPDX license identifiers internally as standard license references. (Roger Meier)                  |
|                              |           |                                                                                                          |
| Qualcomm                     | Company   | Using SPDX license identifiers internally as standard license references.                                |
|                              |           |                                                                                                          |
| Valeo                        | Company   | Using SPDX license identifiers internally as standard license references. Evaluating using format.       |
|                              |           |                                                                                                          |
| Black Duck                   | Tools     | Utilizes license list for references to licenses in Black Duck Suite.                                    |
|                              |           |                                                                                                          |
| nexB                         | Tools     | Utilizes license list for references to licenses in DejaCode.                                            |
|                              |           |                                                                                                          |
| Protecode                    | Tools     | Utilizes license list for references to licenses in Protecode Suite.                                     |
|                              |           |                                                                                                          |
| FOSSology                    | Tools     | Utilizes license list for references to licenses inside tool.                                            |
|                              |           |                                                                                                          |
| Open Source Initiative (OSI) | Standards | Adopted license list short names.                                                                        |
|                              |           |                                                                                                          |
| Composer                     | Community | Utilizes license list for references to licenses in PHP packages                                         |
|                              |           |                                                                                                          |
| Bower                        | Community | Utilizes license list for references to licenses in JavaScript packages                                  |
|                              |           |                                                                                                          |
| NPM                          | Community | Utilizes license list for references to licenses in NodeJS packages                                      |
|                              |           |                                                                                                          |
| Cargo                        | Community | Utilizes license list for references to licenses in Rust packages                                        |
|                              |           |                                                                                                          |
| RubyGems                     | Community | Utilizes license list for references to licenses in Ruby packages                                        |
|                              |           |                                                                                                          |

License List Adoption Tracking

  

## Generation and Consumption of SPDX Documents

### Overview

The SPDX specification is centered on the SPDX document. Creation and
consumption of SPDX documents is a key measure of success for the SPDX
standardization efforts.

### Goals

We talked about one year goals. Should we have one and five?

  - Proposal: At least one additional large open source organization
    provide SPDX documents by LinuxConn 2014

### Metrics

How we will measure adoption of this.

  - Proposal: Number of participants in the SPDX document "plugfest".
  - Proposal: Number of consuming organizations piloting use of SPDX
    documents as part of their governance process.
  - Proposal: Number of consuming organizations announcing adoption of
    SPDX as part of their governance process.
  - Proposal: Number of producing organizations posting SPDX format
    documents on the web.
  - Proposal: Number of large (more than 100 members) open source
    organizations producing SPDX documents (e.g. Linux Kernel, Apache,
    Eclipse).

For groups use one of the following. You can use multiple groups for an
entity.

  - Foundation (e.g. Linux Foundation, Free Software, Apache, Eclipse,
    etc).
  - Standards (e.g. OSI, W3C, etc).
  - Community (e.g. Community projects like Uboot, Kernel, Busy Box, GNU
    Compiler, etc).
  - Forge (e.g. Github, Sourceforge, etc).
  - Tools (e.g. open source community or company that has tools to
    generate or consume SPDX).
  - Company

| Entity            | Group   | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| :---------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Texas Instruments | Company | Limited internal generation of SPDX documents. We are have started shipping some SPDX documents with specific software products.                                                                                                                                                                                                                                                                                                                   |
|                   |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Wind River        | Company | 100% SPDX doc generation - both hi-def (human expert) and low-def (automation); Free SPDX cloud generation: [Cloud Link](http://spdx.windriver.com/pkg_upload.aspx); Format for Open Source disclosure docs for Wind River Linux 5 distro (700+); Used internally in IP compliance review; ISV requested OSS disclosure format; Created website to promote adoption: [spdx.windriver.com](http://spdx.windriver.com)(includes example SPDX files). |
|                   |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Alcatel-Lucent    | Company | Use SPDX documents for internal communication. (Michel Ruffin)                                                                                                                                                                                                                                                                                                                                                                                     |
|                   |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

SPDX Producer/Consumer Tracking

  

## Use of SPDX Short Identifiers

### Overview

This is a new area. It focuses on using META tags in code to help in
identification of licensing and possibly other SPDX information. The
technical team is looking at writing this up. Currently the U-boot
community has started using a field called SPDX-License-Identifier. You
can see an example here:
<http://git.denx.de/?p=u-boot.git;a=blob;f=post/post.c;h=4af5355fa5a20f9c2e763f37b269bea38d43e8ea;hb=6612ab33956ae09c5ba2fde9c1540b519625ba37>

### Goals

We talked about one year goals. Should we have one and five?

  - Proposal: Publish guidelines and/or standards for meta tag inclusion
    by Linux Collab Summit 2014
  - Proposal: 5 or more open source projects utilize meta tags in their
    in development projects by end of year 2013

### Metrics

For groups use one of the following. You can use multiple groups for an
entity.

  - Foundation (e.g. Linux Foundation, Free Software, Apache, Eclipse,
    etc).
  - Standards (e.g. OSI, W3C, etc).
  - Community (e.g. Community projects like Uboot, Kernel, Busy Box, GNU
    Compiler, etc).
  - Forge (e.g. Github, Sourceforge, etc).
  - Tools (e.g. open source community or company that has tools to
    generate or consume SPDX).
  - Company

| Entity     | Group     | Notes                                                                                                                                                                                                                                                                                                                                                                         |
| :--------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| U-boot     | Community | \[[http://git.denx.de/?p=u-boot.git;a=blob;f=post/post.c;h=4af5355fa5a20f9c2e763f37b269bea38d43e8ea;hb=6612ab33956ae09c5ba2fde9c1540b519625ba37\]Using](http://git.denx.de/?p=u-boot.git;a=blob;f=post/post.c;h=4af5355fa5a20f9c2e763f37b269bea38d43e8ea;hb=6612ab33956ae09c5ba2fde9c1540b519625ba37%5DUsing) SPDX-License-Identifier in place of a license header in source. |
|            |           |                                                                                                                                                                                                                                                                                                                                                                               |
| Linaro     | Company   | Tagging files with SPDX short ID <https://git.linaro.org/lng/odp.git/blob/HEAD:/LICENSE>                                                                                                                                                                                                                                                                                      |
|            |           |                                                                                                                                                                                                                                                                                                                                                                               |
| Poco       | Project   | Tagging files with SPDX short ID <https://github.com/pocoproject/poco/blob/develop/LICENSE>                                                                                                                                                                                                                                                                                   |
|            |           |                                                                                                                                                                                                                                                                                                                                                                               |
| Pyserial   | Project   | Tagging files with SPDX short ID <https://github.com/pyserial/pyserial>                                                                                                                                                                                                                                                                                                       |
| Wind River | Company   | Wind River developed a file license tagging syntax that uses SPDX License List shortnames.                                                                                                                                                                                                                                                                                    |
| ARM        | Company   | Tagging files with SPDX short identifiers for mbed project: <https://github.com/ARMmbed>                                                                                                                                                                                                                                                                                      |

META Tags Tracking

[Category:Business](Category:Business "wikilink")
