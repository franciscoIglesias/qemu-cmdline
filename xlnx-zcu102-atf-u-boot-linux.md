# xlnx-zcu102 atf u-boot linux launch example

```
$ qemu-system-aarch64 -M xlnx-zcu102,secure=on,virtualization=on -m 4G -serial stdio -display none -device loader,file=u-boot.elf -kernel bl31.elf -device loader,addr=0x40000000,file=Image -device loader,addr=0x2000000,file=zcu102.dtb
pulseaudio: set_sink_input_volume() failed
pulseaudio: Reason: Invalid argument
pulseaudio: set_sink_input_mute() failed
pulseaudio: Reason: Invalid argument
NOTICE:  ATF running on silicon/RTL0.0 at 0xfffe4000
NOTICE:  BL3-1: Secure code at 0xfffc0000
NOTICE:  BL3-1: Non secure code at 0x8000000
NOTICE:  BL3-1: v1.1(release):5daaa2d7d
NOTICE:  BL3-1: Built : 14:40:20, Jan 17 2021
ERROR:   Error initializing runtime service sip_svc


U-Boot 2015.04 (Jan 16 2021 - 20:56:05) Xilinx ZynqMP

I2C:   ready
DRAM:  1 GiB
Enabling Caches...
NAND:  ERROR:arasan_nand_reset timedout
ERROR:arasan_nand_read_buf timedout:Buff RDY
ERROR:arasan_nand_read_buf timedout:Xfer CMPLT
ERROR:arasan_nand_read_buf timedout:Buff RDY
ERROR:arasan_nand_read_buf timedout:Xfer CMPLT
ERROR:arasan_nand_read_buf timedout:Buff RDY
ERROR:arasan_nand_read_buf timedout:Xfer CMPLT
ERROR:arasan_nand_read_buf timedout:Buff RDY
ERROR:arasan_nand_read_buf timedout:Xfer CMPLT
arasan_nand_init: nand_scan_ident failed
NAND init failed
0 MiB
MMC:   zynq_sdhci: 0
Using default environment

In:    serial
Out:   serial
Err:   serial
SCSI:  SATA link 0 timeout.
AHCI 0001.0000 32 slots 2 ports 1.5 Gbps 0x3 impl SATA mode
flags: 64bit ncq only 
scanning bus for devices...
Found 0 device(s).
Net:   Gem.ff0b0000
Hit any key to stop autoboot:  0 
ZynqMP> setenv bootargs rdinit=/bin/sh console=ttyPS0,115200 maxcpus=1
ZynqMP> setenv bootargs $bootargs earlycon=cdns,mmio,0xff000000,115200n8
ZynqMP> booti 0x40000000 - 2000000
## Flattened Device Tree blob at 02000000
   Booting using the fdt blob at 0x2000000
   Loading Device Tree to 000000000fff6000, end 000000000ffff646 ... OK

Starting kernel ...

[    0.000000] Booting Linux on physical CPU 0x0
[    0.000000] Linux version 4.4.0 (xxxx@xxx) (gcc version 8.3.0 (Debian 8.3.0-2) ) #41 SMP Sat Jan 16 23:14:56 GMT 2021
[    0.000000] Boot CPU: AArch64 Processor [410fd034]
[    0.000000] earlycon: Early serial console at MMIO 0xff000000 (options '115200n8')
[    0.000000] bootconsole [uart0] enabled
[    0.000000] cma: Reserved 128 MiB at 0x0000000038000000
[    0.000000] psci: probing for conduit method from DT.
[    0.000000] psci: PSCIv0.2 detected in firmware.
[    0.000000] psci: Using standard PSCI v0.2 function IDs
[    0.000000] psci: Trusted OS migration not required
[    0.000000] PERCPU: Embedded 15 pages/cpu @ffffffc037f91000 s23832 r8192 d29416 u61440
[    0.000000] Detected VIPT I-cache on CPU0
[    0.000000] CPU features: enabling workaround for ARM erratum 845719
[    0.000000] Built 1 zonelists in Zone order, mobility grouping on.  Total pages: 258560
[    0.000000] Kernel command line: rdinit=/bin/sh console=ttyPS0,115200 maxcpus=1 earlycon=cdns,mmio,0xff000000,115200n8
[    0.000000] PID hash table entries: 4096 (order: 3, 32768 bytes)
[    0.000000] Dentry cache hash table entries: 131072 (order: 8, 1048576 bytes)
[    0.000000] Inode-cache hash table entries: 65536 (order: 7, 524288 bytes)
[    0.000000] software IO TLB [mem 0x32e00000-0x36e00000] (64MB) mapped at [ffffffc032e00000-ffffffc036dfffff]
[    0.000000] Memory: 815648K/1048576K available (7178K kernel code, 168K rwdata, 3880K rodata, 7272K init, 342K bss, 101856K reserved, 131072K cma-reserved)
[    0.000000] Virtual kernel memory layout:
[    0.000000]     vmalloc : 0xffffff8000000000 - 0xffffffbdffff0000   (   247 GB)
[    0.000000]     vmemmap : 0xffffffbe00000000 - 0xffffffbfc0000000   (     7 GB maximum)
[    0.000000]               0xffffffbe00000000 - 0xffffffbe00e00000   (    14 MB actual)
[    0.000000]     fixed   : 0xffffffbffa7fd000 - 0xffffffbffac00000   (  4108 KB)
[    0.000000]     PCI I/O : 0xffffffbffae00000 - 0xffffffbffbe00000   (    16 MB)
[    0.000000]     modules : 0xffffffbffc000000 - 0xffffffc000000000   (    64 MB)
[    0.000000]     memory  : 0xffffffc000000000 - 0xffffffc040000000   (  1024 MB)
[    0.000000]       .init : 0xffffffc000b4e000 - 0xffffffc001268000   (  7272 KB)
[    0.000000]       .text : 0xffffffc000080000 - 0xffffffc000b4d034   ( 11061 KB)
[    0.000000]       .data : 0xffffffc00127a000 - 0xffffffc0012a4160   (   169 KB)
[    0.000000] Hierarchical RCU implementation.
[    0.000000]  Build-time adjustment of leaf fanout to 64.
[    0.000000]  RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
[    0.000000] RCU: Adjusting geometry for rcu_fanout_leaf=64, nr_cpu_ids=4
[    0.000000] NR_IRQS:64 nr_irqs:64 0
[    0.000000] GIC: Using split EOI/Deactivate mode
[    0.000000] Architected cp15 timer(s) running at 100.00MHz (phys).
[    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0x171024e7e0, max_idle_ns: 440795205315 ns
[    0.000358] sched_clock: 56 bits at 100MHz, resolution 10ns, wraps every 4398046511100ns
[    0.020939] Console: colour dummy device 80x25
[    0.022582] Calibrating delay loop (skipped), value calculated using timer frequency.. 200.00 BogoMIPS (lpj=400000)
[    0.023106] pid_max: default: 32768 minimum: 301
[    0.027148] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes)
[    0.027398] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes)
[    0.079324] ASID allocator initialised with 65536 entries
[    0.102125] Brought up 1 CPUs
[    0.102328] SMP: Total of 1 processors activated.
[    0.103095] CPU: All CPU(s) started at EL2
[    0.104930] alternatives: patching kernel code
[    0.129699] devtmpfs: initialized
[    0.180021] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
[    0.226786] xor: measuring software checksum speed
[    0.266522]    8regs     :  3567.000 MB/sec
[    0.307118]    8regs_prefetch:  3491.000 MB/sec
[    0.347880]    32regs    :  3341.000 MB/sec
[    0.388679]    32regs_prefetch:  3307.000 MB/sec
[    0.388952] xor: using function: 8regs (3567.000 MB/sec)
[    0.423153] NET: Registered protocol family 16
[    0.435152] cpuidle: using governor ladder
[    0.435722] cpuidle: using governor menu
[    0.436930] vdso: 2 pages (1 code @ ffffffc001281000, 1 data @ ffffffc001280000)
[    0.437713] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
[    0.459858] DMA: preallocated 256 KiB pool for atomic allocations
[    0.480486] ARM CCI_400_r1 PMU driver probed
[    0.791203] raid6: int64x1  gen()  2277 MB/s
[    0.860466] raid6: int64x1  xor()  1507 MB/s
[    0.929997] raid6: int64x2  gen()  2963 MB/s
[    0.999377] raid6: int64x2  xor()  2063 MB/s
[    1.069275] raid6: int64x4  gen()  3946 MB/s
[    1.138774] raid6: int64x4  xor()   125 MB/s
[    1.208418] raid6: int64x8  gen()   226 MB/s
[    1.277511] raid6: int64x8  xor()   207 MB/s
[    1.346990] raid6: neonx1   gen()  2133 MB/s
[    1.416267] raid6: neonx1   xor()  1462 MB/s
[    1.485609] raid6: neonx2   gen()  3434 MB/s
[    1.554813] raid6: neonx2   xor()  2232 MB/s
[    1.624187] raid6: neonx4   gen()  1956 MB/s
[    1.693404] raid6: neonx4   xor()  2819 MB/s
[    1.762758] raid6: neonx8   gen()   437 MB/s
[    1.832155] raid6: neonx8   xor()  2811 MB/s
[    1.832426] raid6: using algorithm int64x4 gen() 3946 MB/s
[    1.832630] raid6: .... xor() 125 MB/s, rmw enabled
[    1.832917] raid6: using intx1 recovery algorithm
[    1.835747] ACPI: Interpreter disabled.
[    1.841189] arm-smmu fd800000.smmu: probing hardware configuration...
[    1.841506] arm-smmu fd800000.smmu: SMMUv2 with:
[    1.841850] arm-smmu fd800000.smmu:  no translation support!
[    1.856868] SCSI subsystem initialized
[    1.861063] usbcore: registered new interface driver usbfs
[    1.862201] usbcore: registered new interface driver hub
[    1.862833] usbcore: registered new device driver usb
[    1.864448] media: Linux media interface: v0.10
[    1.865103] Linux video capture interface: v2.00
[    1.865677] pps_core: LinuxPPS API ver. 1 registered
[    1.865845] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
[    1.866301] PTP clock support registered
[    1.867067] EDAC MC: Ver: 3.0.0
[    1.883426] Advanced Linux Sound Architecture Driver Initialized.
[    1.905559] clocksource: Switched to clocksource arch_sys_counter
[    1.911615] pnp: PnP ACPI: disabled
[    2.009068] NET: Registered protocol family 2
[    2.023191] TCP established hash table entries: 8192 (order: 4, 65536 bytes)
[    2.023795] TCP bind hash table entries: 8192 (order: 5, 131072 bytes)
[    2.024328] TCP: Hash tables configured (established 8192 bind 8192)
[    2.026251] UDP hash table entries: 512 (order: 2, 16384 bytes)
[    2.026723] UDP-Lite hash table entries: 512 (order: 2, 16384 bytes)
[    2.030183] NET: Registered protocol family 1
[    2.037141] RPC: Registered named UNIX socket transport module.
[    2.037406] RPC: Registered udp transport module.
[    2.037675] RPC: Registered tcp transport module.
[    2.037827] RPC: Registered tcp NFSv4.1 backchannel transport module.
[    2.757974] hw perfevents: enabled with armv8_pmuv3 PMU driver, 5 counters available
[    2.765450] futex hash table entries: 1024 (order: 5, 131072 bytes)
[    2.767644] audit: initializing netlink subsys (disabled)
[    2.769678] audit: type=2000 audit(2.708:1): initialized
[    2.783737] HugeTLB registered 2 MB page size, pre-allocated 0 pages
[    2.790383] VFS: Disk quotas dquot_6.6.0
[    2.790919] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
[    2.803221] NFS: Registering the id_resolver key type
[    2.805220] Key type id_resolver registered
[    2.805424] Key type id_legacy registered
[    2.805974] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
[    2.807129] jffs2: version 2.2. (NAND) (SUMMARY)  © 2001-2006 Red Hat, Inc.
[    2.838375] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 248)
[    2.838992] io scheduler noop registered
[    2.839279] io scheduler deadline registered
[    2.839702] io scheduler cfq registered (default)
[    2.856737] xilinx-dpdma fd4c0000.dma: Xilinx DPDMA engine is probed
[    2.861099] xilinx-zynqmp-dma fd500000.dma: ZynqMP DMA driver Probe success
[    2.862877] xilinx-zynqmp-dma fd510000.dma: ZynqMP DMA driver Probe success
[    2.864357] xilinx-zynqmp-dma fd520000.dma: ZynqMP DMA driver Probe success
[    2.866021] xilinx-zynqmp-dma fd530000.dma: ZynqMP DMA driver Probe success
[    2.867483] xilinx-zynqmp-dma fd540000.dma: ZynqMP DMA driver Probe success
[    2.868933] xilinx-zynqmp-dma fd550000.dma: ZynqMP DMA driver Probe success
[    2.870539] xilinx-zynqmp-dma fd560000.dma: ZynqMP DMA driver Probe success
[    2.872030] xilinx-zynqmp-dma fd570000.dma: ZynqMP DMA driver Probe success
[    2.873669] zynqmp_pm_probe power management API version error. Expected: v0.2 - Found: v0.0
[    2.874190] zynqmp_pm: probe of firmware failed with error -5
[    3.400010] Serial: 8250/16550 driver, 4 ports, IRQ sharing disabled
[    3.414087] ff000000.serial: ttyPS0 at MMIO 0xff000000 (irq = 206, base_baud = 6250000) is a xuartps
[    3.417046] console [ttyPS0] enabled
[    3.417046] console [ttyPS0] enabled
[    3.417846] bootconsole [uart0] disabled
[    3.417846] bootconsole [uart0] disabled
[    3.422435] ff010000.serial: ttyPS1 at MMIO 0xff010000 (irq = 207, base_baud = 6250000) is a xuartps
[    3.425447] [drm] Initialized drm 1.1.0 20060810
[    3.438224] [drm] load() is defered & will be called again
[    3.457596] xilinx-drm-dp-sub fd4aa000.dp_sub: Xilinx DisplayPort Subsystem is probed
[    3.460135] Unable to detect cache hierarchy from DT for CPU 0
[    3.544560] brd: module loaded
[    3.584101] loop: module loaded
[    3.595866] ahci-ceva fd0c0000.ahci: AHCI 0001.0000 32 slots 2 ports 1.5 Gbps 0x3 impl platform mode
[    3.596376] ahci-ceva fd0c0000.ahci: flags: 64bit ncq only 
[    3.613149] scsi host0: ahci-ceva
[    3.618239] scsi host1: ahci-ceva
[    3.620151] ata1: SATA max UDMA/133 mmio [mem 0xfd0c0000-0xfd0c1fff] port 0x100 irq 203
[    3.620547] ata2: SATA max UDMA/133 mmio [mem 0xfd0c0000-0xfd0c1fff] port 0x180 irq 203
[    3.623521] mtdoops: mtd device (mtddev=name/number) must be supplied
[    3.649679] m25p80 spi0.0: found n25q512a, expected m25p80
[    3.650481] m25p80 spi0.0: Controller not in SPI_TX_QUAD mode, just use extended SPI mode
[    3.651387] m25p80 spi0.0: n25q512a (131072 Kbytes)
[    3.653031] 4 ofpart partitions found on MTD device spi0.0
[    3.653383] Creating 4 MTD partitions on "spi0.0":
[    3.654187] 0x000000000000-0x000000100000 : "qspi-fsbl-uboot"
[    3.666376] 0x000000100000-0x000000600000 : "qspi-linux"
[    3.672419] 0x000000600000-0x000000620000 : "qspi-device-tree"
[    3.678938] 0x000000620000-0x000000c00000 : "qspi-rootfs"
[    3.702768] libphy: Fixed MDIO Bus: probed
[    3.708117] CAN device driver interface
[    3.724906] libphy: MACB_mii_bus: probed
[    3.908421] macb ff0e0000.ethernet eth0: Cadence GEM rev 0x40070106 at 0xff0e0000 irq 22 (00:0a:35:00:01:22)
[    3.909790] macb ff0e0000.ethernet eth0: attached PHY driver [Marvell 88E1111] (mii_bus:phy_addr=ff0e0000.etherne:17, irq=-1)
[    3.931497] dwc3 fe200000.dwc3: this is not a DesignWare USB3 DRD Core
[    3.931777] dwc3 fe200000.dwc3: failed to initialize core
[    3.935177] usbcore: registered new interface driver uas
[    3.935904] usbcore: registered new interface driver usb-storage
[    3.943770] mousedev: PS/2 mouse device common for all mice
[    3.953760] rtc_zynqmp ffa60000.rtc: rtc core: registered ffa60000.rtc as rtc0
[    3.962987] ata1: SATA link down (SStatus 0 SControl 300)
[    3.966458] ata2: SATA link down (SStatus 0 SControl 300)
[    4.958967] cdns-i2c ff020000.i2c: timeout waiting on completion
[    4.961000] pca953x 0-0020: failed reading register
[    4.961329] pca953x: probe of 0-0020 failed with error -110
[    5.962395] cdns-i2c ff020000.i2c: timeout waiting on completion
[    5.963450] pca953x 0-0021: failed reading register
[    5.964484] pca953x: probe of 0-0021 failed with error -110
[    5.971441] cdns-i2c ff020000.i2c: 400 kHz mmio ff020000 irq 198
[    5.983259] cdns-i2c ff030000.i2c: 400 kHz mmio ff030000 irq 199
[    6.989750] cdns-i2c ff020000.i2c: timeout waiting on completion
[    6.990108] pca954x 0-0075: probe failed
[    7.990373] cdns-i2c ff030000.i2c: timeout waiting on completion
[    7.991391] pca954x 1-0074: probe failed
[    8.990323] cdns-i2c ff030000.i2c: timeout waiting on completion
[    8.991360] pca954x 1-0075: probe failed
[    9.025474] EDAC MC: ECC not enabled
[    9.026777] sdhci: Secure Digital Host Controller Interface driver
[    9.026985] sdhci: Copyright(c) Pierre Ossman
[    9.027185] sdhci-pltfm: SDHCI platform and OF driver helper
[    9.038545] sdhci-arasan ff170000.sdhci: No vmmc regulator found
[    9.038835] sdhci-arasan ff170000.sdhci: No vqmmc regulator found
[    9.082130] mmc0: SDHCI controller on ff170000.sdhci [ff170000.sdhci] using ADMA 64-bit
[    9.084715] usbcore: registered new interface driver usbhid
[    9.084913] usbhid: USB HID core driver
[    9.098827] Mali: ERR: drivers/staging/mali/DX910-SW-99002-r5p1-01rel0/driver/src/devicedrv/mali/common/mali_pp.c
[    9.099194]            mali_pp_reset_wait() 267
           Mali PP: Failed to reset core Mali_PP0, rawstat: 0x00000000
[    9.099536] 
[    9.099958] Mali: ERR: drivers/staging/mali/DX910-SW-99002-r5p1-01rel0/driver/src/devicedrv/mali/common/mali_kernel_core.c
[    9.100317]            mali_parse_product_info() 164
           Failed to create initial PP object
[    9.100627] 
[    9.103990] Mali: ERR: drivers/staging/mali/DX910-SW-99002-r5p1-01rel0/driver/src/devicedrv/mali/linux/mali_kernel_linux.c
[    9.104338]            mali_probe() 503
           mali_probe(): Failed to initialize Mali device driver.
[    9.104914] mali-utgard: probe of fd4b0000.gpu failed with error -14
[    9.105820] Mali: Mali device driver loaded
[    9.119818] xilinx-dp-snd-pcm amba:dp_snd_pcm0: Xilinx DisplayPort Sound PCM probed
[    9.120373] xilinx-dp-snd-pcm amba:dp_snd_pcm1: Xilinx DisplayPort Sound PCM probed
[    9.122041] xilinx-dp-snd-codec amba:dp_snd_codec0: Xilinx DisplayPort Sound Codec probed
[    9.135003] xilinx-dp-snd-card amba:dp_snd_card: xilinx-dp-snd-codec-dai <-> xilinx-dp-snd-codec-dai mapping ok
[    9.136461] xilinx-dp-snd-card amba:dp_snd_card: xilinx-dp-snd-codec-dai <-> xilinx-dp-snd-codec-dai mapping ok
[    9.147181] xilinx-dp-snd-card amba:dp_snd_card: Xilinx DisplayPort Sound Card probed
[    9.148244] pktgen: Packet Generator for packet performance testing. Version: 2.75
[    9.152358] Initializing XFRM netlink socket
[    9.153869] NET: Registered protocol family 10
[    9.168706] sit: IPv6 over IPv4 tunneling driver
[    9.174824] NET: Registered protocol family 17
[    9.175621] NET: Registered protocol family 15
[    9.175937] can: controller area network core (rev 20120528 abi 9)
[    9.176831] NET: Registered protocol family 29
[    9.177320] can: raw protocol (rev 20120528)
[    9.177773] can: broadcast manager protocol (rev 20120528 t)
[    9.178133] can: netlink gateway (rev 20130117) max_hops=1
[    9.179810] Key type dns_resolver registered
[    9.185755] registered taskstats version 1
[    9.192508] Btrfs loaded
[    9.206732] [drm] load() is defered & will be called again
[    9.213234] xilinx-drm-dp fd4a0000.dp: device found, version 4.010
[    9.213714] xilinx-drm-dp fd4a0000.dp: Display Port, version 1.0200 (tx)
[    9.217037] [drm] load() is defered & will be called again
[    9.221738] rtc_zynqmp ffa60000.rtc: setting system clock to 2021-01-17 15:01:46 UTC (1610895706)
[    9.223468] ALSA device list:
[    9.223658]   #0: DisplayPort monitor
[    9.255614] Freeing unused kernel memory: 7272K (ffffffc000b4e000 - ffffffc001268000)
[    9.256187] Freeing alternatives memory: 52K (ffffffc001268000 - ffffffc001275000)
/bin/sh: can't access tty; job control turned off
/ #
```
