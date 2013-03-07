1.  **Title:** Patch provider provides patch subject to existing SPDX
    data of project
2.  **Primary Actor:** Patch Provider
3.  **Goal in Context:** To indicate the licensing the patch is licensed
    subject to the specific SDPX data of the project.
4.  **Preconditions:**
    1.  Committer simply wants his patch to have licensing information
        matching the project its applied to.
    2.  The project to which the patch applies has existing SPDX data to
        refer to.
5.  **Stakeholders and Interests:**
    1.  **Patch Provider:**
        1.  To communicate that the patch should be licensed the same
            way as the overall project it's contributed to by
            referencing the projects SPDX data.
    2.  '''Upstream maintainers: '''
        1.  To be able to document the license information for the
            patches they receive
        2.  To have a paper trail of the licensing information for their
            project.
        3.  To have their licenses respected
    3.  **Third party patch appliers (think Yocto):**
        1.  To be able to know whether or not they have licensing issues
            when they apply a patch to upstream.
    4.  **Consumers of upstream source:**
        1.  To receive accurate and clear information of licensing of
            upstream source
        2.  To be able to comply easily with licenses for upstream
            source
        3.  To be able to subset, extend, or aggregate artifacts and
            pass on clear authoritative verifiable license for the
            resulting new copyrightable artifacts.
6.  **Main Success Senario:** Patch supplier communicates that their
    patch is licensed matching the SPDX data specified for the project.
7.  **Failed End Condition:** Patch supplier communicates inaccurate
    incomplete licensing information for their patch.
8.  **Trigger:**
    1.  Creation of a patch

[Category:Technical](Category:Technical "wikilink")
