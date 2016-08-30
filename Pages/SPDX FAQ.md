## General

  - What is the SPDX Specification?
      - The SPDX Specification enables suppliers and consumers of
        software that contains open source code to provide a "bill of
        materials" that describes the open source licenses and
        components that are included. The specification defines a common
        file format to communicate this information.
  - Who do you expect to use the SPDX Specification?
      - The specification is designed for use by participants in the
        software supply chain. Some potential use cases for the spec:
          - Developers of open source projects could provide an SPDX
            file to users of that project
          - Linux distros could require upstream projects that are
            included in the distro to provide an SPDX file
          - Developers of software that includes a Linux distro or open
            source project could provide an SPDX file to their users or
            customers
          - In the mobile industry, chipset providers, mobile providers
            and carriers could exchange SPDX files as software moves
            through the supply chain
  - Am I required to use the SPDX specification?
      - The SPDX organization does not and can not make it a requirement
        for anyone to use the SPDX specification. However, we do
        encourage the use of SPDX as a way to streamline the processes
        needed to analyze software for open source licenses. However,
        there may be companies or organizations that DO require use of
        the SPDX specification and the creation of SPDX files as part of
        contracts with their supply chain partners. For example, a
        mobile handset vendor might require, as part of a contract, that
        it's supplier provide an SPDX file along with any software.
  - Who created the SPDX spec?
      - The specification is being created by a working group of the
        Linux Foundation. Its members represent a wide spectrum of open
        source creators and consumers, including open source
        communities, Linux distros, mobile supply chain companies,
        software companies, makers of open source scanning tools and
        service providers. The process is an open process, run much like
        an open source community, and the group is open for anyone that
        wants to participate. Membership in the Linux Foundation is not
        required to participate.''' '''

## Using the SPDX Spec

  - Is an SPDX file associated with a particular piece of software?
      - Yes. An SPDX file is associated with a specific version of a
        software package. A package may consist of one or more files.
        When any changes are made to a particular version of software,
        the corresponding SPDX file will also need to be updated to
        reflect those changes.
  - What information is included in an SPDX file?
      - We refer you to the SPDX specification for specific details, but
        at a high level, a SPDX file represents components, licenses and
        copyrights associated with a particular version of a software
        package. For example, it includes license information (if any)
        associated with each file found within the package. It may also
        include information about what open source project or component
        the file originated from.
  - Is SPDX for open source packages only or can I use it with software
    that is a mix of both open source and proprietary?
      - SPDX files can be created for any software component that
        consists of one or more files. The software component is
        typically represented as a single archive file (e.g .tar, .gz,
        .bz2, .zip, … ).
  - How do I know if the information included in the SPDX file is
    accurate?
      - There are several ways to assess the level of trust in an SPDX
        file.
          - Each SPDX file includes a history of who created and
            reviewed the information -- similar to what you would see
            for authors of open source code. By reviewing that
            information, you can make your own assessment of the level
            of trust you place in the creators.
          - In cases where you receive the SPDX file from a supply chain
            partner, you may also have separate contractual arrangements
            whereby a supplier vouches for or guarantees the accuracy of
            the SPDX file.
          - You may choose to use software tools that can scan software
            and validate the accuracy of the SPDX file.
  - How does one handle non open source licenses or licenses not found
    in the SPDX approved license list?
      - When a license identified in the software package is not found
        in the list of approved SPDX licenses, one can add the license
        text to the SPDX file and define a new license label. That
        license label is defined only for that specific SPDX file.
  - How does SPDX work with binaries?
      - Binary files represent just another file type. License
        information (if known) should be assigned to each file
        regardless of its file type (e.g., binary, source, script …).
  - How does one represent a file or package that is dual licensed
    (i.e., a license choice)?
      - SPDX license information can be represented using conjunctive or
        disjunctive regular expressions. For example, a file that is
        dual licensed under either the GPL-2.0 or MIT would be
        represented using the following disjunctive expression: (GPL-2.0
        or MIT).
  - How does one represent a file that is licensed under two or more
    licenses?
      - SPDX license information can be represented using conjunctive or
        disjunctive regular expressions. For example, a file that is
        subject to the Apache-2.0, MIT and GPL-2.0 would be represented
        using the following conjunctive expression: (Apache-2.0 and MIT
        and GPL-2.0).
  - The Creator field is mandatory. If my organization does not permit
    me or my organization to be listed in the Creator field, is the SPDX
    file non-compliant?
      - Although including a value for this field is mandatory, one can
        always choose the value: ANONYMOUS as described in section 3 of
        the specification. Use of the ANONYMOUS value would be compliant
        with the SPDX specification.
  - What license is the SPDX specification document available under?
      - The SPDX specification document is available under the Creative
        Commons Attribution 3.0 Unported License. A copy of the license
        can be found in the appendix of the specification.
  - What license is the SPDX file data under?
      - The first version of the specification requires the SPDX file
        data to be placed under the Open Data Commons Public Domain
        Dedication and License 1.0 (“PDDL-1.0”). There are plans to
        revisit this requirement in future revisions of the
        specification. See section 2 of the specification for more
        details.
  - Can I share a collection of SPDX files I created with another party
    under confidential terms?
      - The specification states that although it requires the SPDX data
        to be available under the Open Data Commons Public Domain
        Dedication and License 1.0 (“PDDL-1.0”), it does not prohibit
        one from entering into a confidentially agreement with another
        party where the agreement restricts sharing of the SPDX data.
        See section 2 of the specification for more details.
  - Why are there two different license fields for a package (Concluded
    License and Declared License)?
      - The Concluded License field is the license the SPDX file creator
        believes governs the package. The Declared License is what the
        authors of a project believe govern the package. Often these
        fields have the same value. When they are different the SPDX
        file creator should provide background information in the
        Comments on License field.
  - Why does the specification include examples for both Name/Value tag
    and RDF/XML formats?
      - Name/Value tag and RDF/XML formats are two very popular data
        syntax representations used within the open source community.
        The SPDX file creator can choose to represent the SPDX data
        using either format and therefore examples are provided for
        both.
  - Why are there two package identifier fields Package Checksum and
    Package Verification?
      - Although the values of the two fields Package Checksum and
        Package Verification are similar, they each serve a different
        purpose. The Package Checksum provides a unique identifier of a
        software package which is computed by taking the SHA1 of the
        entire software package file. This enables one to quickly
        determine if two different copies of a package are the same. One
        disadvantage of this approach is that one cannot add an SPDX
        data file into the original package without changing the Package
        Checksum value. Alternatively, the Package Verification field
        enables the inclusion of an SPDX file. It enables one to quickly
        verify if one or more of the original package files has changed.
        The Package Verification field is a unique identifier that is
        based on SHAing only the original package files (e.g., excluding
        the SPDX file). This allows one to add an SPDX file to the
        original package without changing this unique identifier.
  - Can I use the SPDX trademark?
      - Yes. The terms and condition can be found here:
        <http://www.spdx.org/trademark>.
  - Is there a designated file extension for SPDX files?
      - The SPDX specification does not specify which file extension a
        SDPX file should have. A common practice is to append the SPDX
        file with the extension .spdx.
  - Should the version number be included as part of the name in the
    package name field?
      - The specification does not specify whether the version number
        should or should not be included in the package name field.
        Since there is a designated field for the version number, it is
        a common practice not to include the version number in the
        package name field.

