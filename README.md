coreserv-ws
===========

This is the SCAL/UX Core System Management Services workspace. It is the tree
from which the following components are built:

- SCAL/UX System Notification Bus
- SCAL/UX System Configuration Store
- SCAL/UX Local Service Manager

These tools implement system and service management for NetaScale SCAL/UX,
but additionally runs on the following operating system/compiler pairs:

- IBM AIX 5.1L+
- HP-UX 11.11+
- FreeBSD 7.0+
- GNU with HURD 0.9+
- GNU with kFreeBSD 7.0+
- GNU with kNetBSD 7.0+
- GNU with kIllumos 2010+
- GNU with Linux 2.6+
- OpenBSD 4.0+
- NetBSD 5.0+
- OS X 10.4+

Other UNIX-like operating systems may work but are untested. *GNU CC* and
*Apple LLVM/Clang* are supported compilers for all the above platforms for which
they are available. HP *aC++* is supported on HP-UX.

SCAL/UX Core System Management Services is available as free, open-source
software under the terms of the Creative Commons
Attribution-NonCommercial-ShareAlike 3.0 Licence.

NetaScale will license this software under alternative terms (permitting
commercial use) to
social and not-for-profit concerns on request.


Building
--------

The following build-time dependencies exist:

- GNU Make
- `rpcgen`
  - Provided by e.g. `rpcgen` package on Red Hat Linux.
- (on GNU with Linux) libtirpc

GNU AutoConf 2.13 is automatically used to assist in configuration, and the
workspace is built with GNU Make. Only `make` need be run to configure and build
the software; `configure` will be invoked automatically.

- You can optionally specify options to the ./configure script by calling Make
  with configure options stored in the environment variable $WS_configureOptions,
  or by explicitly passing them to Make:

    `env WS_configureOptions="--prefix=/usr" make`

    `make WS_configureOptions="--prefix=/usr"`

- If you will change the configuration options, you must invoke the
*reconfigure* target, e.g. by:

  `make Ws_configureOptions="--prefix=/usr/pkg" reconfigure

If you edit `configure.in` then AutoConf will be automatically called to
regenerate the configure script on the next invocation of Make.
Make sure that the first `m4` in your path will be GNU M4, version 1.1 or later.
