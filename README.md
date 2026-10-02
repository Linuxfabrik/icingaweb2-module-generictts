<h1 align="center">
  <a href="https://linuxfabrik.ch" target="_blank">Linuxfabrik</a> Icinga Web 2 GenericTTS Module
</h1>
<p align="center">
  Turns ticket references in Icinga acknowledgements, downtimes and comments into links to your trouble ticket system.
  <span>&#8226;</span>
  <b>maintained by <a href="https://linuxfabrik.ch/">Linuxfabrik</a></b>
</p>
<div align="center" markdown>

![GitHub Stars](https://img.shields.io/github/stars/linuxfabrik/icingaweb2-module-generictts)
![License](https://img.shields.io/github/license/linuxfabrik/icingaweb2-module-generictts)
![Version](https://img.shields.io/github/v/tag/linuxfabrik/icingaweb2-module-generictts?sort=semver)
![GitHub Issues](https://img.shields.io/github/issues/linuxfabrik/icingaweb2-module-generictts)
[![OpenSSF Scorecard](https://api.scorecard.dev/projects/github.com/Linuxfabrik/icingaweb2-module-generictts/badge)](https://scorecard.dev/viewer/?uri=github.com/Linuxfabrik/icingaweb2-module-generictts)
[![GitHubSponsors](https://img.shields.io/github/sponsors/Linuxfabrik?label=GitHub%20Sponsors)](https://github.com/sponsors/Linuxfabrik)
[![PayPal](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7AW3VVX62TR4A&source=url)

</div>

<br />


# Icinga Web GenericTTS Integration

With the Icinga Web GenericTTS integration, you can replace ticket patterns in acknowledgements, downtimes, and comments with links to your trouble ticket systems. To do this, you configure one or more unique regular expressions to link to them.

The module was created by Icinga, who handed its maintenance over to Linuxfabrik. This repository is its home.


## Installation

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

Ansible users can deploy the module with the `linuxfabrik.lfops.icingaweb2_module_generictts` role from [LFOps](https://github.com/Linuxfabrik/lfops).


## Documentation

* [About](doc/01-About.md)
* [Installation](doc/02-Installation.md)
* [Configuration](doc/03-Configuration.md)


## Reporting Issues

1. [Submit an issue](https://github.com/Linuxfabrik/icingaweb2-module-generictts/issues/new/choose) (preferred).
2. [Contact us](https://www.linuxfabrik.ch/en/contact) by email or web form and describe your problem.

For vulnerabilities, follow the private disclosure process in [SECURITY.md](SECURITY.md).


## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.


## License

Icinga Web GenericTTS Integration and the Icinga Web GenericTTS Integration documentation are licensed under the terms of the [GNU General Public License Version 2](LICENSE).


## Support the Project

Enterprise support, including an SLA, is available via a [Service Contract](https://www.linuxfabrik.ch/en/products/service-support).

If this project helps you, consider a donation via
[GitHub Sponsors](https://github.com/sponsors/Linuxfabrik) or
[PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7AW3VVX62TR4A&source=url).

There is no fixed roadmap. Milestones are driven by customer needs and by contributors' time.
