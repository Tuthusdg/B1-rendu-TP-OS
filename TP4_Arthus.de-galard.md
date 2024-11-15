#  TP4 

## Verification

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