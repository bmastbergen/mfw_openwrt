include $(TOPDIR)/rules.mk

PKG_NAME:=admin
PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=Sebastien Delafond <sdelafond@gmail.com>
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bmastbergen/mfw_admin.git

include ../version.mk
PKG_VERSION:=$(call UNTANGLE_VERSION,$(PKG_SOURCE_URL))
PKG_SOURCE_VERSION:=$(PKG_VERSION)

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz

include $(INCLUDE_DIR)/package.mk

define Package/admin
  SECTION:=ui
  CATEGORY:=User Interface
  TITLE:=MFW admin interface
  URL:=https://www.github.com/untangle/mfw_admin
  PKG_BUILD_DEPENDS:=wget
endef

define Package/admin/description
  MFW admin interface
endef

define Build/Compile
	true
endef

define Package/admin/install
	make -C $(PKG_BUILD_DIR) DESTDIR=$(1)/www install
endef

$(eval $(call BuildPackage,admin))
