<big>**SPDX Legal Team projects for 2015**</big>

We will try to not delete items, but mark them as "DONE" to serve as a
record of progress over the course of the year.

LAST UPDATED: 5 May 2015

## Licenses Under Review

  - Owner: Dennis Clark
  - Timeframe: On-going
  - New license or exception requests are tracked here:
    <https://docs.google.com/spreadsheets/d/11AKxLBoN_VXM32OmDTk2hKeYExKzsnPjAVM7rLstQ8s/edit?pli=1#gid=695212681>

## Update & Maintain SPDX License List

  - Owner: Jilayne Lovejoy
  - Timeframe: On-going
  - Add new licenses or make other changes to license list and
    associated web pages as needed. Push changes to Git repository and
    coordinate with Gary to make sure new versions are tagged and
    uploaded to spdx.org

## Standard Headers

  - Owner: ??
  - Timeframe: resolve for ??? release
  - the move to v2.0 creates some issues for the Standard Header field
    of the SPDX License List:

<!-- end list -->

1.  for the GNU family of licenses, the "or later" determination is made
    in the header text; pre-2.0, the GNU licenses were listed as two
    line items each, so the difference in the header (e.g., presence or
    absence of "or later') was accommodated in the Standard Header field
    for each license. As of 2.0 and with the addition of the SPDX
    License Expression syntax the 'or later' option is exercised via the
    + operator. In light of this, what do about the standard header?
2.  Some Standard Headers have replaceable text. While the License
    Matching Guidelines are stated to apply to the Standard Headers,
    there is no markup in the Standard Headers - should there be?
3.  Some licenses have more than one suggestion for a Standard Header -
    how do we accommodate this?

## Fedora / OSI outstanding issues

  - Owner: Jilayne Lovejoy
  - Timeframe: complete by end of 2015

<!-- end list -->

1.  Jabber Open Source License v1.0 – archived text here
    (http://archive.jabber.org/core/JOSL.pdf) is not the same as the OSI
    has on their site (it was OSI approved). What do we do about this?
    need to resolve with OSI (with goal of having on list b/c it was OSI
    approved and we endeavored to have all OSI licenses on SPDX list,
    even if old). license text also can be found at:
    <http://code.google.com/p/jabber-net/wiki/FAQ_License>
2.  various OSI approved (but old or deprecated) licenses don't have
    corresponding link on OSI site; OSI to update and then SPDX to add
    link to SPDX-LL - check this??
3.  other issues with Fedora list, identified when we went through that

## Fedora / SPDX short identifiers comparison and review

  - Owner: Jilayne Lovejoy
  - Timeframe: complete by end of 2015
  - Need to finish creating spreadsheet with comparison chart and then
    send to / confer with Tom Calloway at Fedora

## Composite Licenses

  - Owner: Sam Ellis?
  - Timeframe: future
  - some licenses currently on the SPDX License List are actually
    composite licenses or license stacks; should these be broken apart
    and the SPDX License Expression used? Some discussion on this issue
    took place earlier this year, see:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-01-08>
  - determined that this would require a case-by-case review and should
    be targeted for post-2.0 timeframe

## Add a Suggested Header field to SPDX License List

  - Owner: Mark Gisi
  - Timeframe: future
  - proposal to add a field for a recommended header for licenses that
    do not have a Standard Header. Some discussion here:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-04-30>

## Community Outreach

  - what would this look like?

## Other projects from 2014 list

### Legal Team recruitment and initiation

  - how do we get more people involved?
  - when new people join, should we assign them an SPDX "buddy' to help
    answer questions and otherwise shepherd them into the group?
  - who to target and how to reach them?
  - ask for help from LF or via grassroots effort or both? other ideas?

### Alignment with other license lists

Coordinate with various other license lists to make sure SPDX has
licenses from these lists and check short name matching (or create
"translation" document if different)

#### FOSSology

owner: TBD assigned

  - coordinate with Bob Gobeille, see
    <http://www.fossology.org/projects/fossology/wiki/MatchSPDXLicenceIDs>

#### Gentoo

owner: TBD assigned

#### Suse

owner: TBD assigned

  - list found here:
    <https://docs.google.com/spreadsheet/pub?key=0AqPp4y2wyQsbdGQ1V3pRRDg5NEpGVWpubzdRZ0tjUWc>
    (courtesy of Ciaran Farrell)

### Recommendations or guidance on how to best determine license for a particular file

'how to identify the license for an open source project - ex. Within the
file versus whether there's a copying file on top of the directory ?
provide guidance/suggstion (industry practice?) that license in the file
is more determinate than the license in the directoryShould the legal
group aggregate industry best practices and come up with a group of
guidelines and provide some influence on that?

[Category:Legal](Category:Legal "wikilink")
