#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-jinja2
PKG_VERSION:=2.9.6
PKG_RELEASE:=1
PKG_LICENSE:=BSD

PKG_SOURCE:=Jinja2-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/90/61/f820ff0076a2599dd39406dcb858ecb239438c02ce706c8e91131ab9c7f1
PKG_MD5SUM:=6411537324b4dba0956aaa8109f3c77b
PKG_BUILD_DIR:=$(BUILD_DIR)/Jinja2-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-jinja2
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=A template engine written in pure Python
  URL:=http://jinja.pocoo.org/
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-jinja2/description
  Jinja2 is a template engine written in pure Python. It provides a Django inspired non-XML syntax but supports inline expressions and an optional sandboxed environment.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-jinja2/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-jinja2))
$(eval $(call BuildPackage,python3-jinja2))
