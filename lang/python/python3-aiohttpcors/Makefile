#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-aiohttpcors
PKG_VERSION:=0.5.3
PKG_RELEASE:=1
PKG_LICENSE:=Apache License, Version 2.0

PKG_SOURCE:=aiohttp-cors-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/33/3c/bcbe3996731ccc8ca3e2db6ca717ba03294a650b3ce5dd4bcc1db9b33632
PKG_MD5SUM:=0594dd4f5148405a13b5b703325244a9
PKG_BUILD_DIR:=$(BUILD_DIR)/aiohttp-cors-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-aiohttpcors
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=CORS support for aiohttp
  URL:=https://github.com/aio-libs/aiohttp-cors
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-aiohttpcors/description
  CORS support for aiohttp
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-aiohttpcors/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-aiohttpcors))
$(eval $(call BuildPackage,python3-aiohttpcors))
