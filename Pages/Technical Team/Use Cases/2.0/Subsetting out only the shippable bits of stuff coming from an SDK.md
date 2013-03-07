1.  **Title:** Subsetting out only the shippable bits of stuff coming
    from an SDK
2.  **Primary Actor: User of an SDK**
3.  **Goal in Context:** To allow an SDK User to subset out the bits of
    the SDK that are shipping in their outgoing copyrightable artifact
    so that they can communicate the licensing information for what they
    are actually shipping as SPDX data.
4.  **Stakeholders and Interests:**
    1.  User of an SDK
        1.  To communicate the licensing information for what parts of
            the SDK they are actually shipping.
    2.  **Consumers of Embedded Images:**
        1.  To receive accurate and clear information of licensing of
            the aggregate and all they contain.
        2.  To be able to comply easily with licenses for the aggregate
            and all it contains.
        3.  To be able to trust that the aggregate SPDX data is in
            alignment with the upstream maintainers license assertions
            of the pieces it contains.
5.  **Preconditions:**
    1.  SDK comes with SPDX data.
6.  **Main Success Senario:** SDK User can communicate accurately what
    parts of the SDK they ship and what the licensing information is for
    those pieces.
7.  '''Failed End Condition: '''SDK User cannot communicate accurately
    what parts of the SDK they ship and what the licensing information
    is for those pieces.
8.  **Trigger:**
    1.  Release of a new SDK based deliverable.
9.  **Notes:**

[Category:Technical](Category:Technical "wikilink")
