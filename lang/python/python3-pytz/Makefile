#
# Copyright (C) 2014-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-pytz
PKG_VERSION:=2017.2
PKG_RELEASE:=1

PKG_SOURCE:=pytz-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://pypi.python.org/packages/a4/09/c47e57fc9c7062b4e83b075d418800d322caa87ec0ac21e6308bd3a2d519
PKG_MD5SUM:=f89bde8a811c8a1a5bac17eaaa94383c

PKG_LICENSE:=MIT

PKG_BUILD_DIR:=$(BUILD_DIR)/pytz-$(PKG_VERSION)
PKG_USE_MIPS16:=0

HOST_BUILD_DEPENDS:=python3 python3/host
HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/pytz-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
$(call include_mk, python3-package.mk)
$(call include_mk, python3-host.mk)

define Package/python3-pytz
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=World timezone definitions, modern and historical.
	URL:=http://pythonhosted.org/pytz
	DEPENDS:=+python3 +python3-dev
	MAINTAINER:=Guo Feng <feng.guo@nxp.com>
endef

define Package/python3-pytz/description
	World timezone definitions, modern and historical.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
		--single-version-externally-managed \
	)
endef

define Py3Package/python3-pytz/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

define Host/Compile
   $(call Build/Compile/HostPy3Mod,,\
      install --root="$(STAGING_DIR_HOSTPKG)" --prefix="" \
   )
endef

define Host/Install
endef

$(eval $(call HostBuild))

$(eval $(call Py3Package,python3-pytz))
$(eval $(call BuildPackage,python3-pytz))
