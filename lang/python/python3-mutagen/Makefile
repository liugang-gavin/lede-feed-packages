#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-mutagen
PKG_VERSION:=1.38
PKG_RELEASE:=1
PKG_LICENSE:=GNU GPL v2

PKG_SOURCE:=mutagen-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/57/ec/d7534cdb2766f1fee534a3aabdbdfbf05d6cf77cde617d77b526336a1a72
PKG_MD5SUM:=c54443dfb8d4ac088eb2a0c4fd569772
PKG_BUILD_DIR:=$(BUILD_DIR)/mutagen-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-mutagen
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Read and write audio tags for many formats
  URL:=https://github.com/quodlibet/mutagen
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-mutagen/description
  Mutagen is a Python module to handle audio metadata.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-mutagen/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-mutagen))
$(eval $(call BuildPackage,python3-mutagen))
