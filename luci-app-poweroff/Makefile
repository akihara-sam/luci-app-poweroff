# Copyright (C) 2016 Openwrt.org
#
# This is free software, licensed under the Apache License, Version 2.0 .
# Maintained by eSir Playground <https://github.com/esirplayground/luci-app-poweroff>

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-poweroff
PKG_VERSION:=20200726
PKG_RELEASE:=1
LUCI_TITLE:=LuCI Support of PowerOff Router
LUCI_PKGARCH:=all

include $(TOPDIR)/feeds/luci/luci.mk

define Package/$(PKG_NAME)/conffiles
/etc/config/poweroff
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/view
	$(INSTALL_DIR) $(1)/etc/init.d

	$(INSTALL_BIN) ./luasrc/controller/*.lua $(1)/usr/lib/lua/luci/controller/
	$(INSTALL_BIN) ./luasrc/model/cbi/*.lua $(1)/usr/lib/lua/luci/model/cbi/
	$(INSTALL_BIN) ./luasrc/view/*.htm $(1)/usr/lib/lua/luci/view/
	$(INSTALL_BIN) ./init.d/poweroff $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))


# call BuildPackage - OpenWrt buildroot signature
