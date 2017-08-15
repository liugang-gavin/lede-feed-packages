#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-yarl
PKG_VERSION:=0.11.0
PKG_RELEASE:=1
PKG_LICENSE:=Apache 2.0

PKG_SOURCE:=yarl-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/cc/b6/14db4c96244fa47cf63db62177dd97739d505c90515c83479660ea6d9439
PKG_MD5SUM:=a5a21f6ba05b62d34a32b3bbe50493bf
PKG_BUILD_DIR:=$(BUILD_DIR)/yarl-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-yarl
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Another URL library
  URL:=https://github.com/aio-libs/yarl/
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-yarl/description
  Yet another URL library
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-yarl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-yarl))
$(eval $(call BuildPackage,python3-yarl))
