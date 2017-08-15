#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-distro
PKG_VERSION:=1.0.4
PKG_RELEASE:=1
PKG_LICENSE:=Apache License, Version 2.0

PKG_SOURCE:=distro-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/aa/4e/2cf3e7f67abe101c053af838f8d9b3b5911fd9360b498a1ba66a23d1ed46
PKG_MD5SUM:=1624fe57831ba50b2ecc850ff0dc86a8
PKG_BUILD_DIR:=$(BUILD_DIR)/distro-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-distro
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Linux Distribution
  URL:=https://github.com/nir0s/distro
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-distro/description
  Linux Distribution - a Linux OS platform information API
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-distro/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-distro))
$(eval $(call BuildPackage,python3-distro))
