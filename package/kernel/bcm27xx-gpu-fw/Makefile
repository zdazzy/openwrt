include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=bcm27xx-gpu-fw
PKG_VERSION:=2024-02-08
PKG_RELEASE:=2a1e5bfd933d977a57ba4cd62f3381fdc339e29a

PKG_BUILD_DIR:=$(KERNEL_BUILD_DIR)/$(PKG_NAME)/rpi-firmware-$(PKG_RELEASE)

PKG_FLAGS:=nonshared

include $(INCLUDE_DIR)/package.mk

RPI_FIRMWARE_URL:=@GITHUB/raspberrypi/firmware/$(PKG_RELEASE)/boot/
RPI_FIRMWARE_FILE:=rpi-firmware-$(PKG_RELEASE)

define Download/LICENCE_broadcom
  FILE:=$(RPI_FIRMWARE_FILE)-LICENCE.broadcom
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=LICENCE.broadcom
  HASH:=c7283ff51f863d93a275c66e3b4cb08021a5dd4d8c1e7acc47d872fbe52d3d6b
endef
$(eval $(call Download,LICENCE_broadcom))

define Download/bootcode_bin
  FILE:=$(RPI_FIRMWARE_FILE)-bootcode.bin
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=bootcode.bin
  HASH:=af603ebd97e7b692c30195563f7b25656eb05d57838cf1a715ebb470d1614ce4
endef
$(eval $(call Download,bootcode_bin))

define Download/fixup_dat
  FILE:=$(RPI_FIRMWARE_FILE)-fixup.dat
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=fixup.dat
  HASH:=d8b55a35202684527a973ee47140376f440fee00d9679dc4a852ed0f22eb1bbe
endef
$(eval $(call Download,fixup_dat))

define Download/fixup_cd_dat
  FILE:=$(RPI_FIRMWARE_FILE)-fixup_cd.dat
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=fixup_cd.dat
  HASH:=90913bff616145166c68074360a2714eb92b2f35601fa189836cd03b4231b735
endef
$(eval $(call Download,fixup_cd_dat))

define Download/fixup_x_dat
  FILE:=$(RPI_FIRMWARE_FILE)-fixup_x.dat
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=fixup_x.dat
  HASH:=8a2ad53e131981b0dfac2f6658239fbb4fe18acf0c47b673c906e50612e58f63
endef
$(eval $(call Download,fixup_x_dat))

define Download/fixup4_dat
  FILE:=$(RPI_FIRMWARE_FILE)-fixup4.dat
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=fixup4.dat
  HASH:=5f2d922a87bb3a75f9ae7b5078f52a83d6b83a2a866223a64d328341e5b4351e
endef
$(eval $(call Download,fixup4_dat))

define Download/fixup4cd_dat
  FILE:=$(RPI_FIRMWARE_FILE)-fixup4cd.dat
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=fixup4cd.dat
  HASH:=90913bff616145166c68074360a2714eb92b2f35601fa189836cd03b4231b735
endef
$(eval $(call Download,fixup4cd_dat))

define Download/fixup4x_dat
  FILE:=$(RPI_FIRMWARE_FILE)-fixup4x.dat
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=fixup4x.dat
  HASH:=741a6656b51ffaefd8f52549b3c8f6e6431bc62821987f75ba83443535a22b8a
endef
$(eval $(call Download,fixup4x_dat))

define Download/start_elf
  FILE:=$(RPI_FIRMWARE_FILE)-start.elf
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=start.elf
  HASH:=dd9b42041b566d8b94529a6eda68ded147fd18c6a4b5d6b9743226082114ec84
endef
$(eval $(call Download,start_elf))

define Download/start_cd_elf
  FILE:=$(RPI_FIRMWARE_FILE)-start_cd.elf
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=start_cd.elf
  HASH:=9ffa821b94de83e55ead81c0493a0d0450094d12bed76b5d10bd60e34bdb5ce6
endef
$(eval $(call Download,start_cd_elf))

define Download/start_x_elf
  FILE:=$(RPI_FIRMWARE_FILE)-start_x.elf
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=start_x.elf
  HASH:=209c6345254a1422ebb60757bb520e7994840036b4d1d9ad9fab70f453042951
endef
$(eval $(call Download,start_x_elf))

define Download/start4_elf
  FILE:=$(RPI_FIRMWARE_FILE)-start4.elf
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=start4.elf
  HASH:=e1ee9939c23d253ec278a11954d7a35762d6be0d9f1d2d35a656fe1ae3a0304e
endef
$(eval $(call Download,start4_elf))

define Download/start4cd_elf
  FILE:=$(RPI_FIRMWARE_FILE)-start4cd.elf
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=start4cd.elf
  HASH:=e6bfe1e017a12c1b37c61ff4ee6f594369065c592464b3a6365f26fa589d8a39
endef
$(eval $(call Download,start4cd_elf))

define Download/start4x_elf
  FILE:=$(RPI_FIRMWARE_FILE)-start4x.elf
  URL:=$(RPI_FIRMWARE_URL)
  URL_FILE:=start4x.elf
  HASH:=0699ffde845eadab56ea6216b7b70b2266da35f0ef4ca59eeaaec4102cc5a624
endef
$(eval $(call Download,start4x_elf))

define Package/bcm27xx-gpu-fw
  SECTION:=boot
  CATEGORY:=Boot Loaders
  DEPENDS:=@TARGET_bcm27xx
  TITLE:=bcm27xx-gpu-fw
  DEFAULT:=y if TARGET_bcm27xx
endef

define Package/bcm27xx-gpu-fw/description
 GPU and kernel boot firmware for bcm27xx.
endef

define Build/Prepare
	rm -rf $(PKG_BUILD_DIR)
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-LICENCE.broadcom $(PKG_BUILD_DIR)/LICENCE.broadcom
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-bootcode.bin $(PKG_BUILD_DIR)/bootcode.bin
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-fixup.dat $(PKG_BUILD_DIR)/fixup.dat
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-fixup_cd.dat $(PKG_BUILD_DIR)/fixup_cd.dat
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-fixup_x.dat $(PKG_BUILD_DIR)/fixup_x.dat
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-fixup4.dat $(PKG_BUILD_DIR)/fixup4.dat
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-fixup4cd.dat $(PKG_BUILD_DIR)/fixup4cd.dat
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-fixup4x.dat $(PKG_BUILD_DIR)/fixup4x.dat
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-start.elf $(PKG_BUILD_DIR)/start.elf
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-start_cd.elf $(PKG_BUILD_DIR)/start_cd.elf
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-start_x.elf $(PKG_BUILD_DIR)/start_x.elf
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-start4.elf $(PKG_BUILD_DIR)/start4.elf
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-start4cd.elf $(PKG_BUILD_DIR)/start4cd.elf
	$(CP) $(DL_DIR)/$(RPI_FIRMWARE_FILE)-start4x.elf $(PKG_BUILD_DIR)/start4x.elf
endef

define Build/Compile
	true
endef

define Package/bcm27xx-gpu-fw/install
	true
endef

define Build/InstallDev
	$(CP) $(PKG_BUILD_DIR)/bootcode.bin $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/LICENCE.broadcom $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start_cd.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start_x.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start4.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start4cd.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start4x.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup_cd.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup_x.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup4.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup4cd.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup4x.dat $(KERNEL_BUILD_DIR)
endef

$(eval $(call BuildPackage,bcm27xx-gpu-fw))
