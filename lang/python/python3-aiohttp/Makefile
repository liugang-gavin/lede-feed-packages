#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-aiohttp
PKG_VERSION:=2.2.3
PKG_RELEASE:=1
PKG_LICENSE:=Apache 2

PKG_SOURCE:=aiohttp-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/9b/3a/b560a411b97203fb20b5eee084c1e292862b3092029d9d9faaa8714797fa
PKG_MD5SUM:=7793829c8c2fed46f798e9c75bb68869
PKG_BUILD_DIR:=$(BUILD_DIR)/aiohttp-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-aiohttp
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Async http client/server framework
  URL:=https://github.com/aio-libs/aiohttp/
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-aiohttp/description
  Async http client/server framework (asyncio).
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
		--single-version-externally-managed \
	)
endef

define Py3Package/python3-aiohttp/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-aiohttp))
$(eval $(call BuildPackage,python3-aiohttp))
