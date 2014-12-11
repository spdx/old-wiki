## Why was the license expression syntax introduced in the SPDX 2.0 specification?

The SPDX 1.x Specification and earlier versions of the License List had
a limited ability to represent more complex license situations typically
found in practice. Examples of such complexity can be found at:
<http://wiki.spdx.org/view/FileNoticeExamples> . Additionally, earlier
versions of the SPDX License List required the addition of multiple yet
similar license identifiers in order to capture combinations of
versions, the “or later” license genre (i.e. GPL-2.0 and GPL-2.0+) and
the most common exceptions (e.g., GPL-2.0+-with-autoconf-exception or
GPL-3.0-with-autoconf-exception). The SPDX Legal working group
identified more than 30 additional distinct exceptions. If one tried to
accommodate the many different permutations of the different exceptions
with the “or later” cases, the license list would become unnecessarily
bloated. For additional historical background information you can
reference:
<http://wiki.spdx.org/view/Legal_Team/License_Expression_Review_1>. All
in all, the introduction of the WITH and ‘+” operators, and the addition
of the new license list exceptions section, we are able to represent
more sets of license terms found in practice while simultaneously
streamlining the SPDX License List.

## Why do we need a license expression syntax when projects are available under a single license?

Typically an open source project will start out making their software
available under a single open source license but as some projects evolve
they may leverage code from other successful projects governed by
different licenses. Consequentially many successful projects end up with
a diverse collection of files that are available under different
licenses. Often programs are built from a diverse collection of files
that are available under a composite set of different license terms. The
SPDX License Expression language provides a way for one to construct
license expressions that more accurately represent the licensing terms
are typically found in open source software source code. Also some
projects may offer their software under a multi-license choice where a
license expression provides a formal way to representing this.

## Are there examples of different license expressions found in practice?

Yes, you can find examples here:
<http://wiki.spdx.org/view/FileNoticeExamples>

## In the SPDX 2.0 Specification why is GPL-2.0+ no longer a proper license identifier?

The license identifier “GPL-2.0+” will be depreciated in the updated
version of the SPDX License List that accompanies the SPDX 2.0
specification release. The license identifier “GPL-2.0” (without the
“+”) is still a valid identifier. After using SPDX in practice it
was realized that there are several benefits to treating the “+” as a
separate operator. The expression GPL-2.0+ is a valid expression in SPDX
2.0 and has the same semantic meaning as the deprecated license
identifier “GPL-2.0+”. The only difference is that the “+” is an
operator that stands for “or a later version”. The “+” can now be used
with other licenses in addition to the GPL and LGPL (e.g., EPL-1.0+). It
reduces license list bloat, that is, we do not need to add every
possible license with a “+” for all possible license cases one may
encounter. This also applies to license exceptions. By introducing the
“+” and “WITH” operators we can more simply and conveniently represent
the myriad of special exceptions without needing to clutter the license
list with all the different combinations that include the GPL and LGPL
and later versions of the license. That is, we wanted to avoid adding
the following to the license list:  
\* GPL-2.0-with-autoconf-exception  
\* GPL-2.0+-with-autoconf-exception  
\* GPL-3.0-with-autoconf-exception  
\* GPL-3.0+-with-autoconf-exception  
Now we just need to add autoconf-exception to the SPDX License List as
opposed to the above four identifiers. If a new version of the GPL was
released (e.g., GPL-4.0) only one license identifier needs to be added
as opposed to one for all the potential special exception combinations
(e.g., autoconf, bison, classpath, …)

## In the SPDX 2.0 Specification why are certain licenses with exception identifiers (e.g. GPL-2.0-with-bison-exception) no longer in the SPDX License List?

It was decided to rework the way special expectations will be handled in
the 2.0 version of the SPDX specification. The SPDX Legal working group
identified more than 30 additional distinct exceptions. If one tried to
accommodate the many different permutations of the different exceptions
with the “or later” cases, the license list would become bloated and
unwieldy. The introduction of the WITH operator and a separate list of
exception identifiers alleviates the problem.

## Does a license expression imply any particular legal interpretation?

No. Although the semantics of the operators describe a physical
relationship between licenses, it is up to the user or distributor of
the software to decide how to interpret the legal dynamics of the
physical relationship of the licenses. For example, the expression
GPL-2.0 OR BSD-3-Clause describes a relationship where one can choose
between two licenses, but it does not imply any specific interpretation
of how to choose or the way to interpret the respective licenses.
Another example is GPL-2.0 AND BSD-3-Clause. The AND operator represents
that the code from two different works has been combined via linking or
source code embedding (e.g., for example a program is created by
combining two different files under two different licenses). It does not
specifically imply whether the resulting expression is a derivative work
or a collection. The legal determination of whether the two licenses are
compatible or how one might interpret the marriage of these licenses is
left to the user or distributor of the file or program. It is
conceivable that different organizations could come to different legal
determinations for the same license expression. This is no different
than two organizations having different interpretations of a given
license or how to interpret the ramifications of dynamic vs. static
linking.

## What is the difference between a License and a License Expression?

A license represents a single well defined license text such as the GNU
Public License or the Apache License which may have different versions
made available over time. A license expression can describe the
relationship between two or more licenses or license exceptions. A
relationship is often created when one mixes source code under two
different licenses or one chooses to offer there software under a choice
of two or more licenses.

## Is the License Expression Syntax Case Sensitive?

No. One can use both upper or lower case.
