# Environmental Variables
This is a list of available environmental variables organized by component.
*(Allowed values have been provided, but are none are set as actual defaults)*

## install.sh

| Env Variable Name    | Description                                       | Example Value  |
| :------------------: | :------------------------------------------------ | :------------- |
| $INSTALL_SYMLINK     | Installed files are symlinked instead of copied   | *(any nonblank)* |
| $INSTALL_BIN_DIR     | Executables copied/linked to this directory       | /usr/local/bin |
| $INSTALL_NO_CLOBBER  | Do not overwrite already installed files          | *(any nonblank)* |
| $INSTALL_NO_MODULES  | Do not persist modules to be probed at startup    | *(any nonblank)* |
| $INSTALL_EXCLUDE     | Comma separated list of components not to install | set-cpupower   |
|                      |                                                   | fanspeed       |
| :------------------: | :------------------------------------------------ | :------------- |
