include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-domain-migrator

GLUON_SITEDIR = $(call qstrip,$(CONFIG_GLUON_SITEDIR))
GLUON_SITE_VERSION = $(shell ( cd '$(GLUON_SITEDIR)' && git --git-dir=.git describe --always --dirty=+ ) 2>/dev/null || echo unknown)
PKG_VERSION:=$(if $(DUMP),x,$(GLUON_SITE_VERSION))

PKG_FILE_DEPENDS := $(GLUON_SITEDIR)/migrator.json

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(TOPDIR)/../package/gluon.mk

define Package/gluon-domain-migrator
	SECTION:=gluon
	CATEGORY:=Gluon
	TITLE:=Selects a domain for the node based on a JSON config
endef

define Package/gluon-domain-migrator/description
	Selects a domain for the node based on a JSON config
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
	$(call GluonSrcDiet,./luasrc,$(PKG_BUILD_DIR)/luadest/)
endef

define Package/gluon-domain-migrator/install
	$(CP) $(PKG_BUILD_DIR)/luadest/* $(1)/
	$(INSTALL_DATA) $(GLUON_SITEDIR)/migrator.json $(1)/lib/gluon/
endef

$(eval $(call BuildPackage,gluon-domain-migrator))
