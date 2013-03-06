**April 14, 2010**

This is a sample of what Geronimo would look like under current spec.
Note that I have not provided all of the data – since it would be very
large, but just some samples so we can see how it looks.

**IDENTIFICATION**

**Version**: 1.0

**UniqueID**: 123456789abcdef

**Tool**: OSSDeepDiscovery

**Tool**: FOSSology

**Manual**: OpenLogic

**Reviewed by**: Jane Doe

**Created**: 20100315-HH:MM:SS

*Issues*

  - *Will likely have used multiple tools as well as manual review to
    create this list. Need to have a way to include all of those.*
  - *For “manual”, we may want a company name – not a person’s name*
  - ''As packages get passed up the supply chain, it may be modified or
    added to by multiple people, companies, tools – how do we manage
    that? ''
  - *Do we want to include the field names – or just the value?*
  - ''It’s not 100% clear what “reviewed by” means. Do we really need
    it? ''

**OVERVIEW**

**Formal Name:** Geronimo

**Package Identifier:**
[**geronimo-jetty6-javaee5-2.1.4-bin.tar.gz**](http://apache.inetbridge.net/geronimo/2.1.4/geronimo-jetty6-javaee5-2.1.4-bin.tar.gz)

**Official Source Location:**
<http://geronimo.apache.org/downloads.html>

**Declared License:** Apache-2.0

**Licenses Present:**

Academic-2.1

Apache-1.1

Apache-2.0

Bouncy Castle

BSD

BSD (3 clause)

CDDL

CDDL-1.0

CPL-1.0

CDDL or GPL-2.0 with classpath exception

Dojo

JSON

Jtidy

MIT (modern style with sublicense)

Public Domain

Sun Binary Code License for JDK

Sun Community Source License Version 2.3

W3C-Software

**Copyright Holder:** The Apache Software Foundation

**Copyright Holder:** The Dojo Foundation

**Copyright Date of Package**: 2003-2009 (for ASF)

**Copyright Date of Package**: 2005-2008 (for Dojo)

*Issues*

  - *There doesn’t seem to be any information about what open source
    packages the additional licenses are associated with. Do we want
    that? Many of the additional licenses come from “bundled” packages.
    Knowing what package it is can be helpful, but we don’t show that*
  - *Where should actual license text go?*
  - ''Copyright holder and Copyright Date can be problematic – since
    there may be multiple. What does it mean to have a single one?
    Should we list them all here? Need to align which copyright holders
    and dates go together. ''
  - *Should we be listing copyright for other bundled packages?*
  - *For non-ASF projects, this will get even more complicated.*
  - *All of the highlighted licenses don’t have a short name in Fedora.
    Would we want all of those to be “Other”*
  - *There are a bunch of other notices/copyrights – how should those be
    handled?*

**DETAILS**

**File Name**:

assemblies/geronimo-boilerplate-minimal/LICENSES.TXT

assemblies/geronimo-boilerplate-minimal/src/main/underlay/var/config/README.TXT

assemblies/geronimo-jetty6-javaee5/LICENSE.txt

assemblies/geronimo-jetty6-minimal/LICENSE.txt

assemblies/geronimo-tomcat6-javaee5/LICENSE.txt

buildsupport/buildsupport-maven-plugin/LICENSE.txt

buildsupport/geronimo-assembly-archetype/LICENSE.txt

plugins/connector/geronimo-connector-builder/src/test/resources/database.rar

etc….

**File Type**: How do we handle this at directory level where there may
be multiple types

**License**: Apache-2.0

**Copyrights**: Various??? Do we want to list all of them?

**File Name**:

buildsupport/car-maven-plugin/src/main/java/org/apache/geronimo/mavenplugins/car/AbstractCarMojo.java\!/java.io.BufferedOutputStream

**File Type**: source

**License**: Sun Binary Code License for JDK

**Copyrights**: Sun Microsystems

**File Name**:

buildsupport/geronimo-maven-plugin/src/main/java/org/apache/geronimo/mavenplugins/geronimo/ServerProxy.java\!/javax.management.remote.JMXServiceURL

**File Type**: source

**License**: Sun Community Source License Version 2.3

**Copyrights**: Sun Microsystems

**File Name**:

buildsupport/car-maven-plugin/src/main/java/org/apache/geronimo/mavenplugins/car/CreatePluginListMojo.java\!/org.xml.sax.SAXException

**File Type**: source

**License**: Public Domain

**Copyrights**: ??

**File Name**:

buildsupport/testsuite-maven-plugin/src/main/java/org/apache/geronimo/mavenplugins/testsuite/ResultsSummaryMojo.java\!/org.w3c.dom.Document

**File Type**: ????

**License**: W3C

**Copyrights**: ??

*Issues:*

  - *We can have lots of files and directories that are spread all over
    the project that fall under one license, but are of different types
    and copyrights. Do we need different blocks for each of these? Or
    can we list multiple files/directories*
  - *Do we really want to list every file here?*
  - *Do we just show exceptions to the Declared license*
  - *Do we need copyrights down to the file level? Or just an aggregated
    list?*
  - *With license.txt files or copying files, are we applying the
    license automatically to every file in the directory? The sub
    directory?*
  - *The file type is not easy – doesn’t the file name tell us that? Can
    we drop that field*
  - *I think we should reorient around licenses – list the licenses and
    then a set of files associated with them….creating a*
  - '' definitive list of files for a license is not straightforward
    since you may have a licenses.txt file in a directory''
  - ''Where does the actual license text go? ''

[Category:Technical](Category:Technical "wikilink")
[Category:Archived](Category:Archived "wikilink")
