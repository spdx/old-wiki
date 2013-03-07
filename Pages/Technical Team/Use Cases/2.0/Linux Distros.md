1.  **Title:**Linux Distribution (e.g. Fedora, Ubuntu)
2.  **Primary Actor:** Image Creator
3.  **Goal in Context:** To allow an Image Creator to communicate the
    SPDX data for all of the copyrightable artifacts (packages, files,
    library components, etc) in the distributable image.
4.  **Stakeholders and Interests:**
    1.  ''' Image Creator: '''
        1.  To communicate the licensing information for their
            copyrightable artifact (the image) including all
            copyrightable artifacts it contains.
        2.  To not build images with packages whose lienses aren't
            compatible.
        3.  Be able to add compatible fixes to packages during release
            life cycle.
    2.  **Consumers of Images:**
        1.  To receive accurate and clear information of licensing of
            the images and all they contain.
        2.  To be able to comply easily with licenses for the image and
            all it contains.
        3.  To be able to trust that the images SPDX data is in
            alignment with the upstream maintainers license assertions
            of the pieces it contains.
5.  **Preconditions:**
    1.  Image Creator understands the things it contains, including any
        SPDX data if provided.
6.  **Main Success Senario:** Image Creator communicates accurate
    complete licensing information automatically, as part of every image
    build for the packages in an image in an SPDX data format, each and
    every time the image is built.
7.  **Failed End Condition:** Image Creator communicates inaccurate
    incomplete licensing information for their embedded image.
8.  **Trigger:**
    1.  Release of a new image. (daily, milestone, final release, stable
        release updates)
9.  **Notes:**

[Category:Technical](Category:Technical "wikilink")
