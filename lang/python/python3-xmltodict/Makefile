#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-xmltodict
PKG_VERSION:=0.11.0
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=xmltodict-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/57/17/a6acddc5f5993ea6eaf792b2e6c3be55e3e11f3b85206c818572585f61e1
PKG_MD5SUM:=9f955947db085485873ac68154e88069
PKG_BUILD_DIR:=$(BUILD_DIR)/xmltodict-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-xmltodict
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Makes working with XML feel like JSON
  URL:=https://github.com/martinblech/xmltodict
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-xmltodict/description
  'xmltodict' is a Python module that makes working with XML feel like you are working with
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-xmltodict/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-xmltodict))
$(eval $(call BuildPackage,python3-xmltodict))
