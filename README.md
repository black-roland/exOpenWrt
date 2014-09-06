# Extended OpenWrt repository #
OpenWrt repository with additional and custom packages.

## Packages ##
[**dnscrypt-proxy**](http://dnscrypt.org/) — A tool for securing communications between a client and a DNS resolver.

[**iodine**](http://code.kryo.se/iodine/) — Tunnel IPv4 over DNS. Added patch to reduce memory consumption. Depends on *kmod-tun* — install separately.

## Software repository for ar71xx devices ##
Add third-party source to your opkg configuration file */etc/opkg.conf*:

**trunk**

    src/gz exopenwrt http://exopenwrt.and.in.net/trunk/ar71xx/packages/exOpenWrt

**Attitude Adjustment**

    src/gz exopenwrt http://exopenwrt.and.in.net/attitude_adjustment/ar71xx/packages

And update list of available packages:

    $ opkg update

For example, install dnscrypt-proxy:

    $ opkg install dnscrypt-proxy
