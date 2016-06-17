# archive-format

[![](https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat-square)](http://ipn.io)
[![](https://img.shields.io/badge/project-IPFS-blue.svg?style=flat-square)](http://ipfs.io/)
[![](https://img.shields.io/badge/freenode-%23ipfs-blue.svg?style=flat-square)](http://webchat.freenode.net/?channels=%23ipfs)
[![](https://img.shields.io/badge/discussion_repo-go_to_issues-brightgreen.svg?style=flat-square)](https://github.com/ipfs/archive-format/issues)

> car - Certified ARchives -- WIP

**(WIP -- quick thought dump)**

> A car for your data!

`car` is an archive format, like [`tar`](https://en.wikipedia.org/wiki/Tar_(computing)). It is designed to improve upon some deficiencies in `tar` as well as add fundamental improvements. The deatils of `car` are still being worked on, but the design space is already well scoped. `car` is a synthesis of good ideas. Many other archive formats introduced some of its improvements. `car` is different as it was introduced mainly to work with [IPFS](https://ipfs.io) and related protocols, like [IPLD](https://github.com/ipfs/specs/tree/master/merkledag/ipld.md). But `car` is useful beyond IPFS.

This is a **discussion repo**. That means that all of the work gets done in the [issues](https://github.com/ipfs/apps/issues).

## Table of Contents

- [File System Improvements:](#file-system-improvements)
- [Fundamentally New Features:](#fundamentally-new-features)
- [Whishlist:](#whishlist)
- [Related Work:](#related-work)
- [Contribute](#contribute)
  - [Want to hack on IPFS?](#want-to-hack-on-ipfs)
- [License](#license)

## File System Improvements:

- **Seeking Optimized:** finding object within a `car` file should be easy and fast. We can do this via an index with in-file byte offsets.
- **[UNIX/POSIX files]():** full unix + posix files compliance.
- **[Extended Attributes](https://en.wikipedia.org/wiki/Extended_file_attributes):** support for xattrs and other extensions.
- **Compression Optimized:** support for object-level and archive-level compression. Modular to support new compression protocols.
- **Encryption Optimized:** support for object-level and archive-level encryption (through [AEADs](https://en.wikipedia.org/wiki/Authenticated_encryption) / [NaCl/Box](https://godoc.org/golang.org/x/crypto/nacl/box))

## Fundamentally New Features: 

- **[Data Structures](https://github.com/ipfs/specs/tree/master/merkledag/ipld.md):** support for archiving more than files-- arbitrary datastructures (first-class JSON, XML, IPLD support)
- **[Merkle-Linked](https://github.com/ipfs/specs/tree/master/merkledag/ipld.md):** all objects in a `car` file are merkle-linked -- hash-linked -- together. this means the whole `car` file is a [merkle-dag](https://en.wikipedia.org/wiki/Merkle_tree).
- **[Digital Signatures](https://en.wikipedia.org/wiki/Digital_signature):** `car` has first-class support for Digital Signatures, to verify the authorship and certification of its content.

## Whishlist:

- **[Repo Friendliness](https://github.com/jbenet/random-ideas/issues/33):** make it _easy, efficient, and useful_ to use `car` archives as on-disk repositories for other tools.
- **[Authenticated Datastructures](https://www.cs.umd.edu/~mwh/papers/gpads.pdf):** define all `car` operations as an authenticated datastructure, to have secure, untrusted computing. Merkle-linking and Digital Signatures get us most of the way there.

## Related Work:

- continuity: https://github.com/stevvooe/continuity
- `asar`: https://github.com/atom/asar
- IPFS: https://github.com/ipfs/ipfs
- IPLD: https://github.com/ipfs/specs/tree/master/merkledag/ipld.md
- ipfs/unixfs: https://github.com/ipfs/go-ipfs/tree/master/unixfs
- lambda-auth: http://amiller.github.io/lambda-auth/

## Contribute

Feel free to join in. All welcome.

### Want to hack on IPFS?

[![](https://cdn.rawgit.com/jbenet/contribute-ipfs-gif/master/img/contribute.gif)](https://github.com/ipfs/community/blob/master/contributing.md)

## License

MIT
