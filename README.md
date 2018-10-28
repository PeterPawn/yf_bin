# Binaries for shell scripts from YourFritz repository

This repository contains pre-compiled binaries (for different platforms), that are needed for some scripts from the YourFritz repository.

All of them are built with my fork of the Freetz project, which may be found on GitHub, too.

They are separated now from the other repository, to keep checkouts as small as possible.

This repository has been integrated into the original one as `bin` sub-directory and has to be updated after the first checkout with the command:

```shell
git submodule update --init --remote --force bin
```

In the future you may refresh the content of your `bin` sub-directory (if necessary) with the command from above.
