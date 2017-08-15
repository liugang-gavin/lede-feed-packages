#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-pahomqtt
PKG_VERSION:=1.3.0
PKG_RELEASE:=1
PKG_LICENSE:=Eclipse Public License v1.0 / Eclipse Distribution License v1.0

PKG_SOURCE:=paho-mqtt-$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/paho-mqtt-$(PKG_VERSION)/
PKG_SOURCE_URL:=https://pypi.python.org/packages/33/7f/3ce1ffebaa0343d509aac003800b305d821e89dac3c11666f92e12feca14
PKG_MD5SUM:=b9338236e2836e8579ef140956189cc4
PKG_BUILD_DEPENDS:=python python-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-pahomqtt
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=MQTT version 3.1.1 client class
  URL:=http://mqtt.org/tag/paho
  DEPENDS:=+python
endef

define Package/python-pahomqtt/description
	The MQTT protocol is a machine-to-machine (M2M) ”Internet of Things” connectivity protocol.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-pahomqtt/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
	    $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
	    $(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-pahomqtt))

