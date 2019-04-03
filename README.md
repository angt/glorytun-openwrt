# glorytun-openwrt

Glorytun package for OpenWrt

**You need an OpenWrt version with libsodium >= 1.0.4.**

Add this line in your `feeds.conf.default`:

    src-git glorytun https://github.com/angt/glorytun-openwrt.git

Or install in `package`:

    $ git clone https://github.com/angt/glorytun-openwrt.git
    $ cp -rf glorytun-openwrt/glorytun package

Update and install your feeds:

    $ ./scripts/feeds update -a
    $ ./scripts/feeds install -a

Configure and build:

    $ make defconfig
    $ make menuconfig
    $ make
