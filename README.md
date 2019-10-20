# glorytun-openwrt

Glorytun package for OpenWrt

**You need an OpenWrt version with libsodium >= 1.0.4.**

Add this line in your `feeds.conf.default`:

    src-git glorytun https://github.com/angt/glorytun-openwrt.git

Update and install your feeds:

    $ ./scripts/feeds update -a
    $ ./scripts/feeds install -a

Configure and build:

    $ make defconfig
    $ make menuconfig
    $ make
