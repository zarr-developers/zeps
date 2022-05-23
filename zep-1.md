# ZEP 1 - Zarr version 3

---

Author:

* Alistair Miles <alistair.miles@sanger.ac.uk>

Status: Draft

Type: Specification

Created: 2022-05-23


## Abstract

This ZEP proposes a new major version of the core specification which
defines how to store and retrieve Zarr data. The ZEP also proposes a
new framework for modularising specifications of codecs, storage
systems and protocol extensions.


## Motivation and Scope

Zarr version 2 [ZARR2SPEC](#ref-ZARR2SPEC) has been widely adopted and
implemented in several programming languages. It has enabled the use
of cloud and distributed computing to process a variety of large and
challenging datasets, particularly in the scientific domain. It has
also provided a vehicle for experimentation and innovation in the
field of data storage for high-performance distributed computing.

As usage of Zarr has grown and broadened, several limitations of Zarr
version 2 have surfaced. These include:

* **Interoperability**. Zarr version 2 has been implemented in Python,
  C, C++, Julia, Java and JavaScript. However, there is not feature
  parity across all implementations. Implementations are also not
  currently available for some important languages, such as R. This is
  in part because the version 2 spec was originally developed together
  with the Python implementation, which itself leans heavily on the
  use of NumPy concepts and machinery. A more language-agnostic
  approach to the core specification, together with some slimming down
  of the specification, would help to achieve complete implementations
  with full interperobility across major programming languages.

* **Extensibility**. Zarr verion 2 has been used already for storage
  of some very large and keystone scientific datasets. If this trend
  continues, interoperability and stability of the Zarr ecosystem will
  be vital, to allow these datasets to be utilised to their full
  potential. At the same time, large-scale array data storage is a
  very active area of innovation, and there remain many opportunities
  to improve performance, scalability and resilience for I/O-bound
  high-performance distributed computing. To balance these demands for
  stability and innovation, some framework for community exploration
  and development of Zarr extensions is needed, so that innovation can
  happen in a coordinated way with predictable consequences and
  behaviour of implementations which may or may not support
  extensions.

* **Storage**. Zarr version 2 was originally developed to support
  local file system storage only. Because of this, the design of Zarr
  version 2 implicitly made certain assumptions about the performance
  characteristics of the underlying storage system, such as low
  latency of storage operations to list directories and retrieve small
  files. Fortunately, certain features of Zarr 2 allowed other storage
  systems to be used, such as cloud object stores, and this ability to
  utilise a variety of different underlying storage systems has been
  very valuable across a range of use cases. However, performance of
  certain operations can degrade significantly with some storage
  systems, particularly systems with relatively high latency per
  operation, such as cloud object stores. This limitation has been
  worked around through the use of consolidated metadata, but this
  workaround introduces other limitations, such as additional
  complexity when adding or modifying data.

@@TODO wrap up.


## Usage and Impact

@@TODO

This section describes how users of Zarr will use the new features,
spec changes or a new process described in this ZEP. It should be
comprised mainly of code examples that wouldn’t be possible without
acceptance and implementation of this ZEP, as well as the impact the
proposed changes would have on the ecosystem. This section should be
written from the perspective of the users of Zarr, and the benefit it
will provide them; as such, it should include implementation details
only if necessary to explain the functionality.


## Backward Compatibility

@@TODO

This section describes how the ZEP breaks backward compatibility.

Its purpose is to provide a high-level summary to users who are not
interested in detailed technical discussion, but may have opinions
around, e.g., usage and impact.


## Detailed description

@@TODO

This section should provide a detailed description of the proposed
change. It should include examples of how the new functionality would
be used, intended use-cases and pseudo-code illustrating its use.


## Related Work

This section should list relevant and/or similar technologies,
possibly in other libraries. It does not need to be comprehensive,
just list the major examples of prior and relevant art.


## Implementation

This section lists the major steps required to implement the
ZEP. Where possible, it should be noted where one step is dependent on
another, and which steps may be optionally omitted. Where it makes
sense, each step should include a link to related pull requests as the
implementation progresses.

Any pull requests or development branches containing work on this ZEP
be linked to from here. (A ZEP does not need to be implemented in a
single pull request if it makes sense to implement it in discrete
phases).


## Alternatives

If there were any alternative solutions to solving the same problem,
they should be discussed here, along with a justification for the
chosen approach.


## Discussion

This section should have links related to any discussion regarding the
ZEP. It could be GitHub issues and/or discussions. (The links to
discussions in past if any, goes in this section.)


## References and Footnotes

* <a name="ref-ZARR2SPEC"></a> [ZARR2SPEC] -
  https://zarr.readthedocs.io/en/stable/spec/v2.html


## License

<p xmlns:dct="http://purl.org/dc/terms/">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="https://licensebuttons.net/p/zero/1.0/80x15.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="https://github.com/zarr-developers/zeps">
    <span property="dct:title">the authors</span></a>
  have waived all copyright and related or neighboring rights to
  <span property="dct:title">ZEP 1</span>.
</p>
