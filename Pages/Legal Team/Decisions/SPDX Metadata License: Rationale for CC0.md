## Overview

SPDX files represent a summary of license information extracted from
software source code. The SPDX Legal working group evaluated different
licenses that can be used to cover the data contained in a SPDX file.
One challenge was that the working group did not want to imply that the
data contained in a SPDX file is potentially copyright protected. On the
other hand, in some jurisdictions, data could be considered intellectual
property. In those jurisdictions the working group stride to provide a
license that mitigates the risk of someone obtaining controlling IP
rights over SPDX data. The following were the core requirements driving
the license evaluation process. We sought a license that:

  - does not imply that SPDX data is intellectual property;
  - in jurisdictions that permit data to be intellectual property -
    prevents others from claiming controlling ownership over the data
    contained in a SPDX file;
  - will not hinder adoption of the SPDX format by the open source
    community;
  - minimizes further license proliferation in the open source
    community;
  - permits the exchange of SPDX files under confidentiality terms
    (potentially temporarily) for special situations that may require
    it.

After careful consideration the Creative Commons Zero 1.0 Universal
license was chosen. The rationale for each of the license candidates
considered can be found below.

## License Candidates

**Public Domain Dedication and License (PDDL)**

PDDL is the current designated license for SPDX files as required by the
SPDX 1.0 specification. PDDL was initially chosen because it was a
“data” license. That is, it was initially design to be used with
data as opposed to software or other copyrightable works. The reception
of PDDL as the SPDX file data license has been mixed and somewhat
controversial at times. A copy of the PDDL license can be found here:
<http://opendatacommons.org/licenses/pddl/1.0/>

  - Pros
      - Designed for licensing data.
      - Useful in jurisdictions where intellectual property rights are
        granted to data (bases).
      - Attempts to make data freely accessible (in a similar spirit
        that open source licenses do for software).
      - Permits the exchange of SPDX files under confidentiality terms.

<!-- end list -->

  - Cons
      - Lengthy license (6 pages) – will take time for people to review
        and understand.
      - Yet another new license for open source community to review,
        understand and accept. Would likely add friction to SPDX
        adoption.
      - A major open source foundation pointed out it would be hard to
        get PDDL approved by their organization as well as other
        foundations. This is especially true when considering a license
        that is not familiar to the community (as is the case with
        PDDL).
      - Use of the license implies that SPDX data is copyright
        protected.

**MIT Style SPDX Draft**

The license text is based on the MIT open source license. A copy of the
MIT Style license draft can be found in the appendix of this
document.''''''

  - Pros
      - Viewed more as a disclaimer notice than a data license. The
        intent is to view the SPDX file content as data as opposed to
        protected intellectual property.
      - Serves more as a license in jurisdictions where data is
        considered protectable intellectual property.
      - The license text is short and easy to understand.
      - The license is familiar to the open source community and would
        likely not add much friction to the adoption of SPDX.
      - Permits the exchange of SPDX files under confidentiality terms
  - Cons
      - The license is based on the MIT open source license which was
        designed to be used with software as opposed to data.
      - Requires attribution. Many different SPDX files used in a
        project or supply chain may potentially require the publication
        of many different attribution notices.

'''CC0 1.0 - Universal Public Domain Dedication license '''

Creative Commons (CC) is a non-profit organization devoted to expanding
the range of creative works available for others to build upon legally
and to share. The organization has released several copyright-licenses
known as “Creative Commons” licenses, free of charge to the public. One
such license is the CC0 1.0 which allows one to contribute their work to
the public domain. A copy of the CC0 1.0 license can be found here:
<http://creativecommons.org/publicdomain/zero/1.0/>

  - Pros
      - License text is short and easy to understand.
      - License is familiar to the open source community and therefore
        would likely not to add significant friction to the adoption of
        SPDX.
      - Achieves object of having the data be considered public domain
        in those jurisdictions where data can be protected as
        intellectual property.
      - Permits the exchange of SPDX files under confidentiality terms.
  - Cons
      - License was not designed to be used with data.
      - Use of the license implies that SPDX data is copyright
        protected.

**No License Provided**

One option is to take the position that no license applies.

  - Pros
      - Easy to understand. Does not add friction to adoption of SPDX.
      - Promotes the idea that the SPDX data is not intellectual
        property (e.g., not copyrightable).
      - Permits the exchange of SPDX files under confidentiality terms.
  - Cons
      - Does not prevent one from trying to obtain controlling rights in
        jurisdictions where data is potentially considered intellectual
        property.

[Category:Legal](Category:Legal "wikilink")
