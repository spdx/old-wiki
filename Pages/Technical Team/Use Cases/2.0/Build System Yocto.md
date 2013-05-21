**Title:** Yocto Build System

UPDATE 05/21/2013: Yocto project is actively trying to utilize SPDX.
Here's a writeup they did
<https://bugzilla.yoctoproject.org/show_bug.cgi?id=4516>

**Background:**

Note: This is not a detailed background. You are encouraged to read up
on the Yocto Project by using the following link:
<http://www.yoctoproject.org/docs/1.0/yocto-quick-start/yocto-project-qs.html>

The Yocto Project provides a build system which can be used to provide,
as an example, a file system/kernel/boot loader image that can be
downloaded onto a device and executed. When Yocto builds a package the
package source can come from various sources such as source code control
system like GIT, a tarball, patches and so forth. Entities providng a
Yocto build for their hardware may also be providing pacthes for the
package.Whenever a build is executed, it is possible that the files in a
package are updated (added, modified, removed, etc).

Yocto uses recipes to build packages. These recipes do contain a License
field. The current short names do not match SPDX short names and likely
will not. It was rather difficult to get alignment on the current ones
used. There is talk on the Yocto project about converting the Yocto
short names into SPDX ones.

**Primary Actors:**

Yocto User: Receives a Yocto build for a device. Executes the build.

Package Maintainer: These are upstream projects that a Yocto based build
consumes. This upstream project could be a company that provides a
package as well. A Package Maintainer could be viewed as having a
secondary interest in this use case as their package may be consumed by
a Yocto build even though they as packages maintainers have no vested
interest in Yocto.

the Yocto Project: Provides the Yocto build system.

Build System Provider: They provide a Yocto based build, for example for
their product. They may also provide patches to Packages that the
recipes pull or may even add their own packages.

**Goal in Context:** To execute a Yocto based build and generate an
image for a hardware device or simulator and to have SPDX documents that
describe the licensing for all copyrightable artifacts pulled in by the
build system and used to generate that image (i.e. not just artifacts
that make it into the image, everything and everything that it pulls
including the build system). Note: envision we could be talking about
1000's of related SPDX documents

**Stakeholders and Interests:**

Yocto User:

A. To receive accurate and clear information of licensing for all
copyrightable

elements used in the build and for the build system.

B. To be able to comply easily with licenses for all copyrightable
elements used in

the build and the build system.

2\. Package Maintainer:

A. To communicate the license information for their package.

B. To have their licenses respected.

3\. the Yocto Project:

A. To communicate the license information for their build system and the
licensing of each package

(currently via the license field in a recipe).

B. To have their licenses respected.

4\. Build System Provider:

A. To communicate the licensing information for the build they are
providing.

B. To comply with all the licenses used in the build the system they are
providing.

**Preconditions:**

1.  A yocoto build is created.
2.  Packages used in the Yocoto build have SPDX documents describing the
    copyrigthable elements of the package.
3.  A patch for a package used in the build is created.

**Main Success Scenario:** A user executing a Yocto based build gets
SPDX documents that describe the licensing for all copyrightable
elements that were used to create the build and are the result of a
build.

**Failed End Condition:** Inaccurate or incomplete licensing information
is provided for all packages used in the build and/or for the Yocto
build system.

**Trigger:**

A Yocto user executes a build.

Note: I forgot a point around RPMs when doing this and need to follow up
again with the Yocto Project.

[Category:Technical](Category:Technical "wikilink")
