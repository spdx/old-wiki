  
<span style="font-size:150%">**Welcome to the 2020 SPDX Community Bridge
Project Ideas Page**</span>

Proposals can use the [Google Summer of Code proposal
template](https://rtgdk.github.io/spdx-gsoc-proposal.html) as a general
guide for community bridge projects.

Should you have questions please do not hesitate to contact one of the
mentors directly.

  
\_\_TOC\_\_

  

## What is SPDX ?

First and foremost we are a community dedicated to solving the issues
and problems around Open Source licensing and compliance. The SPDX work
group (part of the Linux Foundation) consists of individuals, community
members, and representatives from companies, foundations and
organizations who use or are considering using the SPDX standard. The
work group operates much like a meritocratic, consensus-based community
project; that is, anyone with an interest in the project can join the
community, contribute to the specification, and participate in the
decision-making process. We come from many different backgrounds
including open source developers, lawyers, consultants and business
professionals, many of who have been involved with license compliance
and identification for years.

As part of this effort we have developed a set of collateral that can be
used:

  - [License List and Short Identifiers](https://spdx.org/using-spdx)
  - [SPDX Specification for generating SPDX Documents in multiple
    formats](https://spdx.org/using-spdx)
  - [A set of basic tools for working with SPDX
    Documents](https://spdx.org/tools)
  - [License Identifiers in source](https://spdx.org/using-spdx)

## Why choose an SPDX Project?

Contributing to one of the SPDX projects below will provide a valuable
contribution to developers and/or users of open source software. We
believe you will find the projects both technically challenging and
rewarding. In essence we believe you will be able to look back one day
and I say I was part of that effort.

  

# Getting Involved

Beyond working with your mentor(s) we highly encourage students who
select one of these projects to get involved with the SPDX community via
our technical working group. Interaction with the technical team is
primarily done via its mailing list and on gitter (see resources). There
is however a weekly call you could join as well. .

## Resources

  - [SPDX website](http://spdx.org)
  - [SPDX Specification](https://spdx.org/specifications)
  - [SPDX Workgroup Tools webpage](https://spdx.org/tools)
  - [SPDX tech mailing
    list](https://lists.spdx.org/mailman/listinfo/spdx-tech)
  - [SPDX Git Repository](https://github.com/spdx)

# Proposed 2020 Projects

Mentors: please fill out the following template for any projects you
wish to propose.

`=== Project Name ===`  
`add overview of project here`  
`====Skills Needed====`  
`what skills should the student have to do the coding exercises`  
`====Background Information====`  
`context for the project and references to be studied`  
`====Available Mentors====`  
`list individuals who are willing to mentor and provide information about the project proposal. `

## SPDX Workgroup Tooling Projects

These projects are aimed at contributing to the SPDX tools to help
reduce the effort to create SPDX documents and increase the accuracy of
them.

### Replace Java Functions in the SPDX Online Tools with Python Library Functions

Improve the performance and reliability of the SPDX Online Tools by
replacing functions implemented in Java with native Python
implementations.

#### Skills Needed

  - Development skills in the Python
  - Based understanding of Java
  - Development skills in Django
  - Ability to work with the community in integrating results with other
    projects

#### Background Information

The [Python Tools](https://github.com/spdx/tools-python) library can be
used but will need to be extended and improved to replace the features.
The Java implementations can be found in the [SPDX Java tools
implementation](https://github.com/spdx/tools)

#### Available Mentors

TBD

### Improve the Python Libraries

The Python Libraries need to be updated to the SPDX 2.2 spec and there
are several issues outstanding.

#### Skills Needed

  - Development skills in the Python
  - Ability to work with the community in integrating results with other
    projects

#### Background Information

See the [SPDX Python Tools Issues
List](https://github.com/spdx/tools-python/issues) for more information.

#### Available Mentors

TBD

### Improve the Deployment Infrastructure for the SPDX Online Tools

Improve the reliability, security and deployability of the SPDX online
tools including container management, deployment testing and monitoring.

#### Skills Needed

  - Development skills in Python and Django
  - Experience with containers
  - Understanding of software as a service deployment

#### Background Information

The current SPDX online tools is deployed manually on an Amazon AWS EC2
Linux instance. The current process is error prone and labor intensive.
We would like to move to a more automated and reliable mechanism. There
is a variety of possible deployment architectures including a container
based approach using Kubernetes.

#### Available Mentors

[Gary O'Neall](mailto:gary@sourceauditor.com) TBD

### Implement SPDX License Matching in Python

Implement as much of the SPDX License Matching Guidelines as practical
in Python. This could replace the current Java implementation for the
[Check License](http://13.57.134.254/app/check_license/) SPDX Online
license checking tool.

Following is a list of suggested features:

  - Provide an interface which will check text against a license
    template using the license matching guidelines
  - Provide an interface which will check text and return all matching
    SPDX listed license ID's
  - Provide an interface which takes 2 license texts as input and
    returns a boolean indicating if the 2 licenses match per the license
    matching guidelines
  - When there is not a match, provide a return value making it possible
    to describe where and why the license does not match

#### Background Information

  - See the [SPDX License Matching
    Guidelines](https://spdx.org/spdx-license-list/matching-guidelines)
    for a description of the guidelines
  - A technical description of the templates and license matching can be
    found in [Appendix
    II](https://spdx.org/spdx-specification-21-web-version#h.2mjng0vqrghe)
    of the SPDX specification
  - A Java implementation can be found in Github [SPDX Tools
    LicenseCompareHelper.java](https://github.com/spdx/tools/blob/master/src/org/spdx/compare/LicenseCompareHelper.java)
  - It's harder than you may think - the template language is a
    challenge to implement. Performance can be a challenge when matching
    a single text against hundreds of potential licenses. Reporting back
    where the missmatch occurs can also be a challenge.

#### Skills Needed

  - Development skills in the Python
  - Skills in parsing and pattern matching
  - Ability to work with the community in integrating results with other
    projects

#### Available Mentors

[Rohit Lodha](mailto:rohit.lodhartg@gmail.com) [Gary
O'Neall](mailto:gary@sourceauditor.com)
