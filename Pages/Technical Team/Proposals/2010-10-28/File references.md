Status: draft

## Issue

The spec does not make it clear how individual files are to be
referenced. This makes discussion of individual files difficult. It
leaves it ambiguous which files in a package are related to File blocks
in the SPDX file. It prevents asserting the equivalence of a file in one
package to a file in another package.

## Proposal

Add the following text to section 3.

> A Package is a collection of one or more files. The files are grouped
> together for the purpose of distributing the software. A Package is
> identified by a URI. This URI can be any valid URI but will most often
> be the URI used to download the package. For example, package being
> described might be
> \<[http://www.apache.org/dist/httpd/httpd-2.2.17.tar.gz\>](http://www.apache.org/dist/httpd/httpd-2.2.17.tar.gz%3E);
> 
> The URI of a package is intended for identification purposes. As such
> a package URI does not have to be dereferenceable. It is acceptable
> for a URI to become unreachable over time or to never indicate a
> network fetchable resource. When indicating a package that does not
> have a public URI you may use an URL that is not reachable from the
> public Internet. If you prefer not do mint a URL for a package you
> many use the SPDX package URN scheme (see Appendix V).

Add the following text to section 5.

> A file is an atomic series of octets. A file may exist on disk, in a
> package or archive file or a resource available via a network protocol
> such as HTTP or FTP. A file is always identified by a URI. Files that
> are contained in a package or archive file whose format store path
> information will are identified by appending that path information in
> the fragment part of the package or archive URI. For example,
> \<[http://www.apache.org/dist/httpd/httpd-2.2.17.tar.gz\#httpd-2.2.17/server/main.c\>](http://www.apache.org/dist/httpd/httpd-2.2.17.tar.gz#httpd-2.2.17/server/main.c%3E);

Create Appendix IV

## Appendix IV: SPDX Package URN scheme

This URN scheme is defined to allow packages to be identified when they
do not have URIs or the provider of the SPDX file does not wish to
expose the URI.

An example SPDX package URN is <urn:package:apache:httpd-2.2.17.tar.gz>.
That SPDX package urns have the following syntax.

` packageuri = "`<urn:package>`:" vendor ":" packageid`  
` vendor = *VCHAR`  
` packageid = *VCHAR`

The vendor is the name of the vendor of the package in question. The
package id is a string that uniquely identifies the package. Package
identification should include the name and version information for the
package.

[Category:Technical](Category:Technical "wikilink")
