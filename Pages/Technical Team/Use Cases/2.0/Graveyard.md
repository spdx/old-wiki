We had several sources to begin pulling for SPDX Use Cases:

1.  The Pad from earlier conversations collected at [Use Cases For SPDX
    2.0
    Discussion](Technical_Team/Old/Use_Cases_Collected_during_1.x_timeframe "wikilink")
2.  The old [SPDX 1.0 Use
    Cases](Technical_Team/Old/Sandbox_for_Sharing_Examples/SPDX_Use_Case_1 "wikilink")
    as well as the [SDPX 1.0 Use Case
    Picture](:File:ecosystem.jpg "wikilink").
3.  Soliciting use cases in 2012 (especially at Linux Collab Summit in
    April)

**NOTE**: On May 29, 2012, we removed use cases which were not yet
fleshed out. A snapshot of 'all' the use cases was saved in child page
SPDX 2.0 Use Cases Graveyard. The process followed was to flesh out use
cases here by having a brief summary listed here as a link to a more
detailed child page. Note, these use cases should be \***doable**\* but
in general not \***required**\*. Any item listed here that is not a
link, should have a child page created for it.

1.  Code commits (original work intended for the project)
    1.  [Committer provides SPDX
        data](Technical_Team/Use_Cases/2.0/Committers_provides_SPDX_data_for_a_code_being_committed "wikilink")
    2.  [Contributor makes commit subject to existing SPDX data of
        project](Technical_Team/Use_Cases/2.0/Contributor_makes_commit_subject_to_existing_SPDX_data_of_project "wikilink")
    3.  Contributor makes commit subject to existing SPDX data of a dual
        licensed project and selects one license
2.  [Committer annotates source files with SPDX
    data](Technical_Team/Use_Cases/2.0/Committer_annotates_source_files_with_SPDX_data "wikilink")
3.  Patches (original work intended for the project)
    1.  [Patch provider provides SPDX data for the
        patch](Technical_Team/Use_Cases/2.0/Patch_provider_provides_SPDX_data_for_the_patch "wikilink")
    2.  [Patch provider provides SPDX data for the patch indicating it
        is licensed however the hell its
        applied](Technical_Team/Use_Cases/2.0/Patch_provider_provides_SPDX_data_for_the_patch_indicating_it_is_licensed_however_the_hell_its_applied "wikilink")
    3.  [Patch provider provides patch subject to existing SPDX data of
        project](Technical_Team/Use_Cases/2.0/Patch_provider_provides_patch_subject_to_existing_SPDX_data_of_project "wikilink")
4.  Patch provider provides a patch that modifies existing SPDX data of
    project
    1.  [Downstream consumers contributing patches to provide SPDX data
        to an upstream that doesn't have
        it.](Technical_Team/Use_Cases/2.0/Downstream_consumers_contributing_patches_to_provide_SPDX_data_to_an_upstream_that_doesnt_have_it "wikilink")
    2.  [Downstream consumers contributing patches to provide
        corrections to SPDX data for an upstream that does have
        it.](Technical_Team/Use_Cases/2.0/Downstream_consumers_contributing_patches_to_provide_corrections_to_SPDX_data_for_an_upstream_that_does_have_it "wikilink")
5.  [Upstream maintainer providing SPDX
    data](Technical_Team/Use_Cases/2.0/Upstream_maintainer_providing_SPDX_data "wikilink")
    1.  [Upstream maintainer providing SPDX data in source
        archive](Technical_Team/Use_Cases/2.0/Upstream_maintainer_providing_SPDX_data_in_source_archive "wikilink")
    2.  [Upstream maintainer providing SPDX data in
        SCM](Technical_Team/Use_Cases/2.0/Upstream_maintainer_providing_SPDX_data_in_SCM "wikilink")
    3.  [Upstream maintainer providing SPDX data at a
        URL](Technical_Team/Use_Cases/2.0/Upstream_maintainer_providing_SPDX_data_at_a_URL "wikilink")
    4.  [Upstream maintainer preparing release artifacts (including SPDX
        data).](Technical_Team/Use_Cases/2.0/Downstream_consumers_contributing_patches_to_provide_SPDX_data_to_an_upstream_that_doesnt_have_it "wikilink")
    5.  Intended usage communicated by the auditee (how/will the audited
        item get included in delivered/deployed bits) \[Bill
        Schineller\]\]
