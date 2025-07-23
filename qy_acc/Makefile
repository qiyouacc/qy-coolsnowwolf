include $(TOPDIR)/rules.mk

PKG_NAME:=qy_acc
PKG_VERSION:=1.2.0
PKG_RELEASE:=1

PKG_SOURCE_SUBDIR:=$(PKG_NAME)_$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)
PKG_LICENSE:=Proprietary

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  TITLE:=qy acc pkg
  DEPENDS:=+kmod-tun
  URL:=https://www.qiyou.cn
endef

define Package/$(PKG_NAME)/description
  QiYou acc plugin
endef

define Build/Prepare
  mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
  echo "nothing"
endef

define Build/InstallDev
  rm -f $(STAMP_BUILT)
endef

define Package/$(PKG_NAME)/install
  $(INSTALL_DIR) $(1)/bin
  $(INSTALL_DIR) $(1)/etc/init.d

  $(CP) ./qy_acc.init $(1)/etc/init.d/qy_acc.init
  chmod 755 $(1)/etc/init.d/qy_acc.init

  $(CP) ./qy_acc.sh $(1)/bin/qy_acc.sh
  chmod 755 $(1)/bin/qy_acc.sh
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
