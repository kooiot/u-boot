# SPDX-License-Identifier: GPL-2.0+

ifeq ($(CONFIG_SPL_BUILD)$(CONFIG_TPL_BUILD),)
nandcore-objs := core.o bbt.o
obj-$(CONFIG_MTD_NAND_CORE) += nandcore.o
obj-$(CONFIG_MTD_RAW_NAND) += raw/
obj-$(CONFIG_MTD_SPI_NAND) += spi/
else
# SPL has no MTD_NAND_CORE symbol, so we must key off SPI NAND usage
nandcore-objs := core.o bbt.o
obj-$(CONFIG_SPL_SPI_NAND_LOAD) += nandcore.o
obj-$(CONFIG_SPL_SPI_NAND_LOAD) += spi/

obj-$(CONFIG_$(SPL_TPL_)NAND_SUPPORT) += raw/
endif
