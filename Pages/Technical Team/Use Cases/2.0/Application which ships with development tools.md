1.  **Title:** Application which ships with development tools
2.  **Primary Actor:** Committer of the open source project containing
    the contrib library
3.  **Goal in Context:** To include within the distribution of an open
    source project development tools used to build a deployable
    executable (or executables) from the open source code. These
    development tools would not be included in any resultant executable
    and may be under a different license than the stated license for the
    project.
4.  **Stakeholders and Interests:**
    1.  '''Committers to the open source project: '''
        1.  Makes clear which copyrightable artifacts are intended to be
            used only at development time and is not intended to be
            distributed with any executables.
    2.  **Consumers of upstream copyrightable artifacts:**
        1.  To receive accurate and clear information of licensing of
            artifacts
        2.  To be able to distinguish copyrighted artifacts intended to
            be build and distributed as part of the project from build
            tools intended to be used at development time
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts
5.  **Preconditions:**
    1.  Project has been organized with clear distinctions between the
        build tools and other project artifacts
    2.  Licensing information has been collected for the build tools and
        main project artifacts
6.  **Main Success Scenario:** Committer provides complete licensing
    information and an indication of which artifacts is part of the main
    project and which artifacts are part of the build tools. Each build
    tool will contain information on licensing.
7.  **Failed End Condition:** Committer does not specify an artifact is
    part of the build tools causing confusion on the applicable license
    for the overall project.
8.  **Trigger:**
    1.  Project release
9.  **Notes:** This use case is from the perspective of a committer who
    is assembling/aggregating additional build tools for further
    distribution. Although the intent of the committer for the build
    tools has been made, the downstream recipient may choose to use the
    build tools in a different manner (e.g. include some of the source
    in the main project itself). The downstream recipient may also
    replace or remove the build tools.
10. **Example:** Wireshark, a network analyzer licensed under GPLv2,
    contains in it's source base piddle, which is GPLv3, but is solely
    used as a tool for building wireshark, and no part of which goes
    \*into\* any of the binary artifacts built out of Wireshark.

[Category:Technical](Category:Technical "wikilink")
