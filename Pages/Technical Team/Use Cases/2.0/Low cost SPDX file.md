As a maintainer of an open source project in order to make complying
with my licensing easier i want to publish the licensing in a machine
readable format but i am not willing to "waste" much effort on such
administrivia. Maintaining data for each and every file in every package
ever produced sounds like a lot of work because those files change a
lot. An SPDX file that describes the package but omits all the file
level information sounds just about right.

**NOTE:** Potential conflict between this Use Case and
[Technical\_Team/Use\_Cases/2.0/Check\_to\_see\_if\_the\_SPDX\_data\_provided\_matches\_the\_files\_provided\_and\_is\_trustworthy\_and\_most\_current\_for\_package](Technical_Team/Use_Cases/2.0/Check_to_see_if_the_SPDX_data_provided_matches_the_files_provided_and_is_trustworthy_and_most_current_for_package "wikilink")
(if SPDX Lite doesn't involve any checksumming...)

'''Note 2: '''Still uncertain if the Use Case is about "package" or
"project" (and the definition of package vs. project in th context of
this Use Case). Hence " copyrightable artifact"

## Stakeholders and interests

  - **Project maintainer**Wants to produce machine readable licensing
    information so that users can more easily adopt the package but does
    not want to "waste" valuable time creating that data rather than
    implementing features.
  - **Lax SPDX consumer**A person or organization that uses SPDX data to
    accomplish goals that do not require exhaustive file by file data.
  - **Strict SPDX consumer**A person or organization that uses SPDX data
    to accomplish goals that require exhaustive data on every file.

## Main scenario

1.  Project maintainer hears about SPDX and decides to implement it for
    his project.
2.  Project maintainer creates SPDX file that describes his package
    (e.g. name, description, licenseDeclared, licenseConcluded, checksum
    (optional??), etc) but does not included information about the files
    in package and does not generate packageVerificationCode.
3.  Project maintainer publishes limited SPDX data for the copyrightable
    artifact
4.  Lax SPDX consumer downloads copyrightable artifact and its SPDX
    data.
5.  Lax SPDX consumer uses the package level licensing information to
    ensure they are in compliance with the licensing of the package.

## Alternate scenario A

1.  Project maintainer hears about SPDX and decides to implement it for
    his project.
2.  Project maintainer creates SPDX file that describes his package
    (name, description, licenseDeclared, licenseConcluded, checksum,
    etc) but does not included information about the files in package
    and does not generate packageVerificationCode.
3.  Project maintainer publishes limited SPDX data for the copyrightable
    artifact
4.  Strict SPDX consumer downloads copyrightable artifact and its SPDX
    file.
5.  Strict SPDX consumer reads the SPDX file and notes its
    incompleteness.
6.  Strict SPDX consumer initiates procedures to do a deeper analysis on
    the package so that its goals can be accomplished.

## Success Scenario

1.  Wider adoption of SPDX by project maintainers providing licensing
    information in a standard (albeit non-exhaustive) format
2.  Consumers obtain licensing intentions of project maintainers in a
    standard (albeit non-exhaustive) format
3.  Consumers are able to contribute / build upon the initial low cost
    SPDX data to flesh it out

[Category:Technical](Category:Technical "wikilink")
