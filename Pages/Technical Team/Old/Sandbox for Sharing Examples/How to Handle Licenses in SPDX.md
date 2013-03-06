**Handling of Licenses IDs (Short names)**

  - We have proposed using the Fedora short names
  - We have also looked at the Debian naming scheme
  - There are a couple of key differences
  - **Version handling**

1\. Fedora builds versions into the short name, but it is done in a
non-standardized way that seems to vary from license to license, eg

  - ASL 1.0 (for Apache 1.0)
  - AGPLv1 (for Affero GPL v1)
  - CeCill (for both Cecill v1.1 and v2)

2\. Debian proposes a standard way – “license name-version”, eg

  - GPL-2
  - Apache-2

3\. Both Fedora and Debian also use standard way to deal with the “and
later” version options by using a “+”, eg

  - GPL-2+ (debian)
  - GPLv2+ (Fedora)

**4. Suggested Solution for SPDX**

  - I believe we should have a standard way to handle versions for SPDX.
    I would suggest going with the Debian approach or something similar.
    This would entail slightly modifying the Fedora short names where
    they do not follow the standard
  - I’m not sure if there is some reason why Fedora hasn’t standardized
    this.

**Handling of “standard” exceptions is different**

1.  Fedora just uses a term that is “with exceptions” They don’t tell
    you which exceptions. The result is that a short name “**GPLv3 with
    exceptions**” is used for both the classpath and font exceptions.
    This seems to create ambiguity.
2.  Debian proposes naming the common exception – with the following
    syntax

<!-- end list -->

  - GPL-2+ with classpath exception
  - GPL-2+ with font exception

**3. Suggested Solution for SPDX**

  - I believe we should use the Debian approach for common “approved”
    exceptions such as the 2 mentioned for GPL

**Spaces in short name**

1.  Fedora has spaces in the short names
2.  Debian does not (they do have spaces when they do “with exceptions”

**3. Suggested Solution for SPDX**

  - I would ask the technical people if this will be problematic having
    spaces when we want to automatically parse these files.

**Handling of multiple licenses**

1.  Both Fedora and Debian use “ands” and “ors” when there are multiple
    licenses associated with a pkg.

<!-- end list -->

  - “and” when you must comply with the terms of all the licenses
    because parts of the package or file are under difference licenses
      - artistic-1 and gpl-2
      - “or” when you get to choose a license
          - artistic-1 or gpl-2

2\. Both Fedora and Debian address the combining of ors and ands.

  - \*\* Use parentheses when needed
      - (artistic-1 or gpl-2) and lgpl=1.1
      - “and” takes precedence
      - GPL-2+ with font exception

**3. Suggested Solution for SPDX**

  - Follow the same rules

**Handling of license variations**

1.  There are several licenses that have “variations”. MIT and BSD are
    examples of this. These situations are handled differently by Fedora
    and Debian.
2.  Fedora

<!-- end list -->

  - For MIT, Fedora treats a bunch of the MIT variations as
    “functionally equivalent” and uses the short name “MIT” to refer
    to all of them. They have a page listing all of the MIT variants and
    the actual text. <https://fedoraproject.org/wiki/Licensing/MIT>
  - For BSD, Fedora seems to have different short names for each of the
    variants, eg
      - BSD License (original) = short name “BSD with advertising”
      - BSD License (no advertising) which is a 3 clause version and BSD
        License (two clause) both = short name of “BSD”
      - BSD Protection License = short name of “BSD Protection”
      - Academy of Motion Picture Arts and Sciences BSD = “AMPAS BSD”

3\. Debian

  - For MIT, Debian says that it is “problematic” and hasn’t addressed
    it . They have no short name for MIT yet.
  - For BSD, Debian has a short name for BSD, but it’s unclear how the
    variants are handled

**4. Suggested Solution for SPDX**

  - This one is a little complicated. I think for any situation where we
    have different variants of a license, they should have different
    short names. Fedora has done this to some extent, but in some cases
    (like BSD 2 and 3-clause) they have combined it to use one short
    name. This would require us to stray from the short names of Fedora.
  - The other question is what do you do with “other” variants that
    don’t have a unique short name. Some people use “BSD-like” or
    terms such as that. I know some people don’t like that. It seems
    that for now the most accurate approach would be either to give a
    variant it’s own short name, or tag it as an “Other” license.

[Category:Technical](Category:Technical "wikilink")
[Category:Archived](Category:Archived "wikilink")
