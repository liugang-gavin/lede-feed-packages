#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-gttstoken
PKG_VERSION:=1.1.1
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=gTTS-token-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://pypi.python.org/packages/4c/c8/dd58eba1464729095217d3acfc4f6581348c6f495ea3342ed7dbc9f9e133
PKG_MD5SUM:=39f56680d81c3d553ccc663f013a48f8
PKG_BUILD_DIR:=$(BUILD_DIR)/gTTS-token-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-gttstoken
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Calculates a token to run the Google TTS
  URL:=https://github.com/boudewijn26/gTTS-token
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-gttstoken/description
  **gTTS-token** (Google Text to Speech token): A python implementation of the token validation of Google Translate
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-gttstoken/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-gttstoken))
$(eval $(call BuildPackage,python3-gttstoken))
