## support

### Haskell compiler

supported Haskell GHC 8.0.x, 8.2.x, 8.4.x, 8.6.x:

* GHC 8.0 (May 2016)
* GHC 8.2 (Jul 2017)
* GHC 8.4 (Mar 2018)
* GHC 8.6 (Aug 2018)

Not supported anymore:

* GHC 7.10 (Apr 2015)
* GHC 7.8 (Apr 2014)
* Older GHCs

Libraries can be effectively gated against older GHCs using
in .cabal file:

```
if impl(ghc < 8.0)
  Buildable: False
else
  build-depends: base
```

or in hpack format:

```
when:
  - condition: "impl(ghc < 8.0)"
    then:
      buildable: False
    else:
      dependencies: base
```

### Operating system

Package SHOULD be operating system independent if possible.

supported:

* Windows:
  * 8 (Aug 2012), 8.1
  * 10 (July 2015)
* Mac OS:
  * 10.10 Yosemite (Jun 2014)
  * 10.11 El Capitan (Jun 2015)
  * 10.12 Sierra (Jun 2016)
  * 10.13 High Sierra (Jun 2017)
* Linux
* BSDs (FreeBSD, NetBSD, OpenBSD)

Not supported anymore:

* Windows Vista (2007, support ended)
* Windows 7 (2009, support ended)
* Older Windows
* Mac OS 10.9 (Jun 2013) and older
* Old Linuxes (TODO: define a cutoff)
* Old BSDs (TODO: define a cutoff)

### Architecture

Package SHOULD be architecture independent if possible.

Package MUST support:

* 64 bits X86-64

Package COULD also support:

* 32 bit i386
* 32/64 bit ARM

Any other architecture is unsupported, but will possibly work
with architecture independent code.

### Missing support & Rationale

In an ideal situation, supporting everything would be nice. However
the support cost has a non-negligeable cost in term of the either

* The source code cleanness
* Time to test complex matrix of differents versions
* Time to add compatibility fixes
* Time to have broad availability of a latest feature

So, the list of supported combinaison will not only be trimmed down
as new combinaisons are added, but old combinaisons will be actively removed so that
compatibility and other workaround are cleaned up and package stay maintainable.
