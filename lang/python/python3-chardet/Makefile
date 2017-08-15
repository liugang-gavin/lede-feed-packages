#
# Copyright (C) 2014-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-chardet
PKG_VERSION:=3.0.4
PKG_RELEASE:=1

PKG_SOURCE:=chardet-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/fc/bb/a5768c230f9ddb03acc9ef3f0d4a3cf93462473795d18e9535498c8f929d
PKG_MD5SUM:=7dd1ba7f9c77e32351b0a0cfacf4055c

PKG_LICENSE:=LGPL

PKG_BUILD_DIR:=$(BUILD_DIR)/chardet-$(PKG_VERSION)
PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-chardet
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Universal encoding detector for Python 2 and 3.
	URL:=https://github.com/chardet/chardet
	DEPENDS:=+python3 +python3-dev
	MAINTAINER:=Guo Feng <feng.guo@nxp.com>
endef

define Package/python3-chardet/description
	Universal encoding detector for Python 2 and 3
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
		--single-version-externally-managed \
	)
endef

define Py3Package/python3-chardet/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-chardet))
$(eval $(call BuildPackage,python3-chardet))
