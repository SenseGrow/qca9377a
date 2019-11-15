
Release Note  
-----------------------------------------------
qca9377a-3-lea3.0-4.0.11.213V-4.14-fn001
-----------------------------------------------
Publisher: jsa@fn-link  Date:2019.1.28


Version 

	Chip: QCA9377-3
	Module: Fn-Link 8223A-SR
	OS: Linux / Android
	Kernel: 4.14.x
	Driver: 4.0.11.213V
	FW_VER: 0.0.0.22

1.Prepare kernel
 a.	Patch your kernel                # Refer to patch_kernel/
 b.     vi .config
 
	CONFIG_CFG80211=y
                CONFIG_NL80211_TESTMODE=y	
	CONFIG_CFG80211_INTERNAL_REGDB=y
2. Compile

	cd WLAN-AIO/build
	vi scripts/te-f30/config.te-f30  # Modify the kernel path and compile toolschain etc.
	make

3. Instructions

 a. Driver 
	WLAN-AIO/rootfs-te-f30.build/lib/modules/wlan.ko
 b. firmware
	cp firmware/* /lib/firmware/ -rf  # /lib/firmware is default firmware path,
					  #  you can change the path in driver according your platform 

 b. Load driver
	insmod wlan.ko


