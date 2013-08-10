**SPECIFICATION RELEASE PROCESS AND CHECKLISTS**

**Status:** DRAFT (not reviewed yet)

  
\_\_TOC\_\_

  

## Introduction

The overall process for releasing a version of the specification can
involve many people from different teams within the SPDX workgroups.This
document and the accompanying checklists are meant to explain how a
change to the specification is drafted, released and the steps and
collateral that need to be updated along the way. This should serve to
not only clarify the process for the SPDX Community but to also avoid
any bumps in the road along the way.

## The Process

Updates to the specification are normally planned and appear on the
[SPDX Roadmap](http://spdx.org/documentation/publications). From time to
time and as circumstances dictate, smaller point revisions to the
specification (i.e. a dot version) will be announced. In general, we
tend to release versions of the specification around the Linux
Collaboration Summit and LinuxCon North America Conferences.

Sources for changes to the specification normally come from bug reports
in the [bugzilla
system](https://bugs.linuxfoundation.org/buglist.cgi?query_format=specific&order=relevance+desc&bug_status=__open__&product=SPDX)
maintained by the Linux Foundation for SPDX. Items being incorporated
into the specification will have their target release set to the version
of the SPDX specification being drafted (i.e. 1.2, 1.3, 2.0, etc). Other
possible sources for incorporation can come from planned tooling
plugfests, feedback from users and so forth. In general, these will be
documented as bugs before inclusion.

When work is planned on a new version, the Technical team lead will
announce the version on the general mailing list along with a short
summary of what changes are going to be addressed (we may not yet know
"how" they will be fixed). The Business team will then update the
Roadmap (if necessary) along with the predicted release date. Anyone
wishing to participate in the drafting/review of the specification
should be on the Tech team mailing list and if possible attend the tech
team calls.

Work on the specification will done using Google Docs. Non editors for
the release can review and comment there. Editors will have access to
make changes. Editors get edit privilege from the Tech team lead. **You
are strongly encouraged to be part of the process, commenting along the
way. Nothing is worse then getting to the end and then realizing one or
more individuals have issues with something.** Note: Google docs offers
some advantages over using the wiki for editing like this. In the future
we may use something else.

As work progresses on the draft, periodic review versions will be
announced by the Tech Team lead on the SPDX mailing lists. Therefore if
you are a casual reviewer you can use these triggers to review the new
changes without having to keep your finger on the specific pulse of
things.

When all changes have been made to the specification and the tech team
/editors are in agreement that this is ready to go, a Best and Final
approval notice will be sent to the General List. Note that we generally
use Lazy Consensus as defined in our [Governance
document](http://spdx.org/about-spdx/governance) when approving
something.

In parallel to the document updates, the RDF terms pages will be
updated. Bugzilla is used to coordinate changes between the spec and the
RDF terms. Once the spec has been updated for a particular bug, the bug
is reassigned to the individual maintaining the RDF terms. The RDF terms
maintainer will update the RDF terms and post intermediate changes to
\[TBD\]. Prior to release, the RDF terms will be reviewed by members of
the technical workgroup. Once the RDF terms have been updated for a
particular bug, it will be reassigned to the individual maintaining the
tools to track changes required in the SPDX tools.

### Tools

The SPDX workgroup tools will be updated and released as part of the
specification.

Once the SPDX RDF terms and the SPDX documents have been updated and
reviewed, the tools will be updated to support the specification.

An early version of the tools will be made available to the SPDX tech
workgroup for testing prior to release.

The updated tools will be uploaded to the SPDX tools web pages found at
<http://spdx.org/spdx-tools/tools-from-the-spdx-workgroup>.

SPDX workgroup tools are designed to be backwards compatible supporting
previous versions of the specification.

The file "changelog" in the root source directory for the tools provide
information on which SPDX document versions are supported by the tools
version.

For comment:

  - Do we tie versions of the tools to the spec version? \[Gary\] -
    Right now this is just in the source file. We probably should
    produce a mapping of the tools version to SPDX version on the web
    page itself.
  - The tools need testing prior to release. I suggest at least three
    independent people must test before release (not including the
    people who worked on the tool). \[Gary\] - Agree - updated
  - is there a lag to the tool release? \[Gary\] - Would like to have
    the tools available at the same time as the release.

### License List Incorporation

Every release of the specification includes the latest published version
of the License List. In general, if you look at the roadmap the SPDX
Group will do an update of the License List before a planned
specification is released (assuming there are updates to the list).

## Specification Review Checklist

|                                                                                   |                    |        |
| --------------------------------------------------------------------------------- | ------------------ | ------ |
| Item                                                                              | Who is Responsible | Status |
| Notification of start of work on a new version to the General List (with summary) | Tech team lead     |        |
| Web site updated with page to hold new spec version (points to google doc repro)  | Web Admin          |        |
| Web site news announcement (in banner area) that draft is under way               | Web Admin          |        |

Specification Review Checklist

## SPDX Specification / Document Collateral Release Checklist

|                                                                         |                    |        |
| ----------------------------------------------------------------------- | ------------------ | ------ |
| Item                                                                    | Who is Responsible | Status |
| Notification on general list that the specification is approved         | Tech team lead     |        |
| Web site updated with page to hold new spec version                     | Web Admin          |        |
| RDF terms page updated                                                  | Web Admin          |        |
| Web site news announcement (in banner area) that there is a new version | Web Admin          |        |
| Press release (via Linux Foundation) for the new version                | Business Team      |        |
| Roadmap updated to show specification release                           | Business Team      |        |

Specification Release Checklist

## SPDX Tools Release Checklist

|                                                              |                       |        |
| ------------------------------------------------------------ | --------------------- | ------ |
| Tool                                                         | Who is Responsible    | Status |
| Spreadsheet Template and Examples updated                    | Tech team tools group |        |
| RDF to Tag and Tag to RDF Translators updated                | Tech team tools group |        |
| RDF to HTML Pretty Printer updated                           | Tech team tools group |        |
| Spreadsheet to RDF and RDF to spreadsheet updated            | Tech team tools group |        |
| SPDX Compare updated                                         | Tech team tools group |        |
| SPDX Viewer updated                                          | Tech team tools group |        |
| Spreadsheet Template and Examples posted to web site         | SPDX Web Admin        |        |
| RDF to Tag and Tag to RDF Translators posted to web site     | SPDX Web Admin        |        |
| RDF to HTML Pretty Printer posted to web site                | SPDX Web Admin        |        |
| Spreadsheet to RDF and RDF to spreadsheet posted to web site | SPDX Web Admin        |        |
| SPDX Compare posted to web site                              | SPDX Web Admin        |        |
| SPDX Viewer posted to web site                               | SPDX Web Admin        |        |

Tool Release Checklist

## Review Comments

Place review comments here. They will be reviewed when its ready to go.

We should add the RDF terms updates to the process. I have some of the
information, but not enough detail to post - Gary

[Category:Technical](Category:Technical "wikilink")