6.  Project maintainer incorporates another project
    1.  [Project maintainer incorporates another project by including
        source](Technical_Team/Use_Cases/2.0/Project_maintainer_incorporates_another_project_by_including_source "wikilink")
    2.  [Project maintainer incorporates another project by including
        binary](Technical_Team/Use_Cases/2.0/Project_maintainer_incorporates_another_project_by_including_binary "wikilink")
    3.  [Project maintainer pulling individual files out of another
        project
        (subsetting)](Technical_Team/Use_Cases/2.0/Project_maintainer_pulling_individual_files_out_of_another_project_\(subsetting\) "wikilink")
7.  Project maintainer incorporates another copyrightable artifact by
    reference (think maven, possibly linking cases)
    1.  by static reference (the referenced library is included with a
        redistribution)
    2.  by dynamic reference (express runtime dependency on the external
        library, but not redistributing it)
    3.  Maven case
8.  SPDX-Lite:
    1.  [Allow a low investment SPDX producer to produce valid SPDX
        data](Technical_Team/Use_Cases/2.0/Low_cost_SPDX_file "wikilink")
    2.  [Produce a valid SPDX dataset even if some data is
        missing](Technical_Team/Use_Cases/2.0/Producing_valid_SPDX_files_in_the_face_of_missing_data "wikilink")
9.  Intermediate packager (rpm, deb, etc) passing on and adding to SPDX
    Data
    1.  Intermediate packager builds source package from upstream source
        1.  [Intermediate packager builds source package from upstream
            source that provides SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_builds_source_package_from_upstream_source_that_provides_SPDX_data "wikilink")
        2.  [Intermediate packager builds source package from upstream
            source that does not provide SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_builds_source_package_from_upstream_source_that_does_not_provide_SPDX_data "wikilink")
    2.  Intermediate packager builds binary package from upstream source
        1.  [Intermediate packager builds binary package from upstream
            source that provides SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_builds_binary_package_from_upstream_source_that_provides_SPDX_data "wikilink")
        2.  [Intermediate packager builds binary package from upstream
            source that does not provides SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_builds_binary_package_from_upstream_source_that_does_not_provides_SPDX_data "wikilink")
    3.  Intermediate packager adds patches to upstream source
        1.  [Intermediate packager adds patches to upstream source that
            provides SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_adds_patches_to_upstream_source_that_provides_SPDX_data "wikilink")
        2.  [Intermediate packager adds patches to upstream source that
            does not provide SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_adds_patches_to_upstream_source_that_does_not_provide_SPDX_data "wikilink")
    4.  Intermediate packager adds someone else's patches to upstream
        source
        1.  [Intermediate packager adds someone else's patches to
            upstream source that provides SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_adds_someone_elses_patches_to_upstream_source_that_provides_SPDX_data "wikilink")
        2.  [Intermediate packager adds someone else's patches to
            upstream source that does not provide SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_adds_someone_elses_patches_to_upstream_source_that_does_not_provide_SPDX_data "wikilink")
    5.  Intermediate packager subsetting upstream source
        1.  [Intermediate packager subsetting upstream source that
            provides SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_subsetting_upstream_source_that_provides_SPDX_data "wikilink")
        2.  [Intermediate packager subsetting upstream source that does
            not provide SPDX
            data](Technical_Team/Use_Cases/2.0/Intermediate_packager_subsetting_upstream_source_that_does_not_provide_SPDX_data "wikilink")
    6.  Intermediate packager chooses to distribute one of multiple
        available under licenses provided for by upstream (check with
        legal team)
    7.  Intermediate packager reviews SPDX data provided by upstream.
10. Build systems (build systems want to pass on SPDX data for the thing
    they are building)
    1.  [Yocto](Technical_Team/Use_Cases/2.0/Build_System_Yocto "wikilink")
        1.  How does SPDX work in an environment where the sources
            aren't there, but are pulled from git or a mirror and
            patched.
    2.  Maven \[Brian Fox\]
        1.  Rolling into release artifacts things only referenced in the
            POM file
        2.  Shading (subsetting) portions of a transitive dependency for
            inclusion in your artifact
    3.  Continuous integration around SPDX files (fixing SPDX files for
        commits coming in etc).
    4.  Linking
        1.  [Debian has an interest in only building things that are
            linking license
            compatible](Technical_Team/Use_Cases/2.0/Debian_has_an_interest_in_only_building_things_that_are_linking_license_compatible "wikilink")
            1.  If a tool is consuming SPDX data to interact with
                heuristics.
    5.  Java complications \[Richard Fontana\]\]
        1.  What to do about installers that download JDK directly from
            sun.
    6.  I just made a binary out of some source
        1.  [SPDX data indicating subset of the source that made it into
            a particular binary or binary
            package](Technical_Team/Use_Cases/2.0/SPDX_data_indicating_subset_of_the_source_that_made_it_into_a_particular_binary_or_binary_package "wikilink")
    7.  Tool used to produce software infecting distribution license of
        the software itself \[Kevin Fleming\] (e.g. code-generator?
        Bison? ..)
