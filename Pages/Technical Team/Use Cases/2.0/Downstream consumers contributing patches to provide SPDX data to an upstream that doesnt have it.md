1.  **Title:** Downstream consumers contributing patches to provide SPDX
    data to an upstream that doesn't have it.
2.  **Primary Actor:** Downstream consumer
3.  **Goal in Context:** The downstream consumer would like to provide
    SPDX data to an upstream that doesn't have it such that upstream
    will accept it as representing their licensing and incorporate it
    into their source base.
4.  **Preconditions:**
    1.  Downstream consumer has analyzed upstream and assembled SPDX
        data matching what can be discovered about it.
    2.  Downstreams analysis is acceptable to upstream.
    3.  (SPDX patch provider may not have commit rights to the upstream
        project, hence providing SPDX data via patch mechanism)
5.  **Stakeholders and Interests:**
    1.  **Downstream Consumer providing patch:**
        1.  To move their analysis of the licensing information of the
            software into the upstream so that it can be shared from the
            root of the software
        2.  To gain legitimacy for their analysis by its acceptance by
            upstream.
    2.  '''Upstream maintainers: '''
        1.  To be able to document the license information for their
            project.
        2.  To have their licenses respected
    3.  **Consumers of upstream source:**
        1.  To receive accurate and clear information of licensing of
            upstream source
        2.  To be able to comply easily with licenses for upstream
            source
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
6.  **Main Success Scenario:** Upstream accepts SPDX data from
    downstream as being an accurate reflection of their licensing
    information and incorporates it into their source base.
7.  **Failed End Condition:** Upstream does not accept SPDX data from
    downstream and incorporate them into their source base.
8.  **Trigger:**
    1.  Submission of SPDX data to upstream for incorporation.

[Category:Technical](Category:Technical "wikilink")
