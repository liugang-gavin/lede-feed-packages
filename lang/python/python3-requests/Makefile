#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-requests
PKG_VERSION:=2.14.2
PKG_RELEASE:=1
PKG_LICENSE:=Apache 2.0

PKG_SOURCE:=requests-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/72/46/4abc3f5aaf7bf16a52206bb0c68677a26c216c1e6625c78c5aef695b5359
PKG_MD5SUM:=4c3c169ed67466088a2a6947784fe444
PKG_BUILD_DIR:=$(BUILD_DIR)/requests-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-requests
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Python HTTP for Humans
  URL:=http://python-requests.org
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-requests/description
  Python HTTP for Humans
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-requests/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-requests))
$(eval $(call BuildPackage,python3-requests))
