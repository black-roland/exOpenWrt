# Extended OpenWrt repository

OpenWrt repository with additional and patched packages.

## Packages

#### [dnscrypt-proxy](https://dnscrypt.org/)

A tool for securing communications between a client and a DNS resolver.

#### [iodine](http://code.kryo.se/iodine/)

Tunnel IPv4 over DNS.

*Note*: Depends on **kmod-tun** package — install separately.

## Software repository for ar71xx devices

#### Trunk

    cd /tmp
    uclient-fetch 'http://exopenwrt.roland.black/exopenwrt.pub'
    opkg-key add exopenwrt.pub
    echo '/etc/opkg/keys/1a929a1dd62138c1' >> /etc/sysupgrade.conf
    echo 'src/gz exopenwrt http://exopenwrt.roland.black/snapshots/trunk/ar71xx/packages/exopenwrt' >> /etc/opkg/customfeeds.conf

#### Chaos Calmer

    cd /tmp
    wget 'http://exopenwrt.roland.black/exopenwrt.pub'
    opkg-key add exopenwrt.pub
    echo '/etc/opkg/keys/1a929a1dd62138c1' >> /etc/sysupgrade.conf
    echo 'src/gz exopenwrt http://exopenwrt.roland.black/chaos_calmer/15.05.1/ar71xx/packages/exopenwrt' >> /etc/opkg.conf

#### Barrier Breaker

    echo 'src/gz exopenwrt http://exopenwrt.roland.black/barrier_breaker/14.07/ar71xx/packages/exopenwrt' >> /etc/opkg.conf

Update list of available packages:

    $ opkg update

Install packages:

    $ opkg install dnscrypt-proxy

## Differences with OpenWrt packages

| Package        | Difference                                                                                                                                                                |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| dnscrypt-proxy | Newest version for Chaos Calmer. Barrier Breaker support. Procd support and possibility of launching multiple instances (thanks to [@spitsw](https://github.com/spitsw)). |
| libsodium      | Newest version for Chaos Calmer. Barrier Breaker support.                                                                                                                 |
| iodine         | Memory usage reduce patch. Info: https://github.com/yarrick/iodine#tips--tricks                                                                                           |
