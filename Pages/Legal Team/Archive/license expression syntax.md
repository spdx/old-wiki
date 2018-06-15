## Information & Background on License Expression Syntax Proposal

  - Background info on the issue is posted on the wiki here:
    <http://wiki.spdx.org/view/Legal_Team/License_Expression_Review_1>
  - Examples are posted here:
    <http://wiki.spdx.org/view/FileNoticeExamples>

**The following info was posted to the SPDX mailing lists on 9 April
2014:**

Editor’s note: Big thanks to Mark Gisi for driving this important
effort.

In the wake of a highly productive cross-functional meeting at the Linux
Collaboration Summit, the SPDX Legal Team proposes certain changes to
the SPDX specification and license list.

**Statement of the problem**:

The current SPDX Specification and License List have a limited language
(i.e. and/or) that is not suitable for expressing complex license
situations (for examples of such complexity, see
<http://wiki.spdx.org/view/FileNoticeExamples> ). Additionally, the
current SPDX License List currently requires the addition of multiple
licenses to the list in order to capture combinations of versions, the
“or later” license genre (i.e. GPL-2.0 and GPL-2.0+) and the most
common exceptions (i.e. GPL-2.0+-with-autoconf-exception and
GPL-3.0-with-autoconf-exception). It should be noted that the SPDX Legal
Team identified more than 30 discrete exceptions. Finally, license
exceptions (i.e. autoconf-exception) are generally not versioned, and
therefore, accounting for changes to the license exceptions when they
are part of the canonical license creates opportunity for error and
confusion. For additional background please see
<http://wiki.spdx.org/view/Legal_Team/License_Expression_Review_1>

**Aim**:

Improve the ability to describe more license variations utilizing some
operator(s) without impact to the current timeline for the next version
of the SPDX Specification.

**Proposed Solution**:

**1)** “+” to be added to the SPDX Specification as an operator to
denote “or later.” As a result, all current licenses on the SPDX License
List with a “Full Name” that includes “or later” will be deprecated.
Deprecated means the license entry will technically remain on the list
(just moved to the Deprecated section) and list users will be highly
discouraged from using them. Deprecated licenses are potentially subject
to removal in a future version of the list.

  - Example: The license GPL-2.0+ will be deprecated. License entry
    GPL-2.0 will remain on the SDPX license list and the following is
    still a valid license expression “GPL-2.0+”. This state’s GPL-2.0 or
    later because the “+” now plays the role of a unary operator that
    means ‘the version of this license or a later version’. The
    following would also be a valid license expression as well: EPL-1.0+
    which means EPL-1.0 or a later version. The change of the “+” to an
    operator will make even more sense once one considers license
    exceptions (modifiers) in the next section.

**2)** “WITH” binary operator (similar to AND/OR) to be added to the
SPDX Specification. It denotes that the license identified by the SPDX
short name identifier is modified by a well-defined exception on a new
“SPDX Modifier List” as described in section (3). As a result, all
current licenses that include the term “exception” in the “Full Name”
will be deprecated.

  - Example: “GPL-2.0-with-bison-exception” will be deprecated but the
    following expression, which achieves the same result, is now valid:
    “GPL-2.0 WITH bison-exception”.

**3)** The Legal Team will be responsible for creating and maintaining
the canonical list of SPDX License List modifiers (i.e. “auto-conf-
exception, bison-exception”). It should be noted that licenses that are
deprecated will be able to be expressed (more eloquently) with the new
changes; hence no license will “fall off” the SPDX License List, nor
will this create a compatibility issue. URL references to all deprecated
licenses will be maintained for full backward compatibility.

  - For example: the following is now a valid expression: “GPL-2.0+ WITH
    bison-exception” where the “+” and “WITH” operators allow a more
    flexible expression to be constructed. Prior to this addition this
    expression was not easy to express.

**Longer Term Solution**:

Add capability for users to define modifier references local to an SPDX
document, analogously the way LicRef is used for licenses not on the
License List. This will involve adding “ModRef” to the SPDX
Specification so the following would be a valid expression: “GPL-2.0
WITH ModRef23.” Where ModRef23 provides the text of a license modifier
that does not appear on the SPDX Modifier List. In the initial proposed
solution, the way to express a file with a GPL-2.0 license with an
exception, that is not included on the SPDX Modifier canonical List,
will be by including the full text of the license and the exception as a
single LicRef (which is the current state of affairs as well).

**Rationale:**

The proposed solution will provide the SPDX community the ability to
express more licenses and license combinations in a more elegant and
meaningful (human consumable) way then is currently available under the
existing SPDX Specification and License List. To the extent that the
SPDX community has come to rely on any of the licenses superseded by the
new specifications those licenses will still be available on the SPDX
License List (although deprecated). Finally, the initial proposed
solution is a major improvement to the current situation and is easily
extensible to the even more flexible longer term solution without
impacting the current timeline for SPDX 2.0.

[Category:Legal](Category:Legal "wikilink")
[Category:Legal](Category:Legal "wikilink")
