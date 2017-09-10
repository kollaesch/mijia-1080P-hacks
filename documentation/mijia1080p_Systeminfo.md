# mijia 1080p - Systeminfo

Author: [kollaesch](https://github.com/kollaesch)

<!-- MarkdownTOC -->

- [General](#general)
- [nvram](#nvram)
- [CPU](#cpu)
- [crypto](#crypto)
- [devices](#devices)
- [mounts](#mounts)
- [filesystems](#filesystems)
- [gm_jiffies](#gm_jiffies)
- [ioports](#ioports)
- [lsmod](#lsmod)
- [kernel-modules](#kernel-modules)

<!-- /MarkdownTOC -->

[**open todos**](todos.md)

## General

On this neat cam there's a linux running. kernel 3.3.30. Futher details for general reference below.


## nvram

```
/usr/sbin/nvram show
light=on
miio_ssid=XXXXXXXXXXX
mible_evtrule=00000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
miio_key_mgmt=WPA
sdram_ncdl=0x00000000
sdcard_status=1
band_nearby=off
night_mode=0
watermark=off
power_master=anyone
motion_detection_enable=on
motion_record=off
sdram_config=0x014B
miio_passwd=XYXYXYXYXYXYXYXYXYXYXYXYXYXYXYXYXYXYXYX
sdram_init=0x0000
ibeacon_uuid=?????????????????????????????????????
mible_psm=?????????????????????????????????????
miio_token=?????????????????????????????????????
wdr=off
model=mijia.camera.v1
vendor=xiaomi
power=on
led_owner=1
sdram_refresh=0x0000
motion_alarm=[0,0,0,0,0,0,1]
flip=off
config_partition=1
miio_uid=WHOISHERE??!
motion_region=[1,1,1,1,1,1,1,1,1,2,2,2,2,2,2,1,1,2,2,2,2,2,2,1,1,1,1,1,1,1,1,1]
```


## CPU

```
/ # cat /proc/cpuinfo
Processor	: FA6 rev 3 (v5l)
BogoMIPS	: 858.52
Features	: swp half
CPU implementer	: 0x66
CPU architecture: 5TE
CPU variant	: 0x0
CPU part	: 0x626
CPU revision	: 3

Hardware	: Grain-Media GM8136 series
Revision	: 0000
Serial		: 0000000000000000
```


## crypto

```
/ # cat /proc/crypto
name         : stdrng
driver       : krng
module       : kernel
priority     : 200
refcnt       : 1
selftest     : passed
type         : rng
seedsize     : 0

name         : aes
driver       : aes-generic
module       : kernel
priority     : 100
refcnt       : 1
selftest     : passed
type         : cipher
blocksize    : 16
min keysize  : 16
max keysize  : 32

name         : sha256
driver       : sha256-generic
module       : kernel
priority     : 0
refcnt       : 1
selftest     : passed
type         : shash
blocksize    : 64
digestsize   : 32

name         : sha224
driver       : sha224-generic
module       : kernel
priority     : 0
refcnt       : 1
selftest     : passed
type         : shash
blocksize    : 64
digestsize   : 28
```


## devices 

```
/proc # cat devices
Character devices:
  1 mem
  4 ttyS
  5 /dev/tty
  5 /dev/console
  5 /dev/ptmx
 10 misc
 13 input
 29 fb
 89 i2c
 90 mtd
128 ptm
136 pts
180 usb
189 usb_device

Block devices:
  1 ramdisk
259 blkext
  7 loop
 31 mtdblock
179 mmc
```

## mounts

```
rootfs on / type rootfs (rw)
/dev/root on / type squashfs (ro,relatime)
devtmpfs on /dev type devtmpfs (rw,relatime,size=62668k,nr_inodes=15667,mode=755)

proc on /proc type proc (rw,relatime)
devpts on /dev/pts type devpts (rw,relatime,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,relatime,mode=777)
tmpfs on /tmp type tmpfs (rw,relatime)
tmpfs on /run type tmpfs (rw,nosuid,nodev,relatime,mode=755)
tmpfs on /var type tmpfs (rw,nosuid,nodev,relatime,mode=755)
tmpfs on /mnt/media type tmpfs (rw,nosuid,nodev,relatime,mode=755)
sysfs on /sys type sysfs (rw,relatime)

/dev/mtdblock3 on /mnt/data type jffs2 (rw,relatime)
/dev/mmcblk0p1 on /mnt/media/mmcblk0p1 type vfat (rw,relatime,fmask=0000,dmask=0000,allow_utime=0022,codepage=cp437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
/dev/mmcblk0p1 on /tmp/sd type vfat (rw,relatime,fmask=0000,dmask=0000,allow_utime=0022,codepage=cp437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
```

## filesystems

```
/proc # cat filesystems
nodev   sysfs
nodev   rootfs
nodev   bdev
nodev   proc
nodev   tmpfs
nodev   devtmpfs
nodev   debugfs
nodev   sockfs
nodev   pipefs
nodev   anon_inodefs
nodev   rpc_pipefs
nodev   devpts
    squashfs
nodev   ramfs
    vfat
    msdos
    exfat
nodev   nfs
nodev   nfs4
nodev   jffs2
nodev   mtd_inodefs
```

## gm_jiffies

```
/proc # cat gm_jiffies
gm jiffies: 0x75f17, HZ = 100
reference count: 0x50
```

## ioports

```
cat ioports
fe001000-fe00101f : serial
```

## lsmod

```
/proc # lsmod
Module                  Size  Used by    Tainted: G
frammap                20422  0
sd8xxx                493790  1
mlan                  517116  1 sd8xxx
```

## kernel-modules

```
/proc # ls /lib/modules/3.3.0/
adda308.ko           frotation_drv.ko     modules.symbols
aec.ko               fscaler300.ko        modules.symbols.bin
audio_drv.ko         ft3dnr200.ko         mp4e_rc.ko
bt8xxx.ko            g_GM_udc.ko          ms.ko
codec.ko             g_ether.ko           osd_dispatch.ko
decoder.ko           g_mass_storage.ko    pmonitor.ko
em.ko                gs.ko                sar_adc.ko
favc_enc.ko          log.ko               sd8xxx.ko
favc_rc.ko           loop_comm.ko         sw_osg.ko
fe_common.ko         mje_rc.ko            think2d.ko
fisp328.ko           mlan.ko              udc-core.ko
fisp_algorithm.ko    modules.alias        vcap0.ko
fisp_ov2715.ko       modules.alias.bin    vcap300_common.ko
fisp_ov2718.ko       modules.builtin.bin  vcap300_isp.ko
fmcp_drv.ko          modules.dep          vpd_master.ko
fmjpeg_drv.ko        modules.dep.bin      vpd_slave.ko
fmpeg4_drv.ko        modules.devname
frammap.ko           modules.softdep
```
