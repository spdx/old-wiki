1.  **Title:** Debian has an interest in only building things that are
    linking license compatible
2.  **Primary Actor:** Builder of binary copyrightable artifact
3.  **Goal in Context:** To be able to determine from the SPDX data of
    the source and libraries linked into a binary executable what
    licenses are in play so that judgements can be made about license
    compatibility.
4.  *' Stakeholders and Interests:*'
    1.  '''Binary Builder: '''
        1.  To understand the license information about the source code
            and libraries linked into the binary they are building.
5.  **Preconditions:**
    1.  Binary builder has some way to understand what source is built
        into their binary
    2.  Binary builder has some way to understand what libraries are
        linked into their binary
    3.  Binary builder has some understanding of the license informatino
        for the source built into their binary and an expression of it
        in SPDX form.
6.  **Main Success Scenario:** Binary builder can determine the licenses
    of all the source code and libaries that are linked into their
    binary.
7.  '''Failed End Condition: '''Binary builder can determine the
    licenses of all the source code and libaries that are not linked
    into their binary.
8.  **Trigger:**
    1.  Binary build time
    2.  Commit time?
9.  **Notes:** In a nutshell, we think this Use Case is asking for SPDX
    data to make licensing info machine readable to a build system, and
    that the license info of a binary be tied somehow to the license
    info of the source that went into it. So that someone can write
    logic around their build system based on what they may or may not
    deem to be acceptable license combinations in their build

[Category:Technical](Category:Technical "wikilink")
