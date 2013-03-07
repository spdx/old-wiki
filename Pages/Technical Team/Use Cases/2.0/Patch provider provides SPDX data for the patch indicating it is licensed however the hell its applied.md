1.  **Title:** Patch provider provides SPDX data for the patch
    indicating it licensed matching whatever files it applies to.
2.  **Primary Actor:** Patch Provider
3.  **Goal in Context:** To indicate the licensing information as SPDX
    data for the patch.
4.  **Preconditions:**
    1.  Committer simply wants his patch to have licensing information
        matching the code it's applied to.
    2.  (the code being patched may likely not even have SPDX data with
        it to begin with)
5.  **Stakeholders and Interests:**
    1.  **Patch Provider:**
        1.  To communicate that the patch should be licensed the same
            way as the code it applies to.
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
    patch is licensed matching the licenses of the files it is applied
    to.
7.  **Failed End Condition:** Patch supplier communicates inaccurate
    incomplete licensing information for their patch.
8.  **Trigger:**
    1.  Creation of a patch
9.  **Notes:** This probably involves work with the legal group around
    an ASLICENSEDAS-1.0 short form, which would involve drafting a
    license indicating this, and such a license should probably exclude
    intentional indications of other licenses (say if the patch actually
    changed license information in the files deliberately).

[Category:Technical](Category:Technical "wikilink")
