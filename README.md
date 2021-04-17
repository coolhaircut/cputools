# **cputools**
Scripts for managing CPU frequency and fan speeds
in high intensity, multiple core CPU machine learning
and/or mining ASIC-resistant cryptocurrencies (specifically
[Monero](doc/CPU_MINING.md#xmr "Monero (XMR)") and other
[RandomX](https://github.com/tevador/RandomX) PoW coins.

## Installing
The *[install.sh](install.sh)* script can:
  * install required dependencies
  * probe and persist necessary modules
  * configure the individual components
  * copy/link them to the correct paths
  * generate systemd startup service

### Run Modes
If all required values are provided and the `FORCE_INTERACTIVE`
is not set, the script will run non-interactively.
Otherwise it will prompt for values that could not be resolved.

### Customizing Installation
These values can be passed in several ways (with later methods overwriting earlier ones). Presecedence order for methods is as follows:
  1. Hardcoded script variables in the head of *[install.sh](install.sh)*
  2. Varibles sourced from *[install.config](install.config)*
  3. Environmental variables (see [ENV.md](doc/ENV.md#install.sh) for a list)
  4. Arguments passed to the script (see [INSTALL.md](doc/INSTALL.md#arguments) for usage)


## Components
### set-cpupower](doc/SET_CPUPOWER)
The **set-cpupower** script depends on the `cpupower`
binary to set the minimum, maximum, and governor for
individual cpu cores and numa nodes.

The values can be included directly into the script.
If a config file *[set-cpupower.conf](/etc/set-cpupower.conf)*
exists, it will be sourced after the hardcoded values, overwritting the defaults.

> **MAKE SURE YOU EDIT THESE VARIABLES BEFORE RUNNING THE SCRIPT, DUMMY!**

### fanspeed
The **fanspeed** scripts uses the `ipmitool` binary
to pin the PWM fans at an optimal level for thermal and/or
accoustic performance.

## References
  * [1](https://github.com/tevador/RandomX)
