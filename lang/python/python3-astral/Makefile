#
# Copyright (C) 2014-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-astral
PKG_VERSION:=1.4
PKG_RELEASE:=1

PKG_SOURCE:=astral-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://pypi.python.org/packages/a4/d6/c309f266677372964c6002a56a7bec2a90875338a71325e20b24d6d1e187
PKG_MD5SUM:=140499d213a234cb216e6b7fe36ee3c7

PKG_LICENSE:=Apache License 2.0

PKG_BUILD_DIR:=$(BUILD_DIR)/astral-$(PKG_VERSION)
PKG_USE_MIPS16:=0
PKG_BUILD_DEPENDS:=python3-pytz python3-pytz/host

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-astral
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Calculations for the position of the sun and moon.
	URL:=https://github.com/sffjunkie/astral
	DEPENDS:=+python3 +python3-dev +python3-pytz
	MAINTAINER:=Guo Feng <feng.guo@nxp.com>
endef

define Package/python3-astral/description
	Calculations for the position of the sun and moon.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
		--single-version-externally-managed \
	)
endef

define Py3Package/python3-astral/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-astral))
$(eval $(call BuildPackage,python3-astral))
