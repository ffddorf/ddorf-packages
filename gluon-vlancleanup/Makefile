include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-vlancleanup
PKG_VERSION:=1
PKG_RELEASE:=$(GLUON_BRANCH)

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(GLUONDIR)/include/package.mk


define Package/gluon-vlancleanup
  SECTION:=gluon
  CATEGORY:=Gluon
  DEPENDS:=+gluon-core
  TITLE:=Removes old mesh_radio0_vlan and mesh_radio1_vlan devices, this is a hotfix package for 2016.X as it is solved in master.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
	$(call GluonSrcDiet,./luasrc,$(PKG_BUILD_DIR)/luadest/)
endef

define Package/gluon-vlancleanup/install
	$(CP) $(PKG_BUILD_DIR)/luadest/* $(1)/
endef

define Package/gluon-vlancleanup/postinst
endef

$(eval $(call BuildPackage,gluon-vlancleanup))
