#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NPM_NAME:=homebridge-mqttlightbulb
PKG_NAME:=node-$(PKG_NPM_NAME)
PKG_VERSION:=0.0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/ameeuw/homebridge-mqttlightbulb
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=d12e16cd92d88a01456f7ed2903a31fffa5a5147
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_DEPENDS:=node/host
PKG_NODE_VERSION:=4.4.5

PKG_MAINTAINER:=Feng Guo <feng.guo@nxp.com>
PKG_LICENSE:=Apache License 2.0
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/node-homebridge-mqttlightbulb
  DEPENDS:=+node
  SUBMENU:=Node.js
  SECTION:=lang
  CATEGORY:=Languages
  DEPENDS:=+libstdcpp
  TITLE:=Homebridge plugin for MQTT Lightbulb
  URL:=https://github.com/ameeuw/homebridge-mqttlightbulb
endef

define Package/node-homebridge-mqttlightbulb/description
  An homebridge plugin that create an HomeKit Lightbulb accessory mapped on MQTT topics
endef

CPU:=$(subst x86_64,x64,$(subst i386,ia32,$(ARCH)))

define Build/Compile
	git init $(PKG_BUILD_DIR)
	npm config set prefix "$(PKG_INSTALL_DIR)/usr"
	$(MAKE_VARS) \
	$(MAKE_FLAGS) \
	npm_config_arch=$(CONFIG_ARCH) \
	npm_config_nodedir=$(BUILD_DIR)/node-v$(PKG_NODE_VERSION)/ \
	npm_config_cache=$(BUILD_DIR)/node-v$(PKG_NODE_VERSION)/npm-cache \
	npm install --build-from-source --target_arch=$(CPU) -g $(PKG_BUILD_DIR)
endef

define Package/node-homebridge-mqttlightbulb/install
   $(INSTALL_DIR) $(1)/usr/lib/node_modules/
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/node_modules/* $(1)/usr/lib/node_modules/
endef

$(eval $(call BuildPackage,node-homebridge-mqttlightbulb))

