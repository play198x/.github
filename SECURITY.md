# Security policy

Play198x decodes media files of unknown provenance — tape and disk rips, tracker
modules, image dumps from thirty-year-old archives. A malformed or hostile file
must not panic, over-read, or exhaust memory in the tool opening it. That is the
realistic risk here, and a crash on a corrupt module is worth reporting.

## Reporting

Please report suspected vulnerabilities privately to **steve@stevehill.xyz**
rather than opening a public issue. Include the file that triggers it where you
can — a failing input is the fastest possible report.

This is a small project without a formal response window, but reports are read
and acted on. Once a fix ships, credit is given gladly — unless you'd rather stay
anonymous.
