include $(TOPDIR)/rules.mk

PKG_NAME:=glorytun
PKG_VERSION:=0.1.1
PKG_RELEASE:=0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/angt/$(PKG_NAME)/releases/download/v$(PKG_VERSION)
PKG_HASH:=d67a5765fb4d6c43a2e0e3e83887cd036568bbf76f65df9f1561dc82a08800b9

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=VPN
  TITLE:=Glorytun
  DEPENDS:=+kmod-tun +libsodium +librt
  URL:=https://github.com/angt/glorytun
endef

TARGET_CPPFLAGS += -DGT_RUNDIR=\\\"/var/run/$(PKG_NAME)\\\"

define Package/$(PKG_NAME)/description
  Glorytun is a vpn designed to improve your internet connectivity:
    - Fast and highly secure.
    - Multipath and active failover.
    - Traffic shaping.
    - Path MTU discovery without ICMP.
endef

define Package/$(PKG_NAME)/conffiles
/etc/config/$(PKG_NAME)
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) init $(1)/etc/init.d/$(PKG_NAME)
	$(INSTALL_DIR) $(1)/etc/config
	touch $(1)/etc/config/$(PKG_NAME)
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
