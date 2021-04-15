# cputools
Scripts for managing CPU frequency and fan speeds (mostly for CPU cryptocurrency mining)

## set-cpupower
The `set-cpupower` script uses the `cpupower` binary (included in the debian package `linux-tools-generic`) to set the minimum, maximum, and governor for 2 numa node cpus.

The values can be included directly into the script. If a config file (`/etc/set-cpupower.conf`) exists, it will be sourced after the hardcoded values, overwritting the defaults.
