## Fedora good license comparison

In order to expand the SPDX License List, align with influential
existing open source projects, and further enable use of SPDX
identifiers - the SPDX Legal team went through the Fedora "good license"
list to look for licenses there that were not already on the SPDX
License List with the goal of adding as many of those licenses as seemed
reasonable. Many licenses were added to v1.20 of the SPDX License List
as a result. Licenses from Fedora that were not added were often for
reasons such as: license was very old and no one had seen it in use
recently, unable to find precise license text, already represented by a
license that could be templated (such as many BSD licenses), etc. If a
license is not on the SPDX License List, but one wants to identify it in
the scope of an SPDX document, then section 5 of the SPDX specification
describes a way to create a LicenseRef for such licenses.

A general description and timeline of that work is as follows:

  - Aug 2013: the Fedora good licenses list was taken from this web
    page:
    <https://fedoraproject.org/wiki/Licensing:Main?rd=Licensing#Good_Licenses>
    and a comparison as to what licenses listed there were already on
    the SPDX License List v. not on the SPDX License List
  - The Fedora/SPDX license work proceeded over the course of the next
    year. This began with an initial pass and recommendation for adding
    licenses by one volunteer and then review by the whole SPDX Legal
    team on the bi-weekly calls. This included identifying licenses that
    were on both lists, but used different names or identifiers,
    licenses that Fedora grouped by using the same identifier whereas
    SPDX License List used different identifiers, and other such info.
    Coordination with members of the Fedora team on questions and input
    on certain licenses was obtained, especially where discrepancies as
    to the precise license text or broken links were found, etc.
  - Aug 2014: As a result of this work, v1.20 of the SPDX License List
    added 73 licenses from the Fedora good licenses list. This was by
    far the largest addition of licenses to the SPDX License List in one
    release.
  - July 2015: Due to some interest on the Fedora legal mailing list in
    using the SPDX license identifiers, the SPDX Legal team posted the
    comparison of what licenses were on the SPDX License List (including
    updating to the then current release of v2.1) and the Fedora list in
    both directions. In this update, some of the licenses that had been
    added to the Fedora list since the initial pass were added here (but
    not sure if we caught all). This work was posted on a public Google
    doc:
    <https://docs.google.com/spreadsheets/d/1LUJuzGKC5K2yYuAg8S-2VYbS2dmg_4IlFdpqj7n9Ghg/edit#gid=138634715>
    and the link was posted on the Fedora legal mailing list
  - Aug 2016: Licenses added to the SPDX License List since v2.1 were
    added to the bottom of the first worksheet, with a note as such. It
    has not been updated since v2.1 of the SPDX License List
