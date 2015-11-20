include $(TOPDIR)/rules.mk

PKG_NAME:=glorytun
PKG_VERSION:=0.0.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/angt/glorytun/releases/download/v$(PKG_VERSION)
PKG_MD5SUM:=c195d3509ae5c29c142ecc14bd39e4f2

include $(INCLUDE_DIR)/package.mk

define Package/glorytun
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=VPN
	TITLE:=Glorytun
	DEPENDS:=+kmod-tun +libsodium
	URL:=https://github.com/angt/glorytun
endef

define Package/glorytun/description
	Glorytun
endef

TARGET_CFLAGS += -std=c99 -D_GNU_SOURCE

define Package/glorytun/conffiles
/etc/config/glorytun
endef

define Build/Configure
        (cd $(PKG_BUILD_DIR); ./autogen.sh --host=$(GNU_TARGET_NAME) --target=$(GNU_TARGET_NAME); cd -);
        $(call Build/Configure/Default,$CONFIGURE_ARGS)
endef

define Package/glorytun/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/glorytun $(1)/usr/sbin
endef

$(eval $(call BuildPackage,glorytun))
