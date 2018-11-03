# Binaries for shell scripts from YourFritz repository

This repository contains pre-compiled binaries (for different platforms), that are needed for some scripts from the YourFritz repository.

All of them are built with my fork of the Freetz project, which may be found on GitHub, too.

They are separated now from the other repository, to keep checkouts as small as possible.

This repository has been integrated into the original one as `bin` sub-directory and has to be updated after the first checkout with the command:

```shell
git submodule update --init --remote --force bin
```

In the future you may refresh the content of your `bin` sub-directory (if necessary) with the command from above.

## Tree structure

```text
/                                              - license, README.md, PGP public key, other info
|
+- squashfs -+-                                - shell scripts to detect the needed architecture of SquashFS binaries and to call them
|            |
|            +- armv7l                         - unpack/pack binaries for ARMv7 (LE) architecture (e.g. Raspberry Pi)
|            |
|            +- i686                           - unpack/pack binaries for Intel 80386 architecture (nearly each Intel or AMD processor with 32-bit support)
|            |
|            +- mips                           - unpack/pack binaries for MIPS32r2 (BE) architecture (most FRITZ!Box devices with Lantiq/Intel or Ikanos processor)
|            |
|            +- x86_64                         - unpack/pack binaries for Intel-compatible 64-bit architecture
|
-- target ---+- mips ---+- 3.10.73             - precompiled binaries for MIPS-based devices with 3.10.73 kernel (up to FRITZ!OS version 07.0x)
             |          |
             |          +- 3.10.107 / 3.10.104 - precompiled binaries for MIPS-based devices with 3.10.10x kernel (starts with FRITZ!OS 07.0x)
             |
             +- i686                           - precompiled binaries for PUMA6-based devices (only for their ATOM)
```

The binaries for target devices are (usually) linked statically, to make them usable without any further prerequisites. For MIPS architectures there're two different branches, because AVM starts to use the uClibc-ng instead of the older uClibc (0.9.3x) from FRITZ!OS version 07.0x on.

The binaries for SquashFS handling are linked statically only for the MIPS architecture, all other architectures need the correct libraries (glibc (or a compatible one) and libz), too.