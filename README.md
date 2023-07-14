# BlackHole-BL  
Simple tool to handle blackhole file black lists that can remove comments, remove duplicates, compress to 9 domains per line, add IPv6 entries, as well as can convert black lists to multiple other black list formats compatible with other software.

Usage: `blackhole-bl [options...] <source> <destination>`

Argument                  | Description
--------------------------|-----------------------------------------------------------------------------------------------------
 `-comments`              | Don't remove comments
 `-compression <number>`  | Number of domains per line, 1 to 9
 `-dupe`                  | Don't check for and remove duplicates
 `-f <format>`            | Destination format:
--------------------------| **adblock, dnsmasq, dualserver, fqdn,**
--------------------------| **blackhole, ipv6, privoxy, rfqdn, rpz, unbound**
 `-from_blackhole <IPv4>` | Black hole address in source
 `-i <file>`              | Source file
 `-o <file>`              | Destination file
 `-to_blackhole <IPv4>`   | Black hole address in destination
 `-to_blackhole_v6 <IPv6>`| IPv6 Black hole address in destination

`-` can be used in place of `<file>` to designate standard input as the source and/or standard output as the destination. If standard input is used, standard output will be used by default if no destination file is given.

By default, dragging and dropping a blackhole file over a blackhole-bl executable will automatically pick out lines beginning with `0.0.0.0`, check for and remove any duplicates, and compress it to 9 domains per line in standard blackhole file format with `0.0.0.0` as the black hole address.

In addition to removing duplicates by default, formats which support wild cards will automatically have wild card entries added and all child subdomains will be pruned from the list.
