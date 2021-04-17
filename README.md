# cputools
Scripts for managing CPU frequency and fan speeds.
*(Mostly for high intensity CPU computing/cryptocurrency mining)*

## Installing
The `install.sh` script runs interactively by default and will prompt for values
that could not be resolved. Values can be passed in several ways and are given
the following order of precedence (with later methods overwriting earlier ones).
  1. Hardcoded script variables in the head of [./install.sh](`install.sh`)
  2. Varibles sourced from [./install.config](`install.config`)
  3. Environmental variables (see [doc/ENV.md#install.sh](ENV.md) for a list)
  4. Arguments passed to the script (see [doc/INSTALL.md#arguments](INSTALL.md) for usage)

 or automatically to configure
all the components, copy them to the correct paths, and enable their
corresponding systemd.service directives.

## Components
### [set-cpupower/README.md](set-cpupower)
The `set-cpupower` script uses the `cpupower` binary (included in the debian
package `linux-tools-generic`) to set the minimum, maximum, and governor for 2
numa nodes with many cores..

The values can be included directly into the script.
If a config file (`/etc/set-cpupower.conf`) exists, it will be sourced after
the hardcoded values, overwritting the defaults.

**MAKE SURE YOU EDIT THESE VARIABLES TO CONFORM TO YOUR CPU BEFORE RUNNING THE SCRIPT DUMMY!**

### fanspeed
The `fanspeed` scripts uses the `ipmitool` binary (included in the debian
package `ipmitool`) so pin the PWM fans at an optimal level for thermal and/or
accoustic performance.
