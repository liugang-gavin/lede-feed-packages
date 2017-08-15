#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-zeroconf
PKG_VERSION:=0.19.1
PKG_RELEASE:=1
PKG_LICENSE:=LGPL

PKG_SOURCE:=zeroconf-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/bf/e3/acc6e2c2938428afa2450143fc4d3953ec60cb4d859db3a58f03d149ef04
PKG_MD5SUM:=12d4cb1eef96c38cd8760a68a83809d4
PKG_BUILD_DIR:=$(BUILD_DIR)/zeroconf-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-zeroconf
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Multicast DNS Service Discovery Library
  URL:=https://github.com/jstasiak/python-zeroconf
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-zeroconf/description
  This is fork of pyzeroconf, Multicast DNS Service Discovery for Python
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-netifaces/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-zeroconf))
$(eval $(call BuildPackage,python3-zeroconf))
