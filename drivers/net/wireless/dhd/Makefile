# bcm4329
SRCBASE := $(shell /bin/pwd)/../..
CONFIG_WIRELESS_EXT=y
DHDCFLAGS =-DLINUX  -DBCMDRIVER -DBCMDONGLEHOST -DDHDTHREAD -DBCMWPA2 -DBCMWAPI_WPI\
	-DUNRELEASEDCHIP -DSRCBASE=\"$(SRCBASE)\" -DCONFIG_WIRELESS_EXT -DDHD_GPL -DDHD_SCHED -DSDTEST\
	-DBDC -DTOE -DDHD_BCMEVENTS -DSHOW_EVENTS -DSDIO_ISR_THREAD  -DEMBEDDED_PLATFORM\
	-DBCMSDIO -DDHD_GPL -DBCMLXSDMMC -DBCMPLATFORM_BUS \
	-Idrivers/net/wireless/dhd -Idrivers/net/wireless/dhd/include

DHDOFILES = dhd_linux.o linux_osl.o bcmutils.o dhd_common.o dhd_custom_gpio.o \
	wl_iw.o siutils.o sbutils.o aiutils.o hndpmu.o bcmwifi.o dhd_sdio.o   \
	dhd_linux_sched.o dhd_cdc.o bcmsdh_sdmmc.o bcmsdh.o bcmsdh_linux.o    \
	bcmsdh_sdmmc_linux.o

obj-$(CONFIG_BCM4329) += dhd.o
dhd-objs += $(DHDOFILES)
EXTRA_CFLAGS = $(DHDCFLAGS)
EXTRA_LDFLAGS += --strip-debug
