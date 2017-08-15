#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-netifaces
PKG_VERSION:=0.10.6
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=netifaces-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/72/01/ba076082628901bca750bf53b322a8ff10c1d757dc29196a8e6082711c9d
PKG_MD5SUM:=1d424cb5ef52907c5ab913011122a98b
PKG_BUILD_DIR:=$(BUILD_DIR)/netifaces-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-netifaces
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Portable network interface information
  URL:=https://bitbucket.org/al45tair/netifaces
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-netifaces/description
  Portable network interface information.
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

$(eval $(call Py3Package,python3-netifaces))
$(eval $(call BuildPackage,python3-netifaces))
