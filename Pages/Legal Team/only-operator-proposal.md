## Introduction to Issue

### Historical Background

Originally, the SPDX License List listed variations of licenses as
separate "line items". Notably, various versions of L/GPL had two listed
items: one for a specific version-only, and one indicating a
version-or-later. This was indicated in the list via the inclusion of
the words "only" and "or later" in the full name; and via the short
identifier: `GPL-2.0` and `GPL-2.0+` respectively. (examples throughout
this page use GPL-2.0, but this issue applies to the entire family of
GNU licenses, i.e., GPL, LGPL, FDL, APGL).

For example, the pre-version-2.0 SPDX License List looked like this:

`  GNU General Public License v2.0 only   GPL-2.0   `  
`  GNU General Public License v2.0 or later   GPL-2.0+`

When the license expression syntax was introduced in version 2.0 of
SPDX, licenses with the "or later" indication were removed as separate
listed licenses ("deprecated"), as the "or later" option could now be
provided for via using the `+` operator. This enabled the use of the `+`
operator with other licenses, as applicable.

The ability to create license expressions using the `+` operator along
with the `with` operator also solved the issue of under-representation
of license-exception combinations.

However, this also created a new issue whereby the standard header which
is usually where the "or later" or "only" option is indicated in
practice could no longer be differentiated or captured directly. This
also resulted in the full license name having "only" with no real way to
modify that to "or later" in the full license name where/when the `+`.

The original argument for the `+` operator was that it could be used
with other licenses (not just GNU family). However, to anyone's memory
we did, not at that time, conduct a full analysis of the other licenses
with "or later" language or how they work in practice.

### Other License with "or later" Clauses

Not all licenses that provide for later versions treat their application
in the same way or as explicitly as the GNU family of licenses does. A
list of the licenses with text related to later versions, relevant text,
and an analysis of the licenses that have "or later version" type
language are listed on this page:
<https://wiki.spdx.org/view/Legal_Team/later-version-clauses>

Notably, most licenses that reference the possibility of later versions
can be read to say you can take and redistribute the work under the
license you found it with or any other later version with no explicit
option of 'this version only.'

