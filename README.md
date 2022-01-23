# Routinator-Local-Exceptions-SLURM
When deploying Routinator for RPKI/ROV validation, you may want to whitelist certain prefixes, such as prefixes from private ASN eBGP customers.

Unfortunately, the Routinator docs and RFC 8416 docs are pretty hard to understand.

Here is a practical example of an exceptions file that works well in production.

We have placed the file in the /var/lib/routinator directory, and changes the user/group owner of the file (chmod / chgrp) to "routinator"

This simple config will allow X prefix from Y ASN. You can verify that this is working by enabling the Routinator webui in /etc/routinator/routinator.conf

You must also add your exceptions file to your config file:
exceptions = "/var/lib/routinator/rpki-exceptions.json
