1.  **Title:** Application which ships with a contrib libraries
2.  **Primary Actor:** Committer of the open source project containing
    the contrib library
3.  **Goal in Context:** To include within the distribution of an open
    source project contributions made by non-project members. These
    contributions are by default not built into the resultant binaries
    (assuming there are build scripts included in the distribution).
    There can be no dependency from the main project on the contrib
    code. The contrib libraries may contain licenses different from the
    main open source project.
4.  **Stakeholders and Interests:**
    1.  '''Committers to the open source project: '''
        1.  Isolates the contrib copyrighted artifacts so that any
            copyleft licenses will not impact the overall licensing of
            the project (including the project committers copyrighted
            works).
    2.  **Contributors to the contrib library:**
        1.  Allow the contributors to make their contributions available
            under the license of their choice
    3.  **Consumers of upstream copyrightable artifacts:**
        1.  To receive accurate and clear information of licensing of
            artifacts
        2.  To be able to distinguish copyrighted artifacts intended for
            be build and distributed as part of the project from
            optional copyrighted artifacts which may or may not be
            included
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
5.  **Preconditions:**
    1.  Project has been organized with clear distinctions between the
        contrib and main project artifacts
    2.  Licensing information has been collected for the contrib and
        main project artifacts
6.  **Main Success Scenario:** Committer provides complete licensing
    information and an indication of which artifacts are part of the
    main project and which artifacts are part of a contrib library. Each
    contrib library will contain information on licensing.
7.  **Failed End Condition:** Committer does not specify an artifact is
    part of a contrib library causing confusion on the applicable
    license for the overall project.
8.  **Trigger:**
    1.  Project release
    2.  Contrib updates
9.  **Notes:** This use case is from the perspective of a committer who
    is assembling/aggregating additional contributed code for further
    distribution. The downstream recipient of the package may choose to
    use one of the contrib items as part of their delivery could alter
    the licensing for the aggregated work product. The downstream
    recipient could also remove the contrib artifacts completely. Allow
    the model to represent that application is 'seperable'.
10. **Example:** Postgresql, which ships under a BSD license overall,
    contains a contrib/ directory that contains GPL licensed code.

[Category:Technical](Category:Technical "wikilink")
