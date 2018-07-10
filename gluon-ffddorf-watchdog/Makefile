include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-ffddorf-watchdog
PKG_VERSION:=1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/gluon-ffddorf-watchdog
  SECTION:=gluon
  CATEGORY:=Gluon
  TITLE:=Restarts services or the whole node if any issues show up
  DEPENDS:=+micrond
endef

define Package/gluon-ffddorf-watchdog/description
	Gluon community wifi mesh firmware framework: ffddorf watchdog
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/gluon-ffddorf-watchdog/install
	$(CP) ./files/* $(1)/
endef

define Package/gluon-ffddorf-watchdog/postinst
endef

$(eval $(call BuildPackage,gluon-ffddorf-watchdog))
