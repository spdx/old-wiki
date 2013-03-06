## Introduction

The following use case is presented to help evaluate the SPDX Proposal,
DRAFT 20100308. It presents a typical ecosystem, discusses the flow of a
facts file within it and the offers some observations. In a future
revision, it will be expanded to map the files and other information to
the specific fields in a Package Facts File.

## Background

In this use case there are six entities each of which plays a different
role. The project, names and names of individuals are fictional but
based on a real open source project and ecosystem.

## Library A Project

  - An individual has created some software he feels is useful to others
    and decides to license it under an Open Source license. He does that
    and places it on a web site for download.
  - This is a small library and consists of only a handful of source
    files including other files such as Makefiles, documentation and
    test data that support building and testing of the library.
  - Being a simple project, it does not require much maintenance and
    therefore is updated infrequently.

## The Project

  - The Project is an active community and offers a set of Libraries
    (for implementing a protocol) that can be integrated by someone into
    their application. They needed some software and found that Library
    A did exactly what they wanted.
  - They have incorporated Library A and their community has developed
    Library B and a Tool which tests both the libraries. The Library B
    and Tool consist of more than a handful of files including other non
    source files which support the project like Makefiles,
    documentation, scripts, test data, and so forth.

## Company A

  - Company A consumes Packages from The Project and has included them
    with software it has developed as part of a larger offering.
  - Company A has made changes to the source from The Project.

## Company B

  - This Company is using what Company A provides to make their own
    product and adds their own software to it.
  - Company B has made some changes to the source from Company A.

## Consumer

  - The Consumer is receiving a product from Company B.

## Independent Auditor

  - The Independent Auditor is performing an analysis of The Project for
    Company A and Company B.
  - The Independent Auditor could also have collected the original
    Package Facts from Library A and The Project in the process of doing
    the audits.

\[*Editorial Note: This Independent Auditor could be a different
organization for Company A and B. Also, it is fair to say that this
could be two entities? One is an auditing firm and the other a tools
vendor. I have combined the two but it can be broken out.*)

## Use Case Ecosystem

`   Library A Project -> The Project  -> Company A -> Company B-> Consumer`  
`   `  
`   Library A            Library A       Library A’   Library A’`  
`   `  
`                         Library B       Library B’   Library B’’`  
`   `  
`                          Tool           Tool`  
`   `  
`    |                     |              ^            ^`  
`   `  
`    |                     |              |            |`  
`   `  
`    ------------------------------------------------------------`  
`   `  
`                                  |`  
`   `  
`                             Independent Auditor`

*Flow of the Package Fact Files in the Ecosystem*

## Library A Project

  - Library A creates a package facts file that is downloaded as part of
    the release.
  - Library A is small so the individual maintaining it hand creates the
    Package Facts before every release.

The files which make up Library A are described in the table below.

|               |                           |                                                      |                 |
| ------------- | ------------------------- | ---------------------------------------------------- | --------------- |
| **File**      | **Copyright in the file** | **License Text in the file**                         | **Exception**   |
| a1.c          | Josh Brown                | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| a2.c          | Josh Brown                | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| a3.c          | Josh Brown                | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| a4.c          | Josh Brown                | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| Makefile      | None specified            | None specified                                       | None specified  |
| testdata.txt  | None specified            | None specified                                       | None specified  |
| readme        | None specified            | None specified                                       | None specified  |
| Package Facts | Josh Brown                | None specified                                       | None specified  |

Exception 1 – This is part of each BSD license header and reads “The
license and distribution terms for any publically available version or
derivative of this code cannot be changed. i.e. this code cannot simply
be copied and put under another distribution license including the GNU
Public License.”

## The Project

  - The Project has three separate Package Facts files: one for the
    tool, one for Library A and one for Library B.
  - This allows for distribution of the Facts file for each piece
    (package) or in the case of the full download each piece would have
    its own.
  - The Project has not modified Library A and is happy to pass along
    Library A’s Package Fact and they do so.
  - The Project creates their own Facts file for Library B and the Tool.
  - The Project likes to automate things so they have put keywords in
    their source and can use these to generate the Facts file.

(*Editorial note: okay we can question why they did not automate the
generation of the facts from Library A but it’s more interesting that
they did not and there are likely many scenarios where facts will be
re-used*).

Library B and the Tool contain the following source files.

Library B Source Files (sampling for illustrative purposes)

