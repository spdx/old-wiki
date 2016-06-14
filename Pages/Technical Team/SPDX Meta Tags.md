**SPDX Meta Tagging**

This is currently a DRAFT and work in progress.

\_\_TOC\_\_

Last Updated: 13 August 2015

# Introduction

The need to identify the license for open source software is critical
for both reporting purposes and license compliance. However, determining
the license can be difficult due to a lack of information or ambiguous
information. Even when licensing information is present, a lack of
consistent notation for providing license information can make
automating the task of license detection very difficult, thus requiring
vast amounts of human effort.

Meta Tagging is a proposal by the SPDX Work-group to use [short license
identifiers](http://spdx.org/licenses/) from the SPDX License List to
indicate license info at the file level. The advantages of doing this
are numerous but include:

  - It is precise, there is no ambiguity due to variations in license
    header text.
  - It is language neutral.
  - It is easy to machine process.
  - It is concise
  - Leads to code that is easier to read.
  - The license travels with the file (as sometimes not entire projects
    are used or license files are removed).
  - It is simple and can be used without much cost in interpreted
    environments like java Script, etc.,.
  - It is a standard and can be universal. There is no need for all the
    variation.
  - An SPDX license identifier is immutable.
  - It provides simple guidance for developer's who want to make sure
    the license for their code is respected.

## History

Although discussed by SPDX for some time, with proposals by Windriver,
the U-boot project was the first open source project to adopt (that we
know about). This was the commit message by Wolfgang Denk the project
maintainer:

<code>

`   Like many other projects, U-Boot has a tradition of including big`  
`   blocks of License headers in all files.  This not only blows up the`  
`   source code with mostly redundant information, but also makes it very`  
`   difficult to generate License Clearing Reports.  An additional problem`  
`   is that even the same licenses are referred to by a number of`  
`   slightly varying text blocks (full, abbreviated, different`  
`   indentation, line wrapping and/or white space, with obsolete address`  
`   information, ...) which makes automatic processing a nightmare.`  
`   `  
`   To make this easier, such license headers in the source files will be`  
`   replaced with a single line reference to Unique Lincense Identifiers`  
`   as defined by the Linux Foundation's SPDX project [1].  For example,`  
`   in a source file the full "GPL v2.0 or later" header text will be`  
`   replaced by a single line:`  
`   `  
`           SPDX-License-Identifier:        GPL-2.0+`

</code>

# Meta Tags

Meta-tags can be used in source code for example which can make it
easier for tools that run over source code to determine where a
particular source code file belongs and what its license is. The
following meta-tags are available currently;

## SPDX-License-Identifier

This tag declares the license the file is under and should be placed at
or near the top of the file. To the extent that the file contains
existing copyright and license information it is our general
recommendation that the tag be used to supplement not replace that
information especially for files with a long history of changes,
multiple copyright holders, or complex licensing. Of course, this is the
ultimate decision of the copyright holders of the file.

### Tag Format

The tag should appear on its own line in the source file, generally as
part of a comment.

SPDX-License-Identifier: <SPDX License Expression>

Where an SPDX license expression is defined in [SPDX 2.0 Specification
see Appendix IV](http://spdx.org/sites/spdx/files/SPDX-2.0.pdf).

The license expression syntax permits references to a single license
(represented by a short form license id from the [SPDX license
list](http://spdx.org/licenses/) ) or a compound set of licenses
(represented by joining together multiple licenses using the license
expression syntax).

#### Representing Individual Licenses

Each license can be represented by the short form license id from the
[SPDX license list](http://spdx.org/licenses/). Optionally, a unary
operator "+" (plus sign) may be included to indicate "or later".

Examples:

:\* SPDX-License-Identifier: MIT

:\* SPDX-License-Identifier: GPL-2.0+

#### Representing Multiple Licenses

A license set should be enclosed in parentheses. When there is a choice
between licenses ("disjunctive license"), they should be separated with
"OR". Similarly when multiple licenses need to be applied ("conjunctive
license"), they should be separated with "AND". In some cases, a set of
license terms apply except under special circumstances, in this case,
use the "WITH" operator followed by one of the [recognized exception
identifiers](http://spdx.org/licenses/exceptions-index.html). Please see
[Appendix IV of SPDX 2.0
Specification](http://spdx.org/sites/spdx/files/SPDX-2.0.pdf) for more
details of the specific syntax.

Examples:

:\* SPDX-License-Identifier: (GPL-2.0 OR MIT)

:\* SPDX-License-Identifier: (LGPL-2.1 AND BSD-2-CLAUSE)

:\* SPDX-License-Identifier: (GPL-2.0+ WITH Bison-exception-2.2)

#### What to do if your license is not on the list?

At this point, its probably best to just put the text of your license
header in the file if it doesn't exist in the license list. Please
contact the [SPDX legal work
group](http://spdx.org/spdx-license-list/request-new-license) to get
your license added to the License List.

# Examples

These are examples of communities which are using a Meta Tag.

## Uboot

U-boot is
\[[http://git.denx.de/?p=u-boot.git;a=blob;f=post/post.c;h=4af5355fa5a20f9c2e763f37b269bea38d43e8ea;hb=6612ab33956ae09c5ba2fde9c1540b519625ba37\]using](http://git.denx.de/?p=u-boot.git;a=blob;f=post/post.c;h=4af5355fa5a20f9c2e763f37b269bea38d43e8ea;hb=6612ab33956ae09c5ba2fde9c1540b519625ba37%5Dusing)
SPDX-License-Identifiers in place of a license header in source.

## ARM mbed

When there is a standard header provided by the license author, it is
recommended to use such standard header (alone or in combination with
the SPDX short identifier). See, for example:
<https://github.com/ARMmbed/mbed-mesh-api/blob/master/source/AbstractMesh.cpp>

## Poco project

If using SPDX short identifiers in individual files, it is recommended
to reproduce the full license in the projects LICENSE file and indicate
that SPDX short identifiers are being used to refer to it. See, for
example: pocoproject/poco and
<https://github.com/pocoproject/poco/blob/develop/XML/src/AbstractContainerNode.cpp>

# Proposing New Meta Tags

To propose a new Meta Tag, send your proposal to the SPDX Technical
Workgroup using their [mailing
list](https://lists.spdx.org/mailman/listinfo/spdx-tech/).

[Category:Technical](Category:Technical "wikilink")
