#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-typing
PKG_VERSION:=3.6.1
PKG_RELEASE:=1
PKG_LICENSE:=PSF

PKG_SOURCE:=typing-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/17/75/3698d7992a828ad6d7be99c0a888b75ed173a9280e53dbae67326029b60e
PKG_MD5SUM:=3fec97415bae6f742fb3c3013dedeb89
PKG_BUILD_DIR:=$(BUILD_DIR)/typing-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-typing
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Type Hints for Python
  URL:=https://docs.python.org/3/library/typing.html
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-typing/description
  Typing defines a standard notation for Python function and variable type annotations.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-typing/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-typing))
$(eval $(call BuildPackage,python3-typing))
