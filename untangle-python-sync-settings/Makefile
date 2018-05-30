include $(TOPDIR)/rules.mk

PKG_NAME:=untangle-python-sync-settings
PKG_VERSION:=0.1
PKG_RELEASE:=2018-05-30
PKG_LICENSE:=GPL-2.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/untangle/ngfw_pkgs.git
PKG_SOURCE_VERSION:=master
# PKG_SOURCE_VERSION:=$(shell git ls-remote $(PKG_SOURCE_URL) $(PKG_BRANCH) ...)
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
MAKE_PATH:=untangle-python-sync-settings

PKG_MAINTAINER:=Dirk Morris <dmorris@untangle.com>

include $(INCLUDE_DIR)/package.mk
#include ../../packages/lang/python/python-package.mk
$(call include_mk, python3-package.mk)

define Package/untangle-python-sync-settings
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python3
  TITLE:=Library for manipulating Untangle system settings
  URL:=https://untangle.com
  DEPENDS:=+python3
endef

define Package/untangle-python-sync-settings/description
	This module is a Library for manipulating Untangle system settings.
endef

define Build/Compile
	$(call Build/Compile/PyMod3,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)", \
	)
endef

define Package/untangle-python-sync-settings/install
	$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/* \
		$(1)$(PYTHON3_PKG_DIR)/
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
endef

$(eval $(call BuildPackage,untangle-python-sync-settings))