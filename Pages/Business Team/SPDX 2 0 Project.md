**<big>SPDX 2.0 Specification Project Overview</big>**

\_\_TOC\_\_

  

# Objectives

This is the next major release of the specification. SPDX 2.0 will
extend the specification beyond the package level scope and enhance it
to address relationships between artifacts.

You can read up on the user requirements and stories here [User
Requirements and
Stories](http://wiki.spdx.org/images/SPDX-TR-2014-3.v1.0.pdf)

  

## Overall Status

New plan is to launch the specification by Linux Collab 2015 which is in
February . This looks very doable as the first draft of the
specification was put onto the technical team mailing list on 11/17.

  

# Milestones

The target date is set by the Milestone owner. When completed, the date
will be changed to say COMPLETE. The milestone owner should also update
the Status column as appropriate.

| Milestone                                   | Owner                | Details                                                                                                                                                              | | Target Date                 | Current Status                                                                                           |
| :------------------------------------------ | :------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- | -------------------------------------------------------------------------------------------------------- |
| Use Cases                                   | Tech Team            | Collection of use cases and then prioritization on the ones that will be addressed in the 2.0 specification.                                                         | COMPLETE                      |                                                                                                          |
| Requirements Overview                       | Kirsten Newcomer     | High level requirements overview.                                                                                                                                    | COMPLETE                      | <http://wiki.spdx.org/images/SPDX-TR-2014-3.v1.0.pdf>                                                    |
| Fedora License List                         | Legal Team           | finish review of Fedora "good" license list and add licenses to SPDX License List for next version (to coincide with version 2.0 of spec release)                    | COMPLETE                      | in progress                                                                                              |
| License Expression Language                 | Legal Team           | draft license expression language text for inclusion in spec                                                                                                         | COMPLETE                      | Has had legal and tech team review. Is in the specification.                                             |
| Object Models                               | Tech Team            | Modeling to support the new use cases. This is the model we are using: [Merged Model Proposal](Technical_Team/Proposals/2012-02-01/Merged_Model_Proposal "wikilink") | COMPLETE                      | [SPDX 2.0 Model](Technical_Team/Model_2_0 "wikilink").                                                   |
| Validate Use cases                          | Tech Team            | See use cases here: [SPDX 2.0 Use Cases](Technical_Team/Use_Cases/2.0 "wikilink"). Need to validate these against the data model.                                    | COMPLETE                      | In Progress. Several of the use cases were reviewed at Linux Collab.                                     |
| License Matching templates                  | Legal Team           | all licenses reviewed and templates created as needed                                                                                                                | for 2.0                       | mostly complete as of SPDX License List 2.0-rc2                                                          |
| SPDX Tools and Examples Updates             | Tech Team            | All SPDX tools and examples updated to support 2.0                                                                                                                   | RC2 or RC3 as starting point? | Need to recruit someone for the tag-value format tools                                                   |
| Migration Plan Draft Review Period          | Tech Team            | How to go from v1.2 documents to 2.0 format                                                                                                                          | TBD                           | Kate and Jack to work on                                                                                 |
| SPDX 2.0 RC 1                               | Tech Team            | First draft of specification out to Technical team mailing list for review. Feedback back by December 1st.                                                           | COMPLETE 11/14                | <https://docs.google.com/document/d/1wE_zvLU4c291ACi9wIJmQoE4ltKRW4rzM1TYiIvEVOs/edit?pli=1>             |
| SPDX 2.0 RC 2                               | Tech Team            | Specification is out for review by the general community.                                                                                                            | 12/18                         | Can start tool development on this version? Update banner on site with link to specification for review. |
| SPDX 2.0 RC 3 Best and Final                | Tech Team            | Best and final version of the specification is out for a final blessing.                                                                                             | Jan 15 2015                   |                                                                                                          |
| SPDX 2.0 Specification Complete             | Tech Team            | Published.                                                                                                                                                           | Feb 15 2015                   |                                                                                                          |
| Migration Plan Best and Final Review Period | Tech Team            | How to go from v1.2 documents to 2.0 format                                                                                                                          | TBD                           |                                                                                                          |
| Update slide set resources                  | Business Team (Phil) | Update slide resources to 2.0                                                                                                                                        | By RC3                        | <http://spdx.org/publications/resources/spdx-slideset>                                                   |
| Update SPDX Whitepaper                      | Business Team (Phil) | Update whitepaper to 2.0                                                                                                                                             | By RC3                        | <http://www.linuxfoundation.org/sites/main/files/publications/lf_foss_compliance_spdx.pdf>               |
| Press release drafted and sent to LF        | Business Team        | Press release announcing 2.0 is drafted and sent to LF to review and publish.                                                                                        | Shoot for 2nd week of January | Contacting prospective companies to get quotes.                                                          |

2.0 Milestones

  

# Useful Links

The following are links to useful information around the 2.0
Specification.

  - [What is a Specification Release
    Checklist](Technical_Team/Spec_Release_Process "wikilink")
  - [SPDX 2.0 Use Cases](Technical_Team/Use_Cases/2.0 "wikilink")
  - [SPDX 2.0 Model ](Technical_Team/Model_2_0 "wikilink")
  - [Schema](http://spdx.org/rdf/ontology/spdx-2-0-rev-11/)
  - [ SPDX\_Specification\_Versions (see dated 2.0
    drafts)](Technical_Team/SPDX_Specification_Versions "wikilink")
  - Bug reports (may be useful to look at those targeted against 2.0 for
    completion)
  - Linux Collab 2014 Summit: [LinuxCollab Meeting
    Minutes](http://wiki.spdx.org/view/Technical_Team/Minutes/2014-03-25)

  

# Specification Release Checklist

This checklist will be used as the Specification approaches release. It
is to make sure we do no forget something.

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

[Category:Business](Category:Business "wikilink")