|               |                                                                    |                                                    |                |
| ------------- | ------------------------------------------------------------------ | -------------------------------------------------- | -------------- |
| **File**      | **Copyright in the file**                                          | **License Text in the file**                       | **Exception**  |
| b1.c          | A. Glass, Company C                                                | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| b2.c          | I. Will                                                            | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| b3.c          | T. Brown                                                           | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| Makefile      | None specified                                                     | None specified                                     | None specified |
| script        | None specified                                                     | None specified                                     | None specified |
| readme        | None specified                                                     | None specified                                     | None specified |
| NOTICE        | Apache Software Foundation, A. Glass, Company C, I. Will, T. Brown | None specified                                     | None specified |
| Package Facts | The Project                                                        | <http://www.opensource.org/licenses/apache2.0.php> | None specified |

Tools Source Files (sampling for illustrative purposes)

|                  |                           |                                                    |                |
| ---------------- | ------------------------- | -------------------------------------------------- | -------------- |
| **File**         | **Copyright in the file** | **License Text in the file**                       | **Exception**  |
| Tool1.c          | Many                      | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| Tool2.c          | Many                      | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| Makefile         | None specified            | None specified                                     | None specified |
| readme           | None specified            | None specified                                     | None specified |
| Binary data File | None specified            | None specified                                     | None specified |
| doc.html         | The Project               | <http://creativecommons.org/licenses/by-sa/3.0/>   | None specified |
| NOTICE           | Many                      | None Specified                                     | None specified |
| Package Facts    | Josh Brown                | <http://www.opensource.org/licenses/apache2.0.php> | None specified |

## Company A

  - Company A brought in the source from The Project.
  - They use the Package Facts from The Project and an Independent
    Auditor to help in analyzing The Project so they understand what
    their obligations are with respect to the licenses (e.g.
    redistribution of source, attribution, etc).
  - Company A has modified both libraries. It updates the existing
    Package Facts for each. Since Company A does have the same tool as
    The Project it hand edits the existing Facts files.
  - Company A did not modify the tool so they re-convey the existing
    Package Facts for the tool.

The files which now make up Library A are described in the table below.

|               |                           |                                                      |                 |
| ------------- | ------------------------- | ---------------------------------------------------- | --------------- |
| **File**      | **Copyright in the file** | **License Text in the file**                         | **Exception**   |
| a1.c          | Josh Brown, Company A     | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| a2.c          | Josh Brown                | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| a3.c          | Josh Brown                | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| a4.c          | Josh Brown, Company A     | <http://www.opensource.org/licenses/bsd-license.php> | See Exception 1 |
| Makefile      | None specified            | None specified                                       | None specified  |
| testdata.txt  | None specified            | None specified                                       | None specified  |
| readme        | None specified            | None specified                                       | None specified  |
| Package Facts | Josh Brown, Company A     | None specified                                       | None specified  |

The files which now make up Library B Source Files (sampling for
illustrative purposes)

|               |                                                                               |                                                    |                |
| ------------- | ----------------------------------------------------------------------------- | -------------------------------------------------- | -------------- |
| **File**      | **Copyright in the file**                                                     | **License Text in the file**                       | **Exception**  |
| b1.c          | A. Glass, Company C                                                           | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| b2.c          | I. Will, Company A                                                            | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| b3.c          | T. Brown                                                                      | <http://www.opensource.org/licenses/apache2.0.php> | None specified |
| Makefile      | None specified                                                                | None specified                                     | None specified |
| script        | None specified                                                                | None specified                                     | None specified |
| readme        | None specified                                                                | None specified                                     | None specified |
| NOTICE        | Apache Software Foundation, A. Glass, Company C, I. Will, T. Brown, Company A | None specified                                     | None specified |
| Package Facts | The Project, Company A                                                        | <http://www.opensource.org/licenses/apache2.0.php> | None specified |

## Company B

  - Company B gets the packages from Company A.
  - They use the Package Facts from Company A and an Independent Auditor
    to help in analyzing the unique instances of the packages to help
    them understand what their obligations are with respect to the
    licenses (e.g. redistribution of source, attribution, etc).
  - Company B wants to create an attribution document they can ship with
    their product (since it has binaries). They use information from the
    Package Facts to do this; as an example, to get the list of
    copyright holders.

(*Editorial Note: Company B was not shown modifying the Facts Files and
passing on to the consumer. They certainly could have done that
though.)*

## Analysis and Observations

(*Editorial Note: This section of the document is for use in analysis of
the use case.*)

The flow of the Fact files and who modified them, according to the
example above, is shown by the table below.

