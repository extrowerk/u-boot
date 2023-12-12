BUILD_DEPENDS+= devel/arm-none-eabi/gcc,aarch64 \
		devel/py-elftools${MODPY_FLAVOR} \
		shells/bash \
		sysutils/e2fsprogs
CROSS_COMPILE=	aarch64-none-elf-

SITES.rkbin=	https://github.com/rockchip-linux/rkbin/raw/master/bin/rk35/
RK3568_TPL=	rk3568_ddr_1560MHz_v1.18.bin
RK356X_BL31=	rk3568_bl31_v1.43.elf

Compile:

CROSS_COMPILE=aarch64-none-elf- ARCH=aarch64 ROCKCHIP_TPL=rk3568_ddr_1056MHz_v1.18.bin BL31=rk3568_bl31_v1.43.elf DTC=/usr/local/bin/dtc gmake O=build/H68K opc-h68k-rk3568_defconfig
CROSS_COMPILE=aarch64-none-elf- ARCH=aarch64 ROCKCHIP_TPL=rk3568_ddr_1056MHz_v1.18.bin BL31=rk3568_bl31_v1.43.elf DTC=/usr/local/bin/dtc gmake O=build/H68K

