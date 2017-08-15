#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-netdisco
PKG_VERSION:=1.0.1
PKG_RELEASE:=1
PKG_LICENSE:=Apache License 2.0

PKG_SOURCE:=netdisco-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/db/f5/98d7943392759e31eff56f697b55820da46ed146d1f5355c4a1950300a73
PKG_MD5SUM:=50bfe6900b7b9270a3cb28b6a841c5f5
PKG_BUILD_DIR:=$(BUILD_DIR)/netdisco-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-netdisco
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Discover devices on your local network
  URL:=https://github.com/home-assistant/netdisco
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-netdisco/description
  Discover devices on your local network
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-netdisco/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-netdisco))
$(eval $(call BuildPackage,python3-netdisco))
