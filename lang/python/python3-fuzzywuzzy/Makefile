#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-fuzzywuzzy
PKG_VERSION:=0.15.0
PKG_RELEASE:=1
PKG_LICENSE:=GPL

PKG_SOURCE:=fuzzywuzzy-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/fc/03/052c31efd8016e58f498fb05ea3717a120108a379548dabe18a3890d48b0
PKG_MD5SUM:=97cbc62d3c4c220b7c566a0e72ef651e
PKG_BUILD_DIR:=$(BUILD_DIR)/fuzzywuzzy-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-fuzzywuzzy
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Fuzzy string matching in python
  URL:=https://github.com/seatgeek/fuzzywuzzy
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-fuzzywuzzy/description
  Fuzzy string matching like a boss. It uses Levenshtein Distance to calculate the differences between sequences in a simple-to-use package.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-fuzzywuzzy/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-fuzzywuzzy))
$(eval $(call BuildPackage,python3-fuzzywuzzy))
