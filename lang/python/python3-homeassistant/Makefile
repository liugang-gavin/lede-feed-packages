#
# Copyright (C) 2014-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-homeassistant
PKG_VERSION:=0.49.0
PKG_RELEASE:=1

PKG_SOURCE:=homeassistant-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/79/e1/674c18d13deefd0a5355bbb59bf38e78721d9e9915b8df7e04b2cfd9839f
PKG_MD5SUM:=6928adbd4b8d00a1b17583328edd9edd

PKG_LICENSE:=Apache License 2.0

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-homeassistant-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)
PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-homeassistant
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Open-source home automation platform
	URL:=https://home-assistant.io/
	DEPENDS:=+python3 +python3-dev
	MAINTAINER:=Guo Feng <feng.guo@nxp.com>
endef

define Package/python3-homeassistant/description
	Open-source home automation platform running on Python 3.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
		--single-version-externally-managed \
	)
endef

define Py3Package/python3-homeassistant/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/hass $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-homeassistant))
$(eval $(call BuildPackage,python3-homeassistant))