11. Aggregator aggregating many 'copyrightable items' for redistribution
    1.  [Linux
        Distros](Technical_Team/Use_Cases/2.0/Linux_Distros "wikilink")
    2.  [Embedded Images (e.g. router images, switch
        images)](Technical_Team/Use_Cases/2.0/Embedded_Images_\(e.g._router_images,_switch_images\) "wikilink")
    3.  SDKs \[Jack Manbeck\]
    4.  \[\[Technical\_Team/Use\_Cases/2.0/Reference\_Implementations|Reference
        implementations\] \[Jack Manbeck\]
    5.  Eclipse/OSGI distributions
    6.  [Application which ships with documentation + media +
        software](Technical_Team/Use_Cases/2.0/Application_which_ships_with_documentation_and_media_and_software "wikilink")
        \[Jack Manbeck\]
    7.  [Application which ships with a contrib
        libraries](Technical_Team/Use_Cases/2.0/Application_which_ships_with_a_contrib_libraries "wikilink")
    8.  [Application which ships with development
        tools](Technical_Team/Use_Cases/2.0/Application_which_ships_with_development_tools "wikilink")
    9.  Receiving what appears to be commercial software but that
        commercial software contains Open Source
    10. Receiving what appears to be opensource software but that
        opensource software contains commercial software
    11. [Subsetting out only the shippable bits of stuff coming from an
        SDK](Technical_Team/Use_Cases/2.0/Subsetting_out_only_the_shippable_bits_of_stuff_coming_from_an_SDK "wikilink")
    12. [Aggregators aggregating other aggregations for
        redistribution](Technical_Team/Use_Cases/2.0/Aggregators_aggregating_other_aggregations_for_redistribution "wikilink")
12. Consumers receiving SPDX data
    1.  Procurement needs to view it and review it
    2.  Legal department needs to review
    3.  Comply with licensing when there are multiple rights holders
        each with licensing use under a different license
    4.  [Provide sufficient data to allow consumer to comply with
        licenses on
        redistribution](Technical_Team/Use_Cases/2.0/Provide_sufficient_data_to_allow_consumer_to_comply_with_licenses_on_redistribution "wikilink")
    5.  Bradley want to extract all rights holders for a particular file
    6.  Multiple SPDX files you need to reconcile
    7.  Recognizing the same SPDX data for the same code coming from
        multiple supply chain paths
    8.  Flagging potential issues revealed by the SPDX
        1.  License conflicts
        2.  Listing out obligations
    9.  Helping to meet the obligations of the licenses (Given that I
        receive an SPDX file, does the info in SPDX file allow me to
        extract what I need to meet basic kinds of obligations)
        1.  How to capture attribution information for binaries
        2.  Help with redistribution obligations
    10. Equivalence classes of binaries and tracking back to the same
        source and source SPDX data.
        1.  Consider what to do about license metafiles
        2.  COPYING files
        3.  LICENSE.\* files
        4.  README.\*
        5.  Think about how to handle NOTICE files and Apache
13. [Consuming code
    snippets](Technical_Team/Use_Cases/2.0/Consuming_code_snippets "wikilink")
    (God help us all) (subfile pieces of code not originally intended
    for the project)
    1.  Make sure that the license and copyright information for a
        snippet is reflected in the SPDX data for the file
    2.  Track differently licensed snippets explicitly
    3.  Handle the case where code is copied and pasted through online
        forums etc.
14. Signoff/multiple signoff on SPDX data
    1.  [Contracts with multiple parties requiring signoff by
        all](Technical_Team/Use_Cases/2.0/Contracts_with_multiple_parties_requiring_signoff_by_all "wikilink")
        \[Kate Stewart\]
    2.  Signing off on only a subset of the SPDX data (of an SPDX
        document in progress?)
15. Third party does licensing analysis
    1.  [Third party generates license
        analysis](Technical_Team/Use_Cases/2.0/Third_party_produces_bill_of_materials_for_software_package "wikilink")
    2.  Actual usage communicated
    3.  Did the code that I shipped (the binaries) match the
        copyrightable items? i.e. be able to produce an SPDX file that
        applies to binary code
    4.  [Collecting enough information to allow auditor to make
        recommendations to remove or not a
        component](Technical_Team/Use_Cases/2.0/Collecting_enough_information_to_allow_auditor_to_make_recommendations_to_remove_or_not_a_component "wikilink")
    5.  Tooling to assist with copyright (change copyright date and list
        of contributors/copyright holders, even as license and most of
        code remains unchanged) for changes between versions
    6.  Unaffiliated third party provides SPDX data for a project
16. Auditor Analyzing/Sanity-checking/correcting Bill of Material he's
    handed
    1.  [Backtrack from compiled/binary file to constituent
        files](Technical_Team/Use_Cases/2.0/Backtrack_from_binary_to_source_files "wikilink")
    2.  outbound: validate that SPDX goes hand in hand with what's being
        shipped \[Kirsten Newcomer\]
        1.  [Check to see if the SPDX data provided matches the files
            provided](Technical_Team/Use_Cases/2.0/Check_to_see_if_the_SPDX_data_provided_matches_the_files_provided_and_is_trustworthy_and_most_current_for_package "wikilink")
        2.  Check to see if the SPDX file is internally consistent (do I
            have a license refs to match licenses)
        3.  Did the code that I shipped (the binaries) match the
            copyrightable items.
    3.  inbound: validate that SPDX goes hand in hand with what's being
        brought in \[Kirsten Newcomer\]
        1.  Chcek to see if the SPDX data matches the files you are
            shipping \[Kirsten Newcomer\]
        2.  Check to see if the SPDX file is internally consistent (do I
            have a license refs to match licenses)
    4.  SPDX lint
    5.  Incomplete SPDX data you may need to complete
    6.  Asserting corrections to SPDX data provided by others further
        upstream
17. Migrating from one version of the SPDX spec to another (moving a
    file from SPDX 1.0 to 2.0 for example)
    1.  e.g. knit together a bunch of 1.0 files into a 2.0...
18. Extensions:
    1.  [Communicate data beyond what is described in spec between
        consenting parties w/o breaking consumers that are not in the
        know](Technical_Team/Use_Cases/2.0/Communicate_data_beyond_what_is_described_in_spec "wikilink")
    2.  Experimental improvements to SDPX files w/o breaking consumers
        that are not in the know. \[Peter Williams\]
    3.  [License list extensions, how do you handle folks who have more
        licenses than
        SPDX](Technical_Team/Use_Cases/2.0/License_list_extension "wikilink")
    4.  [Decorating an already produces and signed SPDX dataset with
        extension
        data](Technical_Team/Use_Cases/2.0/Decorating_an_already_produces_and_signed_SPDX_dataset_with_extension_data "wikilink")
        \[Bill Schineller\]
    5.  Recording per ExtractedLicenseText a comment detailing exactly
        which pattern matching technique / string found that Extracted
        License Text (so that SPDX file doesn't need to repeat in every
        matched File instance) \[D. M. German\]
    6.  Recording free-form tribal knowledge about a file which is not
        otherwise visible in the text of the file itself (e.g. commit
        history from git repo, origin information such as scanning
        against a knowledge base of open source could provide) \[Mark
        Gisi\]
    7.  Conveying Encryption content (Export Control implications) of a
        package/file in a package \[someone at collab summit\]
    8.  Conveying Security Vulnerability information \[Jianshen O.-
        Huawei\]
19. Look at a 'pingback' (URL string similar for blogs)kind of mechanism
    for original providers of SPDX (to allow them to figure out where
    it's used) \[Andrew Hsu\]
20. Cloud
    1.  Materializing a VM and making sure it's OK from a licensing
        mechanism
    2.  SugarCRM case, obligation by virtue of using web service
        interface
21. Legal Use Cases:
    1.  Allow the NDA status of an SPDX document to be communicated in a
        machine readable way (not just a comment) for organizations that
        don't want the SPDX document to be publicly released \[Mark
        Baushke from Juniper\]
    2.  How are we going to handle Public Domain (not in license list...
        region specific...)

## Cross-cutting concerns

1.  Provenance (the need to optionally use signing to validate who said
    what)
2.  Trust
3.  Handling staleness of data
4.  Composite licensing
5.  Ease of sharing information
    1.  Collecting tribal knowledge along the way
6.  Guarding against file bloat
7.  Simple simple simple
8.  SPDX-Lite:
9.  Clarity
10. Automation/toolifiability
11. Regionality

## Themes:

Looking at these Use Cases, there are some underlying themes:

1.  Root of data (closer to upstream the better)
2.  Subsetting of copyrightable things (and their SPDX data) (**Note**:
    Subsets of copyrightable things are usually also copyrightable
    things)
3.  Aggregation of copyrightable things (and their SPDX data) (**Note**:
    Aggregations of copyrightable things are usually also copyrightable
    things).

[Category:Technical](Category:Technical "wikilink")
[Category:Archived](Category:Archived "wikilink")
