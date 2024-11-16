#  TP4 
## I.Clean install
### 3.Verification

```bash
unuser@deb:~$ sudo lsblk
NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda           8:0    0   20G  0 disk
└─sda1        8:1    0   20G  0 part
  ├─ok-root 254:0    0  9.3G  0 lvm  /
  ├─ok-home 254:1    0  1.9G  0 lvm  /home
  ├─ok-swap 254:2    0  1.9G  0 lvm  [SWAP]
  └─ok-var  254:3    0  2.8G  0 lvm  /var
sr0          11:0    1 1024M  0 rom
```

```bash
unuser@deb:~$ df -h
Filesystem           Size  Used Avail Use% Mounted on
udev                 951M     0  951M   0% /dev
tmpfs                197M  1.1M  196M   1% /run
/dev/mapper/ok-root  9.1G  3.5G  5.2G  41% /
tmpfs                984M     0  984M   0% /dev/shm
tmpfs                5.0M  8.0K  5.0M   1% /run/lock
/dev/mapper/ok-var   2.7G  326M  2.3G  13% /var
/dev/mapper/ok-home  1.8G  1.7M  1.7G   1% /home
tmpfs                197M   52K  197M   1% /run/user/1000
tmpfs                197M   48K  197M   1% /run/user/108
```

### 4. Tailles et Inodes
```bash
unuser@deb:~$ df -i
Filesystem          Inodes  IUsed  IFree IUse% Mounted on
udev                243442    436 243006    1% /dev
tmpfs               251812    722 251090    1% /run
/dev/mapper/ok-root 610800 112602 498198   19% /
tmpfs               251812      1 251811    1% /dev/shm
tmpfs               251812      5 251807    1% /run/lock
/dev/mapper/ok-var  183264   6386 176878    4% /var
/dev/mapper/ok-home 121920     83 121837    1% /home
tmpfs                50362     68  50294    1% /run/user/1000
tmpfs                50362     60  50302    1% /run/user/108
```

```bash
unuser@deb:~$ du -h /boot/vmlinuz-6.1.0-27-amd64  && ls -i /boot/vmlinuz-6.1.0-27-amd64
7.9M    /boot/vmlinuz-6.1.0-27-amd64
260620 /boot/vmlinuz-6.1.0-27-amd64
```

## II.Partitioning

### 1. d disk partou
```bash
unuser@deb:~$ sudo find / -name "bash" -type f
/etc/apparmor.d/abstractions/bash
/usr/bin/bash
/usr/share/menu/bash
/usr/share/lintian/overrides/bash
/usr/share/debianutils/shells.d/bash
```

on sait donc que bash se situe dans /usr/bin

```bash
unuser@deb:~$ du -h /usr/bin/bash && ls -i /usr/bin/bash
1.3M    /usr/bin/bash
131817 /usr/bin/bash
```

```bash
unuser@deb:~$ du -h /etc/passwd && ls -i /etc/passwd
4.0K    /etc/passwd
146546 /etc/passwd
```

```bash
unuser@deb:~$ lsblk
NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda           8:0    0   20G  0 disk
└─sda1        8:1    0   20G  0 part
  ├─ok-root 254:0    0  9.3G  0 lvm  /
  ├─ok-home 254:1    0  1.9G  0 lvm  /home
  ├─ok-swap 254:2    0  1.9G  0 lvm  [SWAP]
  └─ok-var  254:3    0  2.8G  0 lvm  /var
sdb           8:16   0   10G  0 disk
sdc           8:32   0   10G  0 disk
sr0          11:0    1 1024M  0 rom
```


```bash
unuser@deb:~$ sudo pvs
  PV         VG Fmt  Attr PSize   PFree
  /dev/sda1  ok lvm2 a--  <20.00g  4.17g
  /dev/sdb      lvm2 ---   10.00g 10.00g
  /dev/sdc      lvm2 ---   10.00g 10.00g
```

```bash
unuser@deb:~$ sudo vgs
  VG  #PV #LV #SN Attr   VSize   VFree
  cat   2   0   0 wz--n-  19.99g 19.99g
  ok    1   4   0 wz--n- <20.00g  4.17g
```

```bash
unuser@deb:~$ sudo lvs
  LV      VG  Attr       LSize  Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  meoooow cat -wi-a-----  3.00g
  home    ok  -wi-ao---- <1.86g
  root    ok  -wi-ao----  9.31g
  swap    ok  -wi-ao---- <1.86g
  var     ok  -wi-ao----  2.79g
```

