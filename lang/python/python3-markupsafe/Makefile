#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-markupsafe
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_LICENSE:=BSD

PKG_SOURCE:=MarkupSafe-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/4d/de/32d741db316d8fdb7680822dd37001ef7a448255de9699ab4bfcbdf4172b
PKG_MD5SUM:=2fcedc9284d50e577b5192e8e3578355
PKG_BUILD_DIR:=$(BUILD_DIR)/MarkupSafe-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-markupsafe
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=A XML/HTML/XHTML Markup safe string
  URL:=http://github.com/pallets/markupsafe
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-markupsafe/description
  Implements a XML/HTML/XHTML Markup safe string for Python
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-markupsafe/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-markupsafe))
$(eval $(call BuildPackage,python3-markupsafe))
