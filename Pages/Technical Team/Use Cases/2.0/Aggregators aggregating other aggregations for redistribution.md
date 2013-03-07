1.  **Title:** Aggregators aggregating other aggregations for
    redistribution
2.  **Primary Actor: Aggregator of aggregations**
3.  **Goal in Context:** To allow an aggregator of aggregations to
    express in SPDX the internal structure of what the copyrightable
    artifacts they are shipping are, how they are organized
    hierarchically, and the licensing information for all of it.
4.  **Stakeholders and Interests:**
    1.  ''**'Aggregator of aggregations**: '''
        1.  To communicate the licensing information for their aggregate
            of aggregations including the internal structure and
            provenance.
    2.  **Consumers of Embedded Images:**
        1.  To receive accurate and clear information of licensing of
            the aggregate and all they contain.
        2.  To be able to comply easily with licenses for the aggregate
            and all it contains.
        3.  To be able to trust that the aggregate SPDX data is in
            alignment with the upstream maintainers license assertions
            of the pieces it contains.
5.  **Preconditions:**
    1.  Aggregator of aggregates understands the things it contains,
        including any SPDX data if provided.
6.  **Main Success Senario:** Aggregator of aggregates communicates
    accurate complete licensing information for their package in an SPDX
    data format for the Aggregate and all it contains.
7.  **Failed End Condition:** Aggregator of aggregates does not
    communicates accurate complete licensing information for their
    package in an SPDX data format for the Aggregate and all it
    contains.
8.  **Trigger:**
    1.  Release of a new aggregate.
9.  **Notes:**

[Category:Technical](Category:Technical "wikilink")
