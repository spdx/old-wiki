Below is a class diagram merging Ed Warnicke's proposed SPDX Element
model with the 1.0 model. Definitely a work in progress. Most of the
class definitions can be found in the 1.0 spec in the RDF appendix
(model) or in [Ed's
proposal](Technical_Team/Proposals/Rough_proposal_for_provenance,_hierarchy_and_aggregation,_and_supply_chain_friendliness_in_SPDX_2.0 "wikilink").

The goals of this proposal are to:

  - Support the use cases for the 2.0 spec
  - Support the supply chain use cases (included in the use cases for
    the 2.0 spec)
  - Support the "hierarchical" or embedded package use cases
  - Provide a more abstract model which can simplify the application of
    SPDX to some of the more complex use cases

This proposal extends the existing proposals by adding an SPDX Element
Relationship which describes the type of relationship from one SPDX
element to another.

See the attached document for the mapping between the SPDX 1.0
properties and this proposal.

See the attached document for a proposal on creating RDF references to
other Licensable documents which can be verified through checksums.

Model updated on April 1, 2014 with the results from the Linux Collab
Summit.

![Class Diagram](Model-4-1-2014.png "Class Diagram")

**Relationship Type and Usage Type Definitions** being fleshed out on
this Google Doc
<https://docs.google.com/spreadsheets/d/13MuhIhmdSx5e9B7OCuz_CUoYRtAu-WU08SbIMlym5Xc/edit?usp=sharing>

Yet another Google Doc, this one for correlating Model support for 2.0
Use Cases
<https://docs.google.com/spreadsheet/ccc?key=0AhWBVUYWeqV1dC01TGE5eERTdVJqMlZSUWwwZHItaWc&usp=drive_web#gid=0>

Element Identifier proposal (such that an element can be uniquely
referred to - IN DRAFT)
<https://docs.google.com/document/d/1gNtAYs7IhlGE4SWAXUIIWwpZmEvr4Jz9Ep1MNswyWBk/edit#heading=h.yg1m5fn32gf3>

[Category:Technical](Category:Technical "wikilink")
