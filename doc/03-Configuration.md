# Configuration

After enabling `generictts`, configure it in Icinga Web under Configuration > Modules > generictts > TTS Integrations. The module stores its configuration in:

```
/etc/icingaweb2/modules/generictts/config.ini
```

The file can also be edited directly. Each section describes one ticket system:

`pattern`

* A PHP regular expression ([PCRE](https://www.php.net/manual/en/reference.pcre.pattern.syntax.php)) including its delimiters, for example `/#([0-9]+)/`. The first capturing group holds the ticket reference.

`url`

* The link target. `$1` is replaced with the URL-encoded content of the first capturing group.

A section without a `url` or without a `pattern` is ignored. The link text is the complete match, so `#4711` stays `#4711`, just clickable.


## Example Configuration

Every acknowledgement, downtime or comment that contains a hash `#` followed by four to six digits gets a link to that ticket:

```ini
[my-ticket-system]
pattern = "/#([0-9]{4,6})/"
url = "https://tickets.example.com/view.php?id=$1"
```

Quantifiers are written with a comma: `{4,6}` means four to six digits, `{4-6}` does not match anything useful.


## More Examples

Jira and OTRS:

```ini
[jira]
pattern = "/([A-Z]+-[0-9]{1,9})/i"
url = "https://jira.example.com/browse/$1"

[otrs]
pattern = "/#([0-9]{1,9})/"
url = "https://otrs.example.com/otrs/index.pl?Action=AgentTicketSearch&Subaction=Search&TicketNumber=$1"
```
