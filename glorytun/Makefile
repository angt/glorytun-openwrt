include $(TOPDIR)/rules.mk

PKG_NAME:=glorytun
PKG_VERSION:=0.0.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/angt/glorytun/releases/download/v$(PKG_VERSION)
PKG_MD5SUM:=8535648ac8c5d075a0a7e7c4a13419f3

PKG_INSTALL:=1
PKG_FIXUP:=autoreconf

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

TARGET_CFLAGS += -std=c99

define Package/glorytun/install
	$(INSTALL_DIR) $(1)/usr/sbin
endef

$(eval $(call BuildPackage,glorytun))