duffer.hs
=========
[![Build Status](https://travis-ci.org/vaibhavsagar/duffer.hs.svg?branch=master)](https://travis-ci.org/vaibhavsagar/duffer.hs)

This is a learning exercise and an API for `git`, in that order. Please do not
use this code in production. Instead I would recommend Vincent Hanquez's
excellent and very educational [hs-git](https://github.com/vincenthz/hs-git/).

# What this library does

- Reads and writes loose blobs, trees, commits, and tags.
- Reads full indexed packfiles.
- Reads and writes git refs.

# Some things this library does not do

- Generate a packfile index from a packfile.
- Read a streamed packfile.
- Support arbitrary backends besides file storage.
- Read .git/index
- Generate human readable diffs.
- Provide Functor, Aplicative, or Monad instances for a repository.

# Goals

Although this is primarily a way for me to learn both Haskell and `git` at the
same time, there a couple of (I think) cool things I would like to do with this
library:

- Use `git` as a NoSQL store, i.e. using `git` data formats to persist data for
  an application. [Irmin]() is exactly this for OCaml but I don't know of an
  equivalent in Haskell. This means eventually supporting pluggable backends
  like Irmin and `libgit2` so that you're not limited to a filesystem backend.
- A GraphQL/other query language interface to a `git` repository's commits. If
  commits form a beautiful acyclic directed graph, surely there is a better way
  of querying them than `git log`.