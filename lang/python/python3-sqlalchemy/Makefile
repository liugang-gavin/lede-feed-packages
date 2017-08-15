#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-sqlalchemy
PKG_VERSION:=1.1.11
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=SQLAlchemy-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/59/f1/28f2205c3175e6bf32300c0f30f9d91dbc9eb910debbff3ffecb88d18528
PKG_MD5SUM:=3de387eddb4012083a4562928c511e43
PKG_BUILD_DIR:=$(BUILD_DIR)/SQLAlchemy-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-sqlalchemy
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Feng Guo <feng.guo@nxp.com>
  TITLE:=Database Abstraction Library
  URL:=http://www.sqlalchemy.org
  DEPENDS:=+python3 +python3-dev
endef

define Package/python3-sqlalchemy/description
  The Python SQL Toolkit and Object Relational Mapper
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --root="$(PKG_INSTALL_DIR)" --prefix="/usr" \
	)
endef

define Py3Package/python3-sqlalchemy/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) -a $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION) $(1)/usr/lib
endef

$(eval $(call Py3Package,python3-sqlalchemy))
$(eval $(call BuildPackage,python3-sqlalchemy))