```bash
unuser@deb:~$ df -h
Filesystem               Size  Used Avail Use% Mounted on
udev                     951M     0  951M   0% /dev
tmpfs                    197M  984K  196M   1% /run
/dev/mapper/ok-root      9.1G  3.6G  5.1G  42% /
tmpfs                    984M     0  984M   0% /dev/shm
tmpfs                    5.0M  8.0K  5.0M   1% /run/lock
/dev/mapper/ok-home      1.8G  3.4M  1.7G   1% /home
/dev/mapper/ok-var       2.7G  367M  2.2G  15% /var
tmpfs                    197M   48K  197M   1% /run/user/108
tmpfs                    197M   44K  197M   1% /run/user/1000
/dev/mapper/cat-meoooow  3.0G  5.8M  2.5G   1% /toto
```

j'ai choisi le btrfs car selon plusieurrs utilisateur il gacherai moins d'espace (de ce que j'ai compris si j'ai plusieurs fois le meme fichier il ne gardera l'espace que d'un seul)

```bash
unuser@deb:~$ sudo lvextend -L +2GB /dev/mapper/ok-home
  Size of logical volume ok/home changed from <1.86 GiB (476 extents) to <3.86 GiB (988 extents).
  Logical volume ok/home successfully resized.

  
unuser@deb:~$ sudo resize2fs /dev/mapper/ok-home
resize2fs 1.47.0 (5-Feb-2023)
Filesystem at /dev/mapper/ok-home is mounted on /home; on-line resizing required
old_desc_blocks = 1, new_desc_blocks = 1
The filesystem on /dev/mapper/ok-home is now 1011712 (4k) blocks long.
```

```bash
unuser@deb:~$ df -h
Filesystem               Size  Used Avail Use% Mounted on
udev                     951M     0  951M   0% /dev
tmpfs                    197M  984K  196M   1% /run
/dev/mapper/ok-root      9.1G  3.6G  5.1G  42% /
tmpfs                    984M     0  984M   0% /dev/shm
tmpfs                    5.0M  8.0K  5.0M   1% /run/lock
/dev/mapper/ok-home      3.8G  3.4M  3.6G   1% /home
/dev/mapper/ok-var       2.7G  367M  2.2G  15% /var
tmpfs                    197M   48K  197M   1% /run/user/108
tmpfs                    197M   44K  197M   1% /run/user/1000
/dev/mapper/cat-meoooow  3.0G  5.8M  2.5G   1% /toto
```


```bash
unuser@deb:~$ sudo btrfs filesystem resize max /toto/
Resize device id 1 (/dev/mapper/cat-meoooow) from 3.00GiB to max
unuser@deb:~$ df -h
Filesystem               Size  Used Avail Use% Mounted on
udev                     951M     0  951M   0% /dev
tmpfs                    197M  984K  196M   1% /run
/dev/mapper/ok-root      9.1G  3.6G  5.1G  42% /
tmpfs                    984M     0  984M   0% /dev/shm
tmpfs                    5.0M  8.0K  5.0M   1% /run/lock
/dev/mapper/ok-home      3.8G  3.4M  3.6G   1% /home
/dev/mapper/ok-var       2.7G  367M  2.2G  15% /var
tmpfs                    197M   48K  197M   1% /run/user/108
tmpfs                    197M   44K  197M   1% /run/user/1000
/dev/mapper/cat-meoooow   20G  5.8M   20G   1% /toto

```

```bash
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a
# device; this may be used with UUID= as a more robust way to name devices
# that works even if disks are added and removed. See fstab(5).
#
# systemd generates mount units based on this file, see systemd.mount(5).
# Please run 'systemctl daemon-reload' after making changes here.
#
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
/dev/mapper/ok-root /               ext4    errors=remount-ro 0       1
/dev/mapper/ok-home /home           ext4    defaults        0       2
/dev/mapper/ok-var /var            ext4    defaults        0       2
/dev/mapper/ok-swap none            swap    sw              0       0
/dev/sr0        /media/cdrom0   udf,iso9660 user,noauto     0       0
/dev/mapper/cat-meoooow /toto      btrfs      defaults 0 0
```

```bash
unuser@deb:~$ sudo mount -av
/                        : ignored
/home                    : already mounted
/var                     : already mounted
none                     : ignored
/media/cdrom0            : ignored
mount: (hint) your fstab has been modified, but systemd still uses
       the old version; use 'systemctl daemon-reload' to reload.
/toto                    : successfully mounted
```

et voila