|                  |                       |                 |               |                                  |                                        |
| ---------------- | --------------------- | --------------- | ------------- | -------------------------------- | -------------------------------------- |
| **Package Fact** | **Library A Project** | **The Project** | **Company A** | **Company B**                    | **Independent Auditor**                |
| Library A        | Original              | Re-conveys      | Modifies      | Modifies, Consumes or Re-conveys | Modifies version in source it examines |
| Library B        | N/A                   | Original        | Modifies      | Modifies, Consumes or Re-conveys | Modifies version in source it examines |
| Tool             | N/A                   | Original        | Re-conveys    | Modifies, Consumes or Re-conveys | Modifies version in source it examines |

In some of the observations below, a best practice is recommended. I
think it is a good idea for the proposal to contain them (even in a
separate document). Listing best practices will help to clarify expected
behavior which can not be captured in the facts fields alone and should
help to create fewer variations on a theme.

In this use case, the Package Facts travelled with the Package vs. being
centralized in one location. While the current proposal does not
preclude either approach it would seem useful to examine both as each
has advantages and disadvantages and may affect the types of fields we
need in the proposal. I am thinking the options could be something like:
Facts follow a Package, Centralized but the distributor of a Package
posts the Facts file for all to see (and comment or possibly update),
Centralized but a common entity posts the facts files for all to see
(and comment or possibly update). There may be more variations. This is
a good area for someone to do an analysis with the pros and cons.

When I asked about the use case one of the responses was how would this
information be collected and put into a facts file. It is a fair
question but I think the answer would be that one size does not fit all.
Instead I propose we re-focus the question and look at the “facts” that
we convey and make sure that we allow for the maximum opportunity to
automate the their generation (for example, if it were me I would put
some doxygen keywords in the source files and call it a day).
Information used for the facts like copyright holders for a file may
change frequently for very active projects. Without the opportunity to
automate I believe larger projects will die under the weight of this and
that the information will not be as accurate due to the number of files,
etc that need to be documented.

Should the information in a facts file be taken at face value or does
the receiver need to decode the package and double check it? If you have
to re-decode the entire package I am not sure of the value of a facts
value (this should help entities receiving the Package to better
understand it is licensing). This level of “reliability” is a key point
and may not entirely emerge until the standard matures but we should be
cognizant of it and make sure that we do not over specify things (i.e.
keep it simple). That said it is fair to dig further if something does
not seem right.

What if the facts file from a project is incorrect? This could range
from minor typos, to missing file declarations, etc. It is entirely
possible that in the course of someone analyzing the files they find
some of these things. What should they do at that point? Do they correct
it; do they place something in the Independent Audit block? We should
specify the behavior or maybe a best practice. The value of this is
especially important as we mature the standard so having expectations
would be a good thing.

There is currently no way to capture the exception for Library A in the
facts file. It is possible it will be listed as a unique license in
which case Company A or any of the downstream recipients could have gone
to the source file but then I think we are assuming people will get the
license field right for the way we intended it to be used. If Library A
had listed it as BSD this may not have happened?

Would it be useful to have multiple audit blocks in one facts file? What
if The Project had audited the Facts and Company A had audited the
facts. It would also be useful to see who made what comments and why at
each stage.

It would seem that there could be multiple versions of a Facts File for
a particular Package and you could even use Facts files to see a history
of the Package (assuming we have a way to track that inside). This seems
useful for Company A or Company B when doing the analysis as they can
see the original file. For example, if Company A did an independent
audit of Library A and the Independent Audit Entity did one as well it
would be like getting a second opinion on the package which seems
useful.

Are Package Facts only created on a formal release a package? If not,
what happens if you access the package through a SCCS like GIT or SVN to
get the working tip? Would the facts file be completely up to date?
Maybe we do not need to worry about this, but I will throw it out there
anyway. This could also be handled through some sort of best practice.

Company B wants to create a single attribution document for their
release. In this example that is somewhat of a trivial exercise. In
reality they need to mash 30-40+ packages in a consumer product of any
size. If the various fact files they want to mash are under different
and potentially incompatible licenses this may hamper their ability to
do so.

In large distributions where some projects assemble other open source it
seems reasonable that a package facts would follow the packages they
bundle like they did in this example of The Project using the one from
Library A. The organization pulling in these packages could mash them in
some way but it if they do not, do we want to specify any guidelines on
how to communicate how many there are, where they are, etc. We may want
to document some best practices along with the proposal so they are
easily discoverable, etc.

[Category:Technical](Category:Technical "wikilink")
[Category:Archived](Category:Archived "wikilink")
