#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-multidict
PKG_VERSION:=2.1.4
PKG_RELEASE:=1
PKG_LICENSE:=Apache 2.0

PKG_SOURCE:=multidict-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/2a/df/eaea73e46a58fd780c35ecc304ca42364fa3c1f4cd03568ed33b9d2c7547
PKG_MD5SUM:=051d92edec87fd98e43ea83f3ce6072d
PKG_BUILD_DIR:=$(BUILD_DIR)/multidict-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-multidict
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Multidict implementation
  URL:=https://github.com/aio-libs/multidict/
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-multidict/description
  Multidicts are useful for working with HTTP headers, URL query args etc.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-multidict/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-multidict))
$(eval $(call BuildPackage,python3-multidict))
