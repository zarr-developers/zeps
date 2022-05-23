# ZEP 1 - Zarr version 3

Author: Alistair Miles <alistair.miles@sanger.ac.uk>

Status: Draft

Type: Specification

Created: 2022-05-23


## Abstract

This ZEP proposes a new major version of the core specification which
defines how to store and retrieve Zarr data. The ZEP also proposes a
new framework for modularising specifications of codecs, storage
systems and extensions.


## Motivation and Scope

Zarr version 2 [[ZARR2SPEC](#ref-ZARR2SPEC)] has been widely adopted and
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
  with full interoperobility across major programming languages.

* **Extensibility**. Zarr is increasingly being used for storage of
  very large and keystone scientific datasets. If this trend
  continues, interoperability and stability of the Zarr ecosystem will
  be vital, to allow these datasets to be utilised to their full
  potential. At the same time, large-scale array data storage is a
  very active area of innovation, and there remain many opportunities
  to improve performance, scalability and resilience for I/O-bound
  high-performance distributed computing. To balance these demands for
  stability and innovation, some framework for community exploration
  and development of Zarr extensions is needed, so that innovation can
  happen in a coordinated way with predictable consequences and
  behaviour of implementations which may not support all extensions.

* **High-latency storage**. Zarr version 2 was originally developed to
  support local file system storage only. Because of this, the design
  of Zarr version 2 implicitly made assumptions about the performance
  characteristics of the underlying storage technology, such as low
  latency for storage operations to list directories and retrieve
  small files. Fortunately, certain features of Zarr 2 still enabled
  other storage systems to be used, such as cloud object stores, and
  this ability to utilise a variety of different underlying storage
  systems has been very valuable across a range of use cases. However,
  performance of certain operations can degrade significantly with
  some storage technologies, particularly systems with relatively high
  latency per operation, such as cloud object stores. This limitation
  has been worked around through the use of consolidated metadata, but
  this workaround introduces other limitations, such as additional
  complexity when adding or modifying data.

* **Storage layout flexibility**. Zarr version 2 adopts a simple
  storage model where each chunk is encoded and then written to a
  single storage object. This simplicity makes implementation easier,
  but presents some practical challenges. For example, for large
  datasets this can generate a very large number of storage objects,
  which does not work well for certain storage systems. Also, this
  forces one retrieval operation per chunk, which can be suboptimal
  where there are many chunks that are often read together, and/or
  where different access patterns need to be accommodated.

These limitations have motivated the proposal described here to define
a new major version of the Zarr core specification, together with a
new modular specification framework.

Normally, it is better to introduce changes in small pieces, allowing
each to be evaluated and discussed in isolation. However, addressing
the limitations described above could not be done without introducing
backwards-incompatible changes into the core specification, and thus
multiple such changes are combined here, in an attempt to minimise the
overall disruption to the ecosystem and the community.


## Usage and Impact

This ZEP and the associated specifications have the following intended
outcomes:

1. Facilitate implementation of a core specification with feature
   parity and full interoperability across all major programming
   languages.

2. Accelerate innovation by facilitating the exploration, development,
   implementation and evaluation of Zarr systems with support for
   novel encoding technologies, storage technologies and features by a
   broader community.

3. Ensure reasonable performance characteristics of all Zarr
   implementations across a variety of different underlying storage
   technologies, including storage with high latency per operation.

4. Improve the performance characteristics of Zarr implementations for
   data with a very large number of chunks and/or with a variety of
   common access patterns.

Adopting this ZEP would have the following disruptive impacts on the
members of the Zarr community:

* Effort and coordination would be required to implement the
  specifications in all current Zarr software libraries and verify
  interoperability.

* Effort would be required by data producers to migrate to generating
  data conformant with the new specifications.

* Some effort may be required by users of Zarr data and/or Zarr
  software libraries to learn about and understand the differences in
  available features and/or how certain features are accessed.


## Backward Compatibility

This ZEP introduces a Zarr core specification version 3, which is
backwards-incompatible with the Zarr version 2 specification
[[ZARR2SPEC](#ref-ZARR2SPEC)].

Implementations of the Zarr version 3 core specification are not
required to be able to read or write data conforming to the Zarr
version 2 specification, and vice versa.


## Detailed description

@@TODO

This section should provide a detailed description of the proposed
change. It should include examples of how the new functionality would
be used, intended use-cases and pseudo-code illustrating its use.


## Related Work

@@TODO

This section should list relevant and/or similar technologies,
possibly in other libraries. It does not need to be comprehensive,
just list the major examples of prior and relevant art.


## Implementation

@@TODO

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

@@TODO

If there were any alternative solutions to solving the same problem,
they should be discussed here, along with a justification for the
chosen approach.


## Discussion

@@TODO

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
