## Background

Work on the SPDX License List (SPDX-LL) began sometime in 2010. The
first SPDX-LL had approximately one hundred licenses on it. The initial
set of licenses was included based on informal discussion and consensus.
Although various "guidelines" were identified in regards to which
licenses to include or not during this time, formal guidelines were not
recorded beyond the meeting minutes. We had to start somewhere, and the
obvious was the easy beginning point. Decisions or guidelines that
evolved out of discussion or by implication included the following:

  - include commonly found open source licenses. Although discussion was
    not explicit in regards to how to define an "open source license,"
    this was always an implicit guiding principle
  - include all OSI approved licenses, both current and those approved
    but now deprecated. Rationale being that once OSI-approved, always
    OSI-approved and deprecated licenses still appear "in the wild"
  - in regards to "public domain": public domain dedications (because,
    it cannot technically be a "license"...) that are commonly found,
    well-established, or associated with a commonly found packages will
    be included on the SPDX-LL (e.g., ANTLR, Sax, CC-0). However, the
    idea of having a "generic" identifier for something that it released
    into the public domain was rejected after some discussion. (For more
    on public domain, see
    <http://wiki.spdx.org/view/Legal_Team/Decisions/Dealing_with_Public_Domain_within_SPDX_Files_(DRAFT)>
    .) This would not be practical for a number of reasons:
    1.  the concept of public domain does not necessarily translate
        across jurisdictions and the conditions under which a work can
        be released to the public domain vary on an country-by-country
        basis. Thus, having a short identifier could potentially only
        introduce ambiguity as to what that short identifier precisely
        means (and ambiguity - at least insofar as it comes to
        accurately identifying a license - is not the goal)
    2.  where something is noted with a public domain dedication, it can
        be captured the same was as any (other) license. That is, if it
        is something is part of the SPDX License List, it will have a
        short identifier, full name and exact text match like the
        examples above, and if it is not on the SPDX License List, it
        can be captured the same way as any (other) license not on the
        list via a license reference.
  - recognition that the need for a more formal process for requesting
    new licenses to be added to the SPDX-LL. Such a process was
    discussed in terms of an ideal goal and pragmatic approach for the
    current reality. A process that bridged the former, with more weight
    on the latter was implemented in April 2012.

## Current State

And that brings us to the waning days of 2012 when the need to make it
clear and transparent to the world what criteria we are using to
maintain this list in terms of determining when to "accept" or "reject"
a request to add a license to the SPDX-LL became impossible to ignore.
Repeated abbreviated discussions around the issue of "freeware" or open
source-ish licenses came up on a multiple occasions and so discussion
ensued and a first draft and one round of revisions were completed by
December 2012.

## Goal

The goal here is to come up with a set of guiding principles for
licenses to be added or not added to the SPDX-LL. This way, when a
license request is submitted the guidelines can be referenced (instead
of one-off rationales for each license, which is inefficient), thus
providing some consistency and reliable expectations for what the
SPDX-LL includes.

This goal was completed in early 2013; the guidelines are included on
the License List Overview page here:
<http://spdx.org/spdx-license-list/license-list-overview>

[Category:Legal](Category:Legal "wikilink")
