#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-yaml
PKG_VERSION:=3.12
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=PyYAML-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://pypi.python.org/packages/6b/f0/a0250248ea260d55748fff586d89a32afbb22656f4498b08d2636a48d4ec
PKG_MD5SUM:=aa5e762e79b19bb80dbcf04f82178832
PKG_BUILD_DIR:=$(BUILD_DIR)/PyYAML-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-yaml
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=YAML parser and emitter for Python
  URL:=http://pyyaml.org/wiki/PyYAML
  DEPENDS:=+python3 +python3-dev +libyaml
endef

define Package/python3-yaml/description
  YAML is a data serialization format designed for human readability and interaction with scripting languages. PyYAML is a YAML parser and emitter for Python.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-yaml/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-yaml))
$(eval $(call BuildPackage,python3-yaml))
