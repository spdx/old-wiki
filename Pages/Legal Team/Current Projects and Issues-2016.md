## SPDX Legal Team projects for 2016

### Licenses Under Review

  - Owner: Dennis Clark
  - Timeframe: On-going
  - New license or exception requests are tracked here:
    <https://docs.google.com/spreadsheets/d/11AKxLBoN_VXM32OmDTk2hKeYExKzsnPjAVM7rLstQ8s/edit?pli=1#gid=695212681>
  - **Licenses "on hold" or other licenses to consider** - try to clear
    those on hold to a decision point:
      - Open Game License v1.0a - discussed
        <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-12-10> -
        needs more research (Alan Tse) - DONE (see
        <http://wiki.spdx.org/view/Legal_Team/Minutes/2016-01-07>)
      - Open Government Licence v3.0 - need more info from person who
        submitted it re: older versions; mark for re-review and need
        someone to reach out to submitter, Mike Linsvayer (WHO?)
      - W3C Document Notice and License (2 versions) -
        documentation/specification license, delayed decision. need to
        re-assess (WHO?)
      - OCaml linking exception - on hold waiting for more info
        <http://lists.spdx.org/pipermail/spdx-legal/2015-July/001465.html>.
        need to reach out to Camille to see if he has found out anything
        further (Jilayne Lovejoy) -
      - various other exceptions on "waiting list" - see spreadsheet.
        Need someone to research, as needed and lead discussion for
        these (WHO?)
      - OSI recently approved this license:
        <http://opensource.org/licenses/OPL-2.1> - note the short
        identifier used in the license header is the same as another
        license (but different version number) already on the SPDX
        License List. We need to add to list and sort out short
        identifier...

### Update & Maintain SPDX License List

  - Owner: Jilayne Lovejoy
  - Timeframe: On-going
  - Add new licenses or make other changes to SPDX License List. Push
    changes to Git repository and coordinate with Gary to make sure new
    versions are tagged and uploaded to spdx.org
  - SPDX License List releases to follow quarterly schedule unless no
    changes or compelling reason to release sooner.
  - Make updates to description on spdx.org/licenses, and all other key
    pages (e.g., items in bulleted list there).

#### Other Licenses or License List related issues

  - **License exception or note on license interpretation?** - Sam Ellis
    requested to add this as an exception:
    <http://repo.gem5.org/gem5/file/021524c21cbc/src/cpu/exec_context.cc>
    and comment from Oliver that this is similar to Linus' note re:
    derived work in kernel. Are these exceptions or clarifications of
    the interpretation of the license itself? Either way, how does SPDX
    want to handle them?
  - **Jabber Open Source License v1.0** - archived text here
    (http://archive.jabber.org/core/JOSL.pdf) is not the same as the OSI
    has on their site (it was OSI approved). What do we do about this?
    need to resolve with OSI (with goal of having on list b/c it was OSI
    approved and we endeavored to have all OSI licenses on SPDX list,
    even if old). license text also can be found at:
    <http://code.google.com/p/jabber-net/wiki/FAQ_License>
  - **Composite Licenses** - some licenses currently on the SPDX License
    List are actually composite licenses or license stacks; should these
    be broken apart and the SPDX License Expression used? Some
    discussion on this issue took place in 2015 (but decided to wait
    until after 2.0 release). See:
    <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-01-08>
  - **Standard Headers with "or later" delineation** - where the
    determination as to whether a specific license version or the "or
    later version" applies is made via a standard header, how does 2.0
    with license expression and + operator capture this, in terms of
    matching, etc.

### Improving License Matching Markup / Move Maintenance of SPDX License List to Github

  - Owner:
  - Timeframe:
  - Joint discussion of legal and tech teams as to whether matching
    markup can be improved. Proposal for change provided by Kris
  - previous points of discussion, see
    <http://wiki.spdx.org/view/Legal_Team/Templatizing> for an overview
    and various related links from there
      - <http://wiki.spdx.org/view/Legal_Team/Minutes/2015-12-10>
