Status: obsolete? (See more recent discussion in
[Legal\_Team/Minutes/2017-11-09](Legal_Team/Minutes/2017-11-09 "wikilink")

## Introduction to Issue

### Background (SPDX)

Originally, the SPDX License List listed variations of licenses as
separate "line items". Notably, various versions of L/GPL had two listed
items: one for a specific version-only, and one indicating a
version-or-later. This was indicated in the list via the inclusion of
the words "only" and "or later" in the full name; and via the short
identifier: GPL-2.0 and GPL-2.0+ respectively. (examples throughout use
GPL-2.0, but this issue applies to the entire family of GNU licenses,
i.e., GPL, LGPL, FDL, APGL).

For example, the pre-version-2.0 SPDX License List looked like this:

`  GNU General Public License v2.0 only   GPL-2.0   `  
`  GNU General Public License v2.0 or later   GPL-2.0+`

When the license expression syntax was introduced in version 2.0 of
SPDX, licenses with the "or later" indication were removed as separate
listed licenses ("deprecated"), as the "or later" option could now be
provided for via using the "+" operator. The ability to use license
expressions via the "+" operator, along with the "with" operator also
solved the issue of under-representation of license-exception
combinations.

However, this also created a new issue whereby the standard header which
is usually where the "or later" or "only" option is indicated in
practice could no longer be differentiated or captured directly. This
also resulted in the full license name having "only" with no real way to
modify that to "or later" in the full license name.

The original argument for the `+` operator was that it could be used
with other licenses (not just GNU family). However, to anyone's memory
we did not at that time conduct a full analysis of the other licenses
with "or later" language or how they work in practice.

### Background (additional)

Not all licenses that provide for later versions treat their application
in the same way or as explicitly as the GNU family of licenses does. A
list of the licenses with text related to later versions, relevant text,
and an analysis of the licenses that have "or later version" type
language are [here](Legal_Team/later-version-clauses "wikilink").

Notably, most license that reference the possibility of later versions
can be read to say you can take and redistribute the work under the
license you found it with or any other later version with no explicit
option of 'this version only.'

The CDDL family is slightly different in that the CDDL is “or later” by
default and “only” with [an explicit notice prohibiting later
versions](https://github.com/spdx/license-list-XML/blob/7ecb7363bc82aedd0e293ca8825e348181619e6a/src/CDDL-1.1.xml#L279-L289).
There's currently no `only` operator for the CDDL, although some code
(e.g. [parts of FreeBSD's ZFS
implementation](https://github.com/freebsd/freebsd/blob/2c31a4b74c2e41b0c7407c9830e22bfd07150af0/uts/common/fs/zfs/abd.c#L2-L5))
do declare that prohibition while other code (e.g. [some illumos
userspace
tools](https://github.com/illumos/illumos-gate/blob/a9bfd41d542f15c474711abb8b0ca66a4cef9918/usr/src/common/acl/acl_common.h#L2-L19))
do not (and are therefore presumably CDDL-1.0+).

And to make versioned license grants even more complicated, the GPL-3.0
and similar have grown a [proxy
clause](https://github.com/spdx/license-list-XML/blob/7ecb7363bc82aedd0e293ca8825e348181619e6a/src/GPL-3.0.xml#L515-L517)
that was not in earlier GPL versions. The CC has [similar proxy
designation](https://github.com/spdx/license-list-XML/blob/7ecb7363bc82aedd0e293ca8825e348181619e6a/src/CC-BY-SA-4.0.xml#L66-L67),
but they don't give users a choice to change the proxy in their license
grant. And similar proxy designation has come up before with the KDE's
LGPL grant (see
[here](https://lists.spdx.org/pipermail/spdx/2011-May/000389.html) and
[here](FileNoticeExamples#.28LGPL-2.1_OR_LGPL-3.0_OR_LicenseRef-KDE-Accepted.29 "wikilink")).

### Issue

In practice, practitioners are not always explicit about whether a
license is a version only or or later option. For licenses that may
include either “only” or “or later” semantics depending on the grant,
having an explicit `+`, `only`, or `PROXY {TEXT}` (or similar) in the
grant's SPDX identifier reduces the chance that an unfamiliar user
misinterprets the identifier.

The spec provides a way to distinguish between [detected license
files](https://spdx.org/spdx-specification-21-web-version#h.32hioqz) and
the [concluded package
license](https://spdx.org/spdx-specification-21-web-version#h.ihv636).
As discussed in the 2017-08-08 meeting, some ecosystems restrict
themselves to license expressions (e.g. [npm allows SPDX 2.0 license
expressions](https://docs.npmjs.com/files/package.json#license)), and
some tools attempt to detect package licenses by looking only at the
license files and not at license-grant blurbs (e.g.
[Licensee](https://github.com/benbalter/licensee/blob/v9.2.0/docs/what-we-look-at.md),
which is [used by the GitHub license
API](https://developer.github.com/v3/licenses/)). This approach will
also fail to distinguish between `MPL-2.0` and
`MPL-2.0-no-copyleft-exception`, since that distinction is [based on the
blurbs](https://github.com/spdx/license-list-XML/blob/7ecb7363bc82aedd0e293ca8825e348181619e6a/src/MPL-2.0-no-copyleft-exception.xml#L43-L44).
And there is currently no way to express “I just found these licenses
and am not sure what the package license is” using only license
expressions.

### Goals

  - Provide way to get to "GPL-2.0-only" (or the like) identifier to
    enable better clarity for that option/scenario
  - Ensure we accommodate the reality of other licenses with language
    re: later versions such that all options can be represented
    appropriately
  - Ensure that there is some amount of consistency with what the short
    identifiers refer to
  - Don't completely break the meaning for current users

## Solutions

Various solutions were discussed on legal and tech team calls on the
following dates, as well as via the mailing list.

The current proposed solution represents the most recent evolution in
discussions on the topic. Items below that are left here for record, but
not necessarily updated.

### Current Proposed Solution

Based on the joint legal/tech call on 17 August 2017, we coalesced
around a solution similar to "alternative option" from 8 Aug joint call:

  - Create an "only" operator defined as to be used to indicate 'only
    the version of the license is intended for use'.
      - add new "only" operator to Appendix IV: SPDX License Expressions
        of spec and explanatory language
  - The + operator would remain with the same definition.
  - In the spec, clarify that the license ID used by itself would
    indicate that the license text itself should be used to determine if
    later versions of the license could be used.
      - This avoids SPDX having to make an interpretation as to what the
        licenses mean/intend.
      - Allows for use of GPL-2.0 when you find just the license file
        with the text of GPL-2.0 and still provides option for Concluded
        License to be GPL-1.0+ if no other info is found
  - Remove "only" from full name of GPL family.
  - This solution allows the license text to speak for itself and uses
    the 'only' and '+' operators to be explicit in intent. It also
    avoids conflicting operators by retaining the "plain" license
    identifier.

Potential issues:

  - Backwards compatibility for GPL-2.0 meaning 'v2-only' to now meaning
    'whatever the license says' creates some inconsistency as the
    default position of the license text with no other info is "or
    later" or "any version", not "only". However, it was pointed out on
    the call that those people conscientious enough to be using GPL-2.0
    correctly, will be more likely to be conscientious enough to add the
    "-only" operator as needed/once it's available. All seemed to agree
    that use of GPL-2.0 is probably not thought through as to "or later"
    or "only", and thus in these situations, there is no different
    meaning.
  - Does not make clear indication of "ambiguous" situation to push
    people towards using 'only' and '+' operators to be explicit
    (preferred). However, we don't have a clear indication of ambiguity
    now either (is ambiguity ever clear?).
  - L/GPL language is clear that it is one or the other, so this could
    create more confusion and not reflect the intention of the license.
    However, all agreed that when you have a machine scanning code with
    no other license info other than a file with the license text of
    GPL-2.0, this is not entirely clear situation.

### Joint call 8 Aug 2017 proposed solution

Based on the joint tech/legal call on 8 August 2017, following is a
proposed solution:

  - Create an "only" operator defined as only the version of the license
    is intended for use.
  - The + operator would remain with the same definition.
  - In the spec, clarify that the license ID used by itself would
    indicate that the license text itself should be used to determine if
    later versions of the license could be used.
  - Create new license ID's GPLv1.0, GPLv2.0, GPLv3.0, LGPLv2.0,
    LGPLv2.1, LGPLv3.0 to replace the current license GPL family of
    license ID's which are defined to mean "only"
  - Deprecated the license ID's GPL-1.0, GPL-2.0, GPL-3.0, LGPL-2.0,
    LGPL-2.1, LGPL-3.0 with a description that the license ID which
    replaces it should be used with the only operator

Potential issues:

  - L/GPL language is clear that it is one or the other, so this could
    create more confusion and not reflect the intention of the license.
  - This could also result in people using the `only` operator with
    other licenses where it is not needed or shouldn't be used. This
    could be mitigated by declaring license metadata for “compatible
    with `-only`”, “compatible with `+`”, etc. Then it would be easy to
    write tooling to validate a given license expression (“You used
    `NPL-1.0-only`, but `NPL-1.0` is not compatible with `-only`”), but
    that doesn't mean users <em>would</em> validate their license
    expressions.
  - “I just found this license text and am not sure about the grant”
    isn't specific to or-later-ness. For example, if you find text for
    `GPL-2.0` and text for `Apache-2.0`, the project is likely either
    `GPL-2.0 AND Apache-2.0` or `GPL-2.0 OR Apache-2.0`, but without
    (finding and parsing) an explicit licence grant you can't figure out
    which was intended. If we have a GPL-specific solution (listing
    neither `+` nor `only`) to representing this situation, there's no
    license-expression syntax for representing the `GPL-2.0 AND/OR
    Apache-2.0` situation. As noted in the [the background
    section](#Background_\(SPDX\) "wikilink"), there <em>is</em> already
    a generic way to make this distinction in the SPDX spec; there's
    just no current way to make it in a license expression.
  - Does not provide a mechanism for encoding GPL-3.0 proxies, or even
    for encoding that a proxy has been designated.

### Alternative Solution - Do Not Deprecated GPL-2.0

Similar to the above proposal, but does not deprecate the GPL family of
license IDs:

  - Create an "only" operator defined as only the version of the license
    is intended for use.
  - The + operator would remain with the same definition.
  - In the spec, clarify that the license ID used by itself would
    indicate that the license text itself should be used to determine if
    later versions of the license could be used.
  - Change the name and description of the GPL family of licenses to
    remove "only" references

Potential issues (in addition to those listed for the previous
proposal):

  - If the GPL license text (in the absence of an explicit licensing
    blurb, e.g. in a file header) is determined to imply something other
    than “only” semantics, instances of `GPL-2.0` become unclear (with
    the old logic, they clearly mean “only” and with the new logic they
    would not. John Sullivan is checking with the FSF to determine their
    position on the intended version(s) if a project has the GPL license
    text in a file but no explicit licensing blurb.

### Alternative Solution - create `-only` and `PROXY {TEXT}` operators for licenses that explicitly declare their compatibility

  - Create an `-only` operator for “only this version of the license is
    intended for use”.
  - Create a `PROXY {TEXT}` operator for the proxy declaration in the
    GPL-3.0 and similar (see [the KDE example
    above](#Background_\(SPDX\) "wikilink")).
  - The `+` operator would remain with the same definition.
  - Change the name and description of the GPL family of licenses to
    remove [“only”
    references](https://github.com/spdx/license-list-XML/blob/7ecb7363bc82aedd0e293ca8825e348181619e6a/src/GPL-2.0.xml#L1).
  - Add fields to the [license
    metadata](https://spdx.org/spdx-specification-21-web-version#h.1v1yuxt)
    and the license-list's XML for “compatible with `-only`”,
    “compatible with `+`”, etc. For example, `GPL-2.0` would be
    compatible with `-only` and `+`; `GPL-3.0` would be compatible with
    `-only`, `+`, and `PROXY {TEXT}`; `NPL-1.0` would be compatible with
    `-only`, although it's use would not be recommended, and
    `BSD-2-Clause` would be compatible with none of these operators.
  - Add metadata flagging licenses which should be explicitly versioned.
    For example, the GPL and CDDL families would declare “should
    explicitly version”. Then tooling could warn if a license expression
    had, for example, `GPL-3.0` unmodified by `-only`, `+`, or `PROXY
    {TEXT}`. Tooling should consider `GPL-2.0 OR GPL-3.0` to be
    explicitly versioned, even though it uses none of the versioning
    operators.

Potential issues:

  - This has the same “ambiguous bare `GPL-2.0` declaration” issue as
    [the current proposal](#Current_Proposed_Solution "wikilink"), but
    at least now we can warn in these cases.
  - This has the same “current `GPL-2.0` users should update to a more
    specific identifier” issue as the two proposals above, but `GPL-2.0
    AND GPL-3.0` folks are not obsolete with this proposal.
  - This has the same “`-only` operator used with an inappropriate
    license” issue as [the current
    proposal](#Current_Proposed_Solution "wikilink"), but again, now we
    can warn in these cases.
  - This has the same “no generic way to say ‘I just found this license
    text and am not sure about the grant’” issue as [the current
    proposal](#Current_Proposed_Solution "wikilink"), but since that's a
    generic problem with an existing out-of-license-expression solution,
    I'd argue for not solving it in the license expression. For examples
    outside of a SPDX declaration, see GitHub's [“not a law
    firm”](https://developer.github.com/v3/licenses/) and [“not legal
    advice”](https://github.com/spdx/tools/blob/master/LICENSE)
    [caveats](https://help.github.com/articles/licensing-a-repository/#disclaimer).

### Alternative Solution - GPL-2.0-only license ID

Replace "GPL-2.0" identifier with "GPL-2.0-only"

Potential issues:

  - `GPL-2.0-only OR GPL-3.0-only` is as strange a license designation
    as `GPL-2.0-only+` which is one of the reasons given for rejecting
    the [alias
    approach](#Alternative_Solution_-_Add_an_.E2.80.9Calias.E2.80.9D_concept_and_make_GPL-2.0_and_GPL-2.0-only.2C_etc._equivalent "wikilink").

### Alternative Solution - Add an “alias” concept and make `GPL-2.0` and `GPL-2.0-only`, etc. equivalent

Add new concept of short identifier “alias” and make `GPL-2.0`
equivalent to `GPL-2.0-only`.

Potential issues:

  - If `GPL-2.0` is equivalent to `GPL-2.0-only`, then what is the
    canonical "or later" option? You could end up with `GPL-2.0-only+`
    which makes no sense\! The ends result here needs to indicate:
    `GPL-2.0-only` and `GPL-2.0+` with no ability to combine them. Also,
    a short identifier "alias" would be a new concept and possibly
    over-engineering a solution for one set of licenses.

NOT an option.

### Alternative Solution - Revert the `+` operator and return to `GPL-2.0-only` and `GPL-2.0+` as separate licenses

Remove the `+` operator from the license expression syntax and
re-implement GPL-2.0-only and GPL-2.0+ as separate line items on the
SPDX License List. This would not impact the extensibility of applying
exceptions, as the "with" operator is the key factor for that. This
would also solve header matching problem as it would allow the standard
header field to be existing and matchable for both variations. The key
downside to this solution is it means rolling back something we spent a
lot of work implementing, but if the outcome provides more clarity and
better license "hygiene" as well as aligning with the FSF wishes, then
it is worth the work?

Potential issues:

  - This has the same `GPL-2.0-only OR GPL-3.0-only`
    [issue](#Alternative_Solution_-_GPL-2.0-only_license_ID "wikilink")
    as the bare `GPL-2.0` → `GPL-2.0-only` rename.

## Selected responses/ideas/commentary from mailing list

*' NOTE:*' Please feel free to add/clarify below link to SPDX-legal
mailing list from this thread can be found here:
<https://lists.spdx.org/pipermail/spdx-legal/2017-May/thread.html>

At the same time as conversations between SPDX leaders and FSF
representatives were on-going, this topic bubbled up on SPDX mailing
list. Below is a summary of such conversations.

#### D. Wheeler 5/25/2017

Technically “GPL-2.0” in SPDX means “only this version”, but in practice
many practitioners & tools are sloppy about this. Part of the problem is
that tools can easily determine that “GPL version 2.0 is in this
package” but in many cases they cannot easily determine automatically
a distinction between “2.0 or greater” versus “2.0 and no other”. In
addition, in many cases it doesn’t matter, so the increased effort would
be a waste of time. What the tools really need to indicate is a way in
SPDX to indicate “2.0 at least is here, and I don’t know if ‘or later’
is okay”. Since SPDX doesn’t have a mechanism to report this, “GPL-2.0”
is sometimes being used to report of “I know 2.0 is here, and I don’t
know if ‘or later’ is okay” - even though it’s technically not compliant
with the SDPX spec.

It’d be helpful to have a simple way to indicate “I really mean this
specific version” (my “\!” suffix) vs. “this version at least is okay,
and I’m not sure about later versions” (which is how “GPL-2.0” is
currently interpreted; maybe another suffix like “?” or “\*” would help
to mark this case).

#### K. Stewart 5/25/2017

We've started having some discussions with FSF about what they'd prefer,
and their preference seems to be GPL-2.0-only, so we probably want to go
that way rather than introducing the "\!" idea.

#### D. Wheeler 5/25/2017

` K. Stewart: We've started having some discussions with FSF about what they'd prefer, and their preference seems to be GPL-2.0-only,  so we probably want to go that way rather than introducing the "!" idea.`

Okay. Although that's less flexible, that's much easier to transition
(you don't have to change any parsing code), so I see the advantages of
this.

If this is done: 1. It needs to cover all the licenses where this is
likely. At \*least\* GPL and LGPL; I think MPL is probably in this case
too. 2. The original license terms need to \*stay\* in SPDX, with
modified clarifying text. Something like this:

GPL-2.0: The GNU General Public License (GPL), version 2.0 is
acceptable, and without any clear statement if later versions are
acceptable. Where practical, try to use more specific license
expressions such as "GPL-2.0+", "GPL-2.0-only", or "(GPL-2.0-only OR
GPL-3.0-only)". Historically this indicator meant "GPL version 2.0
only", but in practice tools often can't determine if later ones are
acceptable (or not) & used this term in such cases. This specification
acknowledges this practice and provides more specific alternatives when
that information is available.

#### D. Wheeler 5/26/2017

We need at least \*3\* cases. Here they are, with potential
names/expressions:

  - GPL-2.0-only. I \*know\* that \*only\* the GPL version 2.0 is
    acceptable. I had originally proposed a "\!" suffix.
  - GPL-2.0+. I \*know\* that GPL version 2.0, or later, is acceptable.
  - GPL-2.0. I \*know\* that at least GPL version 2.0 is acceptable
    (e.g., I found its license text). However, I'm not entirely certain
    whether or not later versions are acceptable, so I make \*no\*
    assertion either way. This appears to be what "GPL-2.0" has become,
    in some cases, in spite of the spec. Which is why we need a way to
    mark certainty vs. uncertainty. If you prefer, you could label this
    "GPL-2.0-at-least", or add a "?" suffix to mean "I don't know if
    later/other versions are acceptable".

The problem is that while tools can detect the presence of a license,
it's often difficult for them to determine if an "or later" clause is
valid in some cases. In many cases SPDX is capturing tool output, so we
need for there to be a valid expression for tools to output. My
understanding is that some tools that find GPL version 2.0 will
currently report "GPL-2.0"... even if a later version is also
acceptable... and as a result, "GPL-2.0" is not being interpreted as
originally intended.

What's more, without a third case, it'll just happen again. Tools can't
easily determine if "or later" applies, and in many cases you do \*NOT\*
need more information than this. It can take a lot of effort ($) to
determine if it's really "GPL-2.0-only" or "GPL-2.0+", and if the spec
only supports those two options, then that's a problem.. because people
are \*not\* going to spend effort unnecessarily.

If "GPL-2.0" is deprecated, then tools will start reporting
"GPL-2.0-only" when they're not sure if later versions apply, because in
many cases they can't easily determine it. Then we'll be back to the
original problem, where "GPL-2.0-only" may mean "I found GPL 2.0 but
maybe later versions will be okay". Ugh. Since many tools can only
determine "at least this version", there needs to be a standard way to
report it.

#### T. King 5/26/2017

Digging at this “acceptable” idea a bit more, I'm guessing it's
something like “adapters may share adapted works under”. But the SPDX
isn't just about copyleft (e.g. it includes CC-BY-ND-\*). I think it
makes more sense to focus on licenses (just the text, e.g. GPL-2.0) and
license grants. For example, here are some SPDX License Expressions
translated into grants:

  - GPL-2.0: You can redistribute it and/or modify it under the terms of
    the GNU General Public License version 2 as published by the Free
    Software Foundation.

<!-- end list -->

  - GPL-2.0+: You can redistribute it and/or modify it under the terms
    of the GNU General Public License as published by the Free Software
    Foundation; either version 2 of the License, or (at your option) any
    later version.

<!-- end list -->

  - CC-BY-SA-4.0: This work is licensed under a Creative Commons
    Attribution-ShareAlike 4.0 International License.

You can distribute an adaptation under a later version of the CC BY-SA
because that's part of the CC-BY-SA-4.0 \[1\].

  - CC-BY-SA-4.0+: This work is licensed under a Creative Commons
    Attribution 4.0 International License; either version 4.0 of the
    License, or (at your option) any later version.

The CC-BY-SA-4.0 tries to grant you that right anyway, but regardless of
how you read the CC-BY-SA-4.0, I'm granting you that right directly.

\> CC-BY-SA-3.0+ would be a synonym for CC-BY-SA-3.0 \[6\], but I don't
\> see a problem with that. It would probably be useful to call that \>
out in the wording that forbids the -only suffix for CC-BY-SA-3.0…

If the SPDX doesn't want to get into the business of determining when
licenses grant + semantics, then we probably don't want an -only suffix
and we certainly don't want a GPL-2.0-only short identifier.

But if you want to be in the business of warning users about the lack of
built-in or-later wording in the GPL, CC-BY-ND-4.0, etc. and the
presence of built-in or-later in the CC-BY-SA-4.0, etc., I don't see how
you'd avoid making claims about whether the license had built-in
or-later wording.

#### D. Seaward 5/26/2017

Perhaps "GPL-2.0"could be deprecated and instead whoever is tagging must
use one of:

  - GPL-2.0-only
  - GPL-2.0+
  - GPL-2.0?

...where "only" means only, "+" means "or later" and "?" means unclear.
Legacy data still tagged "GPL-2.0" would be treated as "GPL-2.0?" until
updated. (This assumes the SPDX team want people tagging things as
unclear\!)

### Gary O'Neall 8/3/2017

Summary of proposal made on the legal call. Proposal to create an "only"
operator. The semantics would be the only operator indicates that only
the version of the license is intended for use. The + operator would
remain with the same definition. The license ID used by itself would
indicate that the license text itself should be used to determine if
later versions of the license could be used. The advantage of this
proposal is allows the author of the SPDX document to describe many of
the scenarios found in the license header text explicitly. The
disadvantage is it doesn't solve the problem of the current GPL license
ID's having an explicit "only" version which contradicts the language of
the license itself. I can think of 2 possible solutions:

  - Create new license short ID's and deprecate the original ones. For
    example, we could add GPLv2 instead of GPL-2.0. There are several
    other possible naming conventions (e.g. GPL-v2.0, GPL2.0). The
    important aspect is that the new license ID is different. We could
    then deprecate the old license ID's.
  - Rely on the license list version to interpret the "only" aspect of
    the GPL licenses. Versions prior to the implementation of the only
    operator would interpret the GPL to be ONLY, after implementation of
    the only operator it would be interpreted per the license text. The
    issue with this approach is not all license expressions have an
    associated license list version.