The CDDL family is slightly different in that the CDDL is “or later” by
default and “only” with [an explicit notice prohibiting later
versions](https://github.com/spdx/license-list-XML/blob/7ecb7363bc82aedd0e293ca8825e348181619e6a/src/CDDL-1.1.xml#L279-L289).
There's currently no `only` operator for the CDDL, although some code
(e.g. [parts of FreeBSD's ZFS
implementation](https://github.com/freebsd/freebsd/blob/2c31a4b74c2e41b0c7407c9830e22bfd07150af0/uts/common/fs/zfs/abd.c#L2-L5))
does declare that prohibition while other code (e.g. [some illumos
userspace
tools](https://github.com/illumos/illumos-gate/blob/a9bfd41d542f15c474711abb8b0ca66a4cef9918/usr/src/common/acl/acl_common.h#L2-L19))
does not (and is therefore presumably CDDL-1.0+).

### Issue

In practice, practitioners are not always explicit about whether a
license is a version only or or later option. Also, because the "only"
or "or later" distinction often is found outside the actual license text
(e.g., in a license notice or header in the source files), machines (and
humans) need a way to identify the license file itself without
determining (yet) if the package is "only" or "or later". In other
words, there is currently no way to express 'I just found this license
text and am not sure what the package license is' using only license
expressions.

The SPDX specification provides a way to distinguish between what is
[detected license
files](https://spdx.org/spdx-specification-21-web-version#h.111kx3o) and
the [concluded file
license](https://spdx.org/spdx-specification-21-web-version#h.2lwamvv)
as well as similar fields at the package level when creating an SPDX
document. But before getting to that point, tools must have ways to
correctly identify what is precisely found in the files without having
to draw a conclusion. Also, as discussed in the 2017-08-08 meeting, some
ecosystems restrict themselves to license expressions (e.g. [npm allows
SPDX 2.0 license
expressions](https://docs.npmjs.com/files/package.json#license)), and
some tools attempt to detect package licenses by looking only at the
license files and not at license-grant blurbs (e.g.
[Licensee](https://github.com/benbalter/licensee/blob/v9.2.0/docs/what-we-look-at.md),
which is [used by the GitHub license
API](https://developer.github.com/v3/licenses/)).

### Examples / Challenges

The scenarios below map out various examples and how one would identify
the [License Information in
File](https://spdx.org/spdx-specification-21-web-version#h.111kx3o) and
then the [Concluded License for the
package](https://spdx.org/spdx-specification-21-web-version#h.ihv636)
using SPDX short identifiers and bearing in mind machine reading for
this task. Some of these scenarios have been discussed on the various
calls on this topic as to how one would identify the license short
identifier for each file currently:

1.  '''you find: 1 text file with the license text of GPLv2; and 4
    source files with the standard header for GPLv2, which include the
    language "any later version" '''
    1.  4.6 License Information in File:
        1.  1 text file with license text of GPLv2 = as `GPL-2.0` means
            "only" - this is hard to determine, and different tools may
            handle this in different ways, including `NOASSERTION`
        2.  4 source files with standard header for GPLv2, which include
            the language "any later version" = `GPL-2.0+`
    2.  3.15 Declared License: same issue as for determining identifier
        for text file with license text of GPLv2 as above
    3.  3.13 Concluded License at package level = `GPL-2.0+`
    4.  4.5 Concluded License at file level - same as for package level
        due to notices
    5.  Note: in the current reality, `GPL-2.0` for the license text
        file would mean "only", yet one cannot determine from that file
        alone if the copyright holder intends to use the version only or
        the or later option (see example 4). Also note, that a machine
        can positively identify the "or later" option via the use of
        recommended standard license header. This would be the same
        scenario, but with GPL-2.0 if the license header did not evoke
        the "any later version" language.
2.  '''you find: no license file; 4 source files with the statement,
    “This is licensed under GPL" '''
    1.  4.6 License Information in File: 4 source files = `NOASSERTION`
        - because the information doesn't match anything on the SPDX
        License List or standard headers.
    2.  3.15 Declared License (for package) = NONE (because no license
        file was found); NOASSERTION would also be an option
    3.  4.5 Concluded License at file level = `GPL-1.0+`
    4.  3.13 Concluded License package = `GPL-1.0+`
    5.  Note: The determination of `GPL-1.0+` would be made by a human.
        But given the language of the GPL stating, "If the Program does
        not specify a version number of the license, you may choose any
        version ever published by the Free Software Foundation." and the
        short identifier `GPL-1.0+` covers any version.
3.  **you find: 1 license file with GPLv2 license text; 4 source files
    with no license information whatsoever (aka, the Github example)**
    1.  4.6 License Information in File:
        1.  1 text file with license text of GPLv2 = as `GPL-2.0` means
            "only" - this is hard to determine, and different tools may
            handle this in different ways, including `NOASSERTION` (same
            as scenario 1)
        2.  4 source files with no license information whatsoever = NONE
            (as per SPDX specification)
    2.  4.5 Concluded License at file level = some interpretation will
        be made here, based on the text of the license
    3.  3.13 Concluded License package = some interpretation will be
        made here, based on the text of the license
    4.  different conclusions might include GPL-1.0+, GPL-2.0, GPL-2.0+
        1.  Is including a copy of a particular version of the license
            "the Program specif\[ying\] a version number of the license
            which applies to it" and thus we can confidently conclude
            the package is GPL-2.0? Is the "or later" option triggered
            due to the language or would that be too far of a step to
            take? See [one interpretation from mailing list
            here](https://lists.spdx.org/pipermail/spdx-legal/2017-September/002162.html).
    5.  Answer: John Sullivan from the FSF was [going to check for a FSF
        position on
        this](Legal_Team/or-later-vs-unclear-disambiguation#Alternative_Solution_-_Do_Not_Deprecated_GPL-2.0 "wikilink").

## Goals

  - Provide way to get to "GPL-2.0-only" (or the like) identifier to
    enable better clarity for that option/scenario
  - Ensure we accommodate the reality of other licenses with language
    re: later versions such that all options can be represented
    appropriately
  - Ensure that there is some amount of consistency with what the short
    identifiers mean / Don't completely break the meaning for current
    users

## Proposed Solution: add `only` operator

Based on the various legal and tech calls and including representatives
from the LF (some notes in [Legal
Team/or-later-vs-unclear-disambiguation](Legal_Team/or-later-vs-unclear-disambiguation "wikilink")),
we coalesced around the following proposal:

'''Create an "only" operator defined as to be used to indicate 'only the
version of the license is intended for use' '''

For licenses that may include “only” or “or later” (or both) clauses in
the license text, having explicit `+` and `only` operators to use in
SPDX identifiers reduces the chance that an unfamiliar user mis-uses or
misinterprets the identifier and provides a way to be explicit and
accurate that was arguably not available before. This solution allows
the license text to speak for itself (via the "plain" license
identifier) and uses the `only` and `+` operators to be explicit in
intent.

This leaves the ability to use the "plain" license identifier (without
an operator) to indicate the existence of the license text itself or
other scenarios where it is not clear whether the "or later" or "only"
options are articulated by the copyright holder. This avoids SPDX having
to make an interpretation as to what the licenses mean or intend. This
would also bring into consistency the use of "plain" identifiers for all
other licenses that have "or later" clauses.

The + operator would remain with the same definition.

Necessary/associated changes:

  - add new "only" operator to Appendix IV: SPDX License Expressions of
    spec and explanatory language as to how/when to use it.
  - Remove "only" from full name of GNU family licenses on SPDX License
    List
  - clarify that the license ID used by itself would indicate that the
    license text itself should be used to determine if later versions of
    the license could be used (in Appendix IV or V?)

Potential issues:

  - Backwards compatibility for GPL-2.0 meaning 'only' to now meaning
    'whatever the license says' creates some inconsistency as the
    default position of the license text with no other info is "or
    later" or "any version", not "only". However, it was pointed out on
    the call that those people conscientious enough to be using GPL-2.0
    correctly, will be more likely to be conscientious enough to add the
    `only` operator as needed once it's available. All seemed to agree
    that use of GPL-2.0 is probably not thought through as to "or later"
    or "only", and thus in these situations, there is no different
    meaning.
  - Does not make clear indication of "ambiguous" situation to push
    people towards using 'only' and '+' operators to be explicit
    (preferred). However, we don't have a clear indication of ambiguity
    now either (is ambiguity ever clear?). You can clearly detect the
    ambiguous situations in tooling if you add metadata to license
    definitions recording whether they are compatible with the various
    version-related operators (as discussed
    [here](Legal_Team/or-later-vs-unclear-disambiguation#Alternative_Solution_-_create_-only_and_PROXY_.7BTEXT.7D_operators_for_licenses_that_explicitly_declare_their_compatibility "wikilink")
    and
    [here](https://lists.spdx.org/pipermail/spdx-legal/2017-August/002126.html)).
  - GPL language is clear that it is one or the other, so this could
    create more confusion and not reflect the intention of the license.
    However, all agreed that when you have a machine scanning code with
    no other license info other than a file with the license text of
    GPL-2.0, this is not entirely clear situation.
