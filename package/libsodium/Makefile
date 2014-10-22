#
# Copyright (C) 2011-2014 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libsodium
PKG_VERSION:=1.0.0
PKG_RELEASE:=1.E

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://download.dnscrypt.org/libsodium/releases
PKG_MD5SUM:=3093dabe4e038d09f0d150cef064b2f7

PKG_INSTALL:=1
PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/libsodium
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=Library for network communication, encryption, decryption, signatures, etc
	URL:=https://github.com/jedisct1/libsodium
	MAINTAINER:=Black Roland https://github.com/black-roland/exOpenWrt
endef

define Package/libsodium/description
	NaCl (pronounced "salt") is a new easy-to-use high-speed software library for
	network communication, encryption, decryption, signatures, etc.
	Sodium is a portable, cross-compilable, installable, packageable fork of NaCl,
	with a compatible API.
endef

CONFIGURE_ARGS += \
	--disable-ssp \
	--disable-asm \
	--enable-minimal

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
endef

define Package/libsodium/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsodium.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libsodium))