<!-- end list -->

  - Should I use the CONTAINS and CONTAINED\_BY relationships for files
    inside a package?
      - No. When a file is inside a package, this in itself implies a
        containment relationship. Furthermore, creating such superfluous
        relationships, especially reciprocal relationships, for large
        numbers of files can introduce performance issues with SPDX
        Tools and, possibly, other utilities.

## Licenses (i.e. the SPDX License List)

  - What is the SPDX License List?
      - The SPDX License List is a list of well known, commonly-used,
        and Open Source Initiative (OSI) approved open source software
        licenses. The list includes the following fields for each
        license:
          - The full name of the license
          - A short identifier for use in an SPDX file
          - A url for where the original license can be found
          - Any relevant notes about the license, (such as if its been
            since deprecated or its relationship to other license)
          - The license text itself
  - Why does it exist?
      - The purpose of the SPDX License List is to provide short
        identifiers for popular and common licenses. The full license
        text associated with each license on the SPDX License list will
        have a unique, permanent URL on the SPDX.org website. Being able
        to refer to licenses via the short form identifier lessens the
        SPDX file size and allows for unambiguous license
        identification.
  - How do I identify licenses not on the SPDX License List?
      - The SPDX specification includes a way to identify and include
        open source licenses that are not on the SPDX License List. In
        this case, a short form identifier for the license is created
        and the full text of the license included in the SPDX file.
  - Why are some licenses I've heard of included on the list and some
    not?
      - The primary purpose of the list is to provide a short form
        identifier for common or popular open source software licenses.
        To create this list, the SPDX legal work group included all the
        OSI approved licenses and any other license members of the work
        group had experience with "in the wild." All versions (even if
        since deprecated) of these licenses were also included. It was
        always contemplated that the list would grow over time, so the
        initial goal was to provide a sensible starting point such that
        the most commonly found licenses would have a short identifier.
  - How to request adding a license to SPDX License List?
  - What if I find a license or license variation that is not on the
    SPDX License List - how do I identify that license?

## Tools

  - Are there tools available that can help me create, validate or read
    an SPDX file?
      - The SPDX Group has developed some open source tools to assist
        with creation, viewing and validation of SPDX documents. The
        tools are intended to:
          - Reduce the effort of creating, consuming and validating SPDX
            Documents
          - Provide a translation from the technical document (e.g.
            RDF/XML or tag-value format) to a more readable format
          - Provide a mechanism for validating SPDX documents
          - Enable contributions and review of the tool implementation
            by the broader technical community through open source
            licensing
      - In addition, we expect that additional open source and
        proprietary tools will be created to help with these tasks.
      - See the [Tools page](http://spdx.org/tools) for more information
        and to download documentation.
