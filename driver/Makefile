ifeq ($(KERNELRELEASE),)
		PWD = $(shell pwd)
	        KERNELDIR = ../../../
modules:
	        $(MAKE) -C $(KERNELDIR) M=$(PWD) ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- modules

modules_install:
	        $(MAKE) -C $(KERNELDIR) M=$(PWD) ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- modules_install
			                                  
clean:                    
	        rm -rf  *.o *.ko .tmp_versions *.mod.c modules.order  Module.symvers ssd253x-ts.* 
else                      
		obj-m := openvfd.o
		openvfd-objs += protocols/i2c.o
		openvfd-objs += protocols/spi_3w.o
		openvfd-objs += controllers/dummy.o
		openvfd-objs += controllers/seg7_ctrl.o
		openvfd-objs += controllers/fd628.o
		openvfd-objs += controllers/fd650.o
		openvfd-objs += controllers/hd44780.o
		openvfd-objs += controllers/gfx_mono_ctrl.o
		openvfd-objs += controllers/ssd1306.o
		openvfd-objs += controllers/pcd8544.o
		openvfd-objs += openvfd_drv.o
endif
