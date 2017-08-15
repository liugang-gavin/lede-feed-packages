#
# Copyright (C) 2014-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-asynctimeout
PKG_VERSION:=1.2.1
PKG_RELEASE:=1

PKG_SOURCE:=async-timeout-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/eb/a3/9fbe8bf7de4128d8f5562ca0b7b2f81d21b006085149528b937e1624e71f
PKG_MD5SUM:=e71f9b197498f917864e29af7a5defa0

PKG_LICENSE:=Apache 2

PKG_BUILD_DIR:=$(BUILD_DIR)/async-timeout-$(PKG_VERSION)
PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-asynctimeout
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Timeout context manager for asyncio programs.
	URL:=https://github.com/aio-libs/async_timeout/
	DEPENDS:=+python3 +python3-dev
	MAINTAINER:=Guo Feng <feng.guo@nxp.com>
endef

define Package/python3-asynctimeout/description
	Timeout context manager for asyncio programs.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
		--single-version-externally-managed \
	)
endef

define Py3Package/python3-asynctimeout/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-asynctimeout))
$(eval $(call BuildPackage,python3-asynctimeout))
