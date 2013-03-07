1.  **Title:** Embedded Images (e.g. router images, switch images)
2.  **Primary Actor:** Embedded Image creator
3.  **Goal in Context:** To allow an Embedded Image Creator to
    communicate the SPDX data for all of the copyrightable artifacts
    (packages, files, SDK components, etc) in the embedded image.
4.  **Stakeholders and Interests:**
    1.  '''Embedded Image Creator: '''
        1.  To communicate the licensing information for their
            copyrightable artifact (the image) including all
            copyrightable artifacts it contains.
    2.  **Consumers of Embedded Images:**
        1.  To receive accurate and clear information of licensing of
            the embedded images and all they contain.
        2.  To be able to comply easily with licenses for the embedded
            image and all it contains.
        3.  To be able to trust that the embedded images SPDX data is in
            alignment with the upstream maintainers license assertions
            of the pieces it contains.
5.  **Preconditions:**
    1.  Embedded Image Creator understands the things it contains,
        including any SPDX data if provided.
6.  **Main Success Senario:** Embedded Image Creator communicates
    accurate complete licensing information for their package in an SPDX
    data format for the Embedded Image and all it contains.
7.  **Failed End Condition:** Embedded Image Creator communicates
    inaccurate incomplete licensing information for their embedded
    image.
8.  **Trigger:**
    1.  Release of a new embedded image.
9.  **Notes:**

[Category:Technical](Category:Technical "wikilink")
