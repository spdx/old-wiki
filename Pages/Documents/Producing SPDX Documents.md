  

|                                                               |                      |
| ------------------------------------------------------------- | -------------------- |
| ![Logo\_spdx\_250.png](Logo_spdx_250.png "Logo_spdx_250.png") | **SPDX Tech Report** |

<hr>

  
  
<span style="font-size:40px">PRODUCING SPDX DOCUMENTS</span>  
version 0.1  
WORKING DRAFT

  
  
\_\_TOC\_\_  
  

# Overview

SPDX documents describe the licensing associated with a files. These
files can be organized into what we call a "Package". A package is
merely a grouping of files, with some association to each other as
defined by the creator of the document. In general, the association
should be obvious, such as an SPDX document for a software library or
application. SPDX Documents can use one of two formats:

  - Tag/value -a simple text based format. Here is an example you can
    view.
  - RDF/xml - a Resource Description Format developed by the W3C. Here
    is an example you can view.

You can use either format and there are SPDX tools to convert one format
to another. The format you use will be based on your own factors,
preference, tools and use.

# SPDX Document

The most current version of the specification can be found here:
[Specifications](https://spdx.org/specifications). Prior to reading
through this document, we recommend you read through this section and
then read through the latest specification to get a more in depth feel
for the sections and fields.

## Structure of an SPDX Document

![specification21.png](specification21.png "specification21.png")

SPDX Documents are composed of one or more sections. Some of these
sections are required, while others are optional. If you examine the
figure, you will see the following sections as of the 2.1 Specification:

  - Document Creation Information - Denotes who created the document,
    how it was created and other useful information related to its
    creation.
  - Package Information - This section provides information about the
    "package". A package can be one or more files. These files could be
    one or more files of any type including but not limited to source,
    documents, binaries, and so forth. The package information contains
    the originator, where it was sourced from, a download URL, a
    checksum and so forth. it also contains summary licensing for the
    package.
  - File Information - This is information about a specific file. It can
    contain the file copyrights found in the file (if any), the license
    of the file, a checksum for the file, file contributors and so
    forth.
  - Snippet Information - Snippet information can be used to define
    licensing for ranges within files.
  - Other Licensing Information - Other licensing information provides a
    way to describe licenses that are not on the SPDX License List. You
    can create a local (to the SPDX document) identifier for the license
    and place the license text itself in the document as a well and then
    reference it for files just like you would a license from the
    license list.
  - Relationships - Relationships were introduced in the 2.0
    specification and are a very powerful way of expressing how SPDX
    documents relate to one another. See explanation and example above.
  - Annotations - Annotations are comments made by people on various
    entities and elements within the document. For example, someone
    reviewing the document may make an annotation about a file and its
    license. Annotations are useful for reviews of SPDX documents and
    for conveying specific information about the package, file,
    creation, license, file(s), etc

## Optional vs. Required Fields

Each field in the SPDX Specification has a Cardinality associated with
it. Possible values for this are: xx.

As an example: Cardinality:​ Optional, one or many.

## Packages and Relationships

  

# Tooling

## SPDX Workgroup Tools

## Community Tools

## Commercial Tools

# Strategies

## Build Time Generation of Documents

# Best Practices

Editors Note: we may move this section to its own document upon
completion.

# Examples

The following application will be used in the examples for this section.
As the examples are meant to build on one another in terms of the use
case and complexity they show. Some examples may use only portions of
the application. Each example will state what is used. By using one
application, going through the examples should be easier. The
application used is time, version 1.7 with some made up directories
added (okay alone it was too simple).

Download the example here

## A Simple Example (aka hello world)

## Document with minimum Required Fields

## SPDX document for a binary delivery - no relationships

## SPDX document for a binary delivery - uses relationship to point to source package

## SPDX document for an application delivery (source, binaries, documents, etc) - more expressive use of relationships
