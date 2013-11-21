This page brings together various modelling proposals for 2.0 under a
common page. The models currently under discusson are shown below with a
brief excerpt from the page:

## [Rough Conceptual Model](Technical_Team/Proposals/Yet_another_rough_proposal_for_conceptual_model_of_SPDX_2 "wikilink")

"This conceptual model is an attempt to incrementally add hierarchy and
provenance capabilities to the existing SPDX model. Many of the [use
cases](Technical_Team/Use_Cases/2.0 "wikilink") have been considered but
further analysis is necessary to ensure that this model covers all
scenarios. ..."

## [Provenance and Supply Chain Model](Technical_Team/Proposals/Rough_proposal_for_provenance,_hierarchy_and_aggregation,_and_supply_chain_friendliness_in_SPDX_2.0 "wikilink")

"A desire has been expressed to be able to have SPDX be capable of
expressing

1.  [Provenance](Technical_Team/SDPX_2.0_Provenance "wikilink") (we can
    know precisely who said what and when about a package)
2.  Hiearchy and Aggregation ( package A contains packages B, C, etc)
3.  How software flows through a supply chain (upstream to packager,
    through several intermediate vendors to consumer) ..."

## [Merged Model Proposal](Technical_Team/Proposals/2012-02-01/Merged_Model_Proposal "wikilink")

"Below is a class diagram merging Ed Warnicke's proposed SPDX Element
model with the 1.0 model. Definately a work in progress. Most of the
class definitions can be found in the 1.0 spec in the RDF appendix
(model) or in [Ed's
proposal](Technical_Team/Proposals/Rough_proposal_for_provenance,_hierarchy_and_aggregation,_and_supply_chain_friendliness_in_SPDX_2.0 "wikilink").

The goals of this proposal are to:

  - Support the use cases for the 1.0 spec
  - Support the supply chain use cases
  - Support the "hierarchical" or embedded package use cases
  - Provide a more abstract model which can simplify the application of
    SPDX to some of the more complex use cases ... "

## [Usage Relationship Proposal](Technical_Team/Proposals/2012-02-01/Usage_Relationship_Proposal "wikilink")

"Modification to the Merged Model Proposal to move the Usage property
from the SPDXElement to the SPDXElementRelationship"

[Category:Technical](Category:Technical "wikilink")
