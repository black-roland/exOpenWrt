# Extended OpenWrt repository
OpenWrt repository with additional and custom packages.

## Packages
[**dnscrypt-proxy**](http://dnscrypt.org/) — A tool for securing communications between a client and a DNS resolver.

[**iodine**](http://code.kryo.se/iodine/) — Tunnel IPv4 over DNS. Added patch to reduce memory consumption. Depends on *kmod-tun* — install separately.

## Software repository for ar71xx devices
**Chaos Calmer**

    cd /tmp
    wget 'http://exopenwrt.and.in.net/exopenwrt.pub'
    opkg-key add exopenwrt.pub
    echo 'src/gz exopenwrt http://exopenwrt.and.in.net/chaos_calmer/15.05-rc3/ar71xx/packages/exopenwrt' >> /etc/opkg.conf

**Barrier Breaker**

    echo 'src/gz exopenwrt http://exopenwrt.and.in.net/barrier_breaker/14.07/ar71xx/packages/exopenwrt' >> /etc/opkg.conf

Update list of available packages:

    $ opkg update

Install packages:

    $ opkg install dnscrypt-proxy
