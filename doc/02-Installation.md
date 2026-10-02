# Installing Icinga Web GenericTTS Integration

[Icinga Web](https://icinga.com/docs/icinga-web/latest/) is required to run Icinga Web GenericTTS Integration. If it is not set up yet, do this first.

Icinga's package repositories carry the `icinga-generictts` package up to v2.1.0. Later releases are only published at [Linuxfabrik/icingaweb2-module-generictts](https://github.com/Linuxfabrik/icingaweb2-module-generictts), so install the module from there.


## Installing from Source

Download the release tarball into the Icinga Web modules directory, using `generictts` as the module name, and enable the module. Pick the version from the [tags](https://github.com/Linuxfabrik/icingaweb2-module-generictts/tags):

```bash
MODULE_NAME="generictts"
MODULE_VERSION="v2.1.0"
MODULE_PATH="/usr/share/icingaweb2/modules/${MODULE_NAME}"
RELEASES="https://github.com/Linuxfabrik/icingaweb2-module-${MODULE_NAME}/archive"
mkdir "$MODULE_PATH" \
&& wget --quiet --output-document=- "$RELEASES/${MODULE_VERSION}.tar.gz" \
   | tar --extract --gzip --file=- --directory="$MODULE_PATH" --strip-components=1
icingacli module enable "${MODULE_NAME}"
```

See the Icinga Web documentation on [how to install modules](https://icinga.com/docs/icinga-web/latest/doc/08-Modules/#installation) for details.


## Installing with Ansible

The `linuxfabrik.lfops.icingaweb2_module_generictts` role from [LFOps](https://github.com/Linuxfabrik/lfops) downloads and enables the module, see its [README](https://github.com/Linuxfabrik/lfops/tree/main/roles/icingaweb2_module_generictts).


## Next Steps

Configure your ticket systems as described in [Configuration](03-Configuration.md).
