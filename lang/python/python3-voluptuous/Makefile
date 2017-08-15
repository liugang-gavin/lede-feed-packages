#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-voluptuous
PKG_VERSION:=0.10.5
PKG_RELEASE:=1
PKG_LICENSE:=BSD

PKG_SOURCE:=voluptuous-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/c3/81/c84f8a3e723b760fdd1c41fc80201cb80cd29c1bce5159d8918c58df7d2a
PKG_MD5SUM:=e3fc99b75618d384cad63bc71b6507bc
PKG_BUILD_DIR:=$(BUILD_DIR)/voluptuous-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-voluptuous
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Voluptuous is a Python data validation library
  URL:=https://github.com/alecthomas/voluptuous
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-voluptuous/description
  Voluptuous, despite the name, is a Python data validation library. It is primarily intended for validating data coming into Python as JSON, YAML, etc.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-voluptuous/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-voluptuous))
$(eval $(call BuildPackage,python3-voluptuous))
