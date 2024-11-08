# TP2 Terminal Linux

## Partie II

### 1. Fichiers

#### A.find me

Chemin vers repertoire personnel
```bash
unuser@TPOS:~$ cd /home/
unuser@TPOS:/home$ ls -l
total 4
drwx------ 16 unuser unuser 4096 Nov  7 10:44 unuser
```
trouver le chemin du fichier ssh

```bash
root@TPOS:/home/unuser# find / -name "sshd_config"
/usr/share/openssh/sshd_config
find: ‘/run/user/1000/doc’: Permission denied
/etc/ssh/sshd_config
```

### 2. Users 

#### A. Nouveau user
```bash
unuser@TPOS:~$ sudo useradd -m marmotte -s /bin/bash
unuser@TPOS:~$ cd /
unuser@TPOS:/$ cd home/
unuser@TPOS:/home$ ls
marmotte  unuser
unuser@TPOS:/home$ sudo passwd marmotte
New password:
Retype new password:
passwd: password updated successfully
unuser@TPOS:/home$ su marmotte
Password:
marmotte@TPOS:/home$
```

#### B.Info enregistré par le système

```bash
unuser@TPOS:/etc$ cat passwd | grep marmotte
marmotte:x:1001:1001::/home/marmotte:/bin/bash
```
hash password de marmotte

```bash
root@TPOS:/etc# cat shadow | grep marmotte
marmotte:$y$j9T$4mA3BHiM16wKRvPL7bqPW/$9IpeM6Sw02p7kUZKfeO6AzSSjCHcJUESRXOGoDl7OM2:20034:0:99999:7:::
```

#### D.Connexion sur le nouvel utilisateur

```bash
marmotte@TPOS:/home/unuser$ exit
exit
unuser@TPOS:~$
```

le mechant permission denied

```bash
marmotte@TPOS:~$ ls /home/unuser/
ls: cannot open directory '/home/unuser/': Permission denied
```

## Partie III

#### A.Run the kill

```bash 
unuser@TPOS:~$ sleep 1000
```

pendant ce temp la dans un autre Terminal

``` bash
unuser@TPOS:~$ ps -fe | grep sleep
unuser      7020    6515  0 17:31 pts/1    00:00:00 sleep 1000
unuser      7073    7036  0 17:31 pts/0    00:00:00 grep sleep
unuser@TPOS:~$ kill 7020
```

et paf 
```bash
unuser@TPOS:~$ sleep 1000
Terminated
``` 

#### B.Tâche de fond

```bash
unuser@TPOS:~$ sleep 1000
Terminated
unuser@TPOS:~$ sleep 1000 &
[1] 7335
unuser@TPOS:~$ ps -fe | grep sleep
unuser      7335    6515  0 17:36 pts/1    00:00:00 sleep 1000
unuser      7337    6515  0 17:36 pts/1    00:00:00 grep sleep
```

son PID est donc 7335


#### C.Find paths

```bash
root@TPOS:~# find / -name "sleep"
/usr/lib/klibc/bin/sleep
/usr/bin/sleep
find: ‘/run/user/1000/doc’: Permission denied
```

```bash
root@TPOS:~# find / -name "*.bashrc"
/root/.bashrc
/usr/share/doc/adduser/examples/adduser.local.conf.examples/skel/dot.bashrc
/usr/share/doc/adduser/examples/adduser.local.conf.examples/bash.bashrc
/usr/share/base-files/dot.bashrc
find: ‘/run/user/1000/doc’: Permission denied
/etc/skel/.bashrc
/etc/bash.bashrc
/home/unuser/.bashrc
/home/unuser/Documents/gameshell/gameshell/World/.bashrc
/home/marmotte/.bashrc
```

#### D.La variable PATH 

```bash
root@TPOS:~# find / -name "ping"
/usr/share/bash-completion/completions/ping
/usr/bin/ping
find: ‘/run/user/1000/doc’: Permission denied
root@TPOS:~#
root@TPOS:~#
root@TPOS:~# find / -name "ssh"
/var/log/runit/ssh
/usr/share/bash-completion/completions/ssh
/usr/share/runit/meta/ssh
/usr/lib/apt/methods/ssh
/usr/bin/ssh
/run/user/108/gcr/ssh
/run/user/1001/gcr/ssh
find: ‘/run/user/1000/doc’: Permission denied
/run/user/1000/gcr/ssh
/etc/sv/ssh
/etc/ssh
/etc/init.d/ssh
/etc/runit/runsvdir/default/ssh
/etc/default/ssh
root@TPOS:~#
root@TPOS:~#
root@TPOS:~# find / -name "sleep"
/usr/lib/klibc/bin/sleep
/usr/bin/sleep
find: ‘/run/user/1000/doc’: Permission denied
root@TPOS:~#
root@TPOS:~#
root@TPOS:~# echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
```

on peut voir qu'ils sont tous dans usr/bin donc oui ils sont tous dans le PATH

```bash
root@TPOS:~# find / -name "git"
/var/lib/git
/usr/share/doc/git
/usr/share/lintian/overrides/git
/usr/share/bash-completion/completions/git
/usr/lib/git-core/git
/usr/bin/git
```

Pareil on peut voir que le programme git est stocké dans usr/bin

```bash
unuser@TPOS:/etc/apt$ cat sources.list
#deb cdrom:[Debian GNU/Linux 12.7.0 _Bookworm_ - Official amd64 NETINST with firmware 20240831-10:38]/ bookworm contrib main non-free-firmware

deb http://deb.debian.org/debian/ bookworm main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm main non-free-firmware

deb http://security.debian.org/debian-security bookworm-security main non-free-firmware
deb-src http://security.debian.org/debian-security bookworm-security main non-free-firmware

# bookworm-updates, to get updates before a point release is made;
# see https://www.debian.org/doc/manuals/debian-reference/ch02.en.html#_updates_and_backports
deb http://deb.debian.org/debian/ bookworm-updates main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm-updates main non-free-firmware

# This system was installed using small removable media
# (e.g. netinst, live or single CD). The matching "deb cdrom"
# entries were disabled at the end of the installation process.
# For information about how to configure apt package sources,
# see the sources.list(5) manual.
```

## Partie IV

recup fichier 
```bash
unuser@TPOS:~/Downloads$ wget https://gitlab.com/it4lik/b1-os/-/raw/main/tp/2/meow
--2024-11-08 12:23:03--  https://gitlab.com/it4lik/b1-os/-/raw/main/tp/2/meow
Resolving gitlab.com (gitlab.com)... 172.65.251.78, 2606:4700:90:0:f22e:fbec:5bed:a9b9
Connecting to gitlab.com (gitlab.com)|172.65.251.78|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18016947 (17M) [application/octet-stream]
Saving to: ‘meow’

meow               100%[================>]  17.18M  7.67MB/s    in 2.2s

2024-11-08 12:23:06 (7.67 MB/s) - ‘meow’ saved [18016947/18016947]
```

decompression du fichier
```bash
unuser@TPOS:~/Downloads$ unzip meow.zip
Archive:  meow.zip
  inflating: meow
unuser@TPOS:~/Downloads$ ls
meow  meow.zip
unuser@TPOS:~/Downloads$ cd meow
-bash: cd: meow: Not a directory
unuser@TPOS:~/Downloads$ file meow
meow: XZ compressed data, checksum CRC64
unuser@TPOS:~/Downloads$ tar -xf meow
tar: This does not look like a tar archive
tar: Skipping to next header
tar: Exiting with failure status due to previous errors
unuser@TPOS:~/Downloads$ rm meow.zip
unuser@TPOS:~/Downloads$ ls
meow
unuser@TPOS:~/Downloads$ mv meow meow.xz
unuser@TPOS:~/Downloads$ ls
meow.xz
unuser@TPOS:~/Downloads$ tar -xf meow.xz
tar: This does not look like a tar archive
tar: Skipping to next header
tar: Exiting with failure status due to previous errors
unuser@TPOS:~/Downloads$ ls
meow.xz
unuser@TPOS:~/Downloads$ mv meow.xz meow
unuser@TPOS:~/Downloads$ file meow
meow: XZ compressed data, checksum CRC64
unuser@TPOS:~/Downloads$ mv meow meow.xz
unuser@TPOS:~/Downloads$ ls
meow.xz
unuser@TPOS:~/Downloads$ xz -d meow.xz
unuser@TPOS:~/Downloads$ ls
meow
unuser@TPOS:~/Downloads$ file meow
meow: bzip2 compressed data, block size = 900k
unuser@TPOS:~/Downloads$ mv meow meow.bz2
unuser@TPOS:~/Downloads$ ls
meow.bz2
unuser@TPOS:~/Downloads$ bzip2 -d meow.bz2
unuser@TPOS:~/Downloads$ ls
meow
unuser@TPOS:~/Downloads$ file meow
meow: RAR archive data, v5
unuser@TPOS:~/Downloads$ unrar
-bash: unrar: command not found
unuser@TPOS:~/Downloads$ unar
-bash: unar: command not found
unuser@TPOS:~/Downloads$ sudo apt update
[sudo] password for unuser:
Hit:1 http://deb.debian.org/debian bookworm InRelease
Get:2 http://deb.debian.org/debian bookworm-updates InRelease [55.4 kB]
Get:3 http://security.debian.org/debian-security bookworm-security InRelease [48.0 kB]
Get:4 http://security.debian.org/debian-security bookworm-security/main Sources [126 kB]
Get:5 http://security.debian.org/debian-security bookworm-security/main amd64 Packages [190 kB]
Fetched 420 kB in 3s (156 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
6 packages can be upgraded. Run 'apt list --upgradable' to see them.
unuser@TPOS:~/Downloads$ sudo pat upgrade
sudo: pat: command not found
unuser@TPOS:~/Downloads$ sudo apt upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
The following packages will be upgraded:
  gir1.2-javascriptcoregtk-4.0 gir1.2-webkit2-4.0
  libjavascriptcoregtk-4.0-18 libjavascriptcoregtk-4.1-0
  libwebkit2gtk-4.0-37 libwebkit2gtk-4.1-0
6 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
Need to get 62.2 MB of archives.
After this operation, 127 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://security.debian.org/debian-security bookworm-security/main amd64 gir1.2-webkit2-4.0 amd64 2.46.3-1~deb12u1 [106 kB]
Get:2 http://security.debian.org/debian-security bookworm-security/main amd64 gir1.2-javascriptcoregtk-4.0 amd64 2.46.3-1~deb12u1 [49.9 kB]
Get:3 http://security.debian.org/debian-security bookworm-security/main amd64 libwebkit2gtk-4.0-37 amd64 2.46.3-1~deb12u1 [23.2 MB]
Get:4 http://security.debian.org/debian-security bookworm-security/main amd64 libjavascriptcoregtk-4.0-18 amd64 2.46.3-1~deb12u1 [7,832 kB]
Get:5 http://security.debian.org/debian-security bookworm-security/main amd64 libwebkit2gtk-4.1-0 amd64 2.46.3-1~deb12u1 [23.2 MB]
Get:6 http://security.debian.org/debian-security bookworm-security/main amd64 libjavascriptcoregtk-4.1-0 amd64 2.46.3-1~deb12u1 [7,831 kB]
Fetched 62.2 MB in 4s (14.1 MB/s)
Reading changelogs... Done
(Reading database ... 114989 files and directories currently installed.)
Preparing to unpack .../0-gir1.2-webkit2-4.0_2.46.3-1~deb12u1_amd64.deb ...
Unpacking gir1.2-webkit2-4.0:amd64 (2.46.3-1~deb12u1) over (2.46.0-2~deb12u1) ...
Preparing to unpack .../1-gir1.2-javascriptcoregtk-4.0_2.46.3-1~deb12u1_amd64.deb ...
Unpacking gir1.2-javascriptcoregtk-4.0:amd64 (2.46.3-1~deb12u1) over (2.46.0-2~deb12u1) ...
Preparing to unpack .../2-libwebkit2gtk-4.0-37_2.46.3-1~deb12u1_amd64.deb ...
Unpacking libwebkit2gtk-4.0-37:amd64 (2.46.3-1~deb12u1) over (2.46.0-2~deb12u1) ...
Preparing to unpack .../3-libjavascriptcoregtk-4.0-18_2.46.3-1~deb12u1_amd64.deb ...
Unpacking libjavascriptcoregtk-4.0-18:amd64 (2.46.3-1~deb12u1) over (2.46.0-2~deb12u1) ...
Preparing to unpack .../4-libwebkit2gtk-4.1-0_2.46.3-1~deb12u1_amd64.deb ...
Unpacking libwebkit2gtk-4.1-0:amd64 (2.46.3-1~deb12u1) over (2.46.0-2~deb12u1) ...
Preparing to unpack .../5-libjavascriptcoregtk-4.1-0_2.46.3-1~deb12u1_amd64.deb ...
Unpacking libjavascriptcoregtk-4.1-0:amd64 (2.46.3-1~deb12u1) over (2.46.0-2~deb12u1) ...
Setting up libjavascriptcoregtk-4.0-18:amd64 (2.46.3-1~deb12u1) ...
Setting up gir1.2-javascriptcoregtk-4.0:amd64 (2.46.3-1~deb12u1) ...
Setting up libjavascriptcoregtk-4.1-0:amd64 (2.46.3-1~deb12u1) ...
Setting up libwebkit2gtk-4.0-37:amd64 (2.46.3-1~deb12u1) ...
Setting up libwebkit2gtk-4.1-0:amd64 (2.46.3-1~deb12u1) ...
Setting up gir1.2-webkit2-4.0:amd64 (2.46.3-1~deb12u1) ...
Processing triggers for libc-bin (2.36-9+deb12u8) ...
unuser@TPOS:~/Downloads$ sudo apt install unrar
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package unrar is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'unrar' has no installation candidate
unuser@TPOS:~/Downloads$ sudo apt update && sudo apt install unrar
Hit:1 http://security.debian.org/debian-security bookworm-security InRelease
Hit:2 http://deb.debian.org/debian bookworm InRelease
Hit:3 http://deb.debian.org/debian bookworm-updates InRelease
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
All packages are up to date.
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package unrar is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'unrar' has no installation candidate
unuser@TPOS:~/Downloads$ sudo apt-add-repository contrib non-free
sudo: apt-add-repository: command not found
unuser@TPOS:~/Downloads$ sudo apt-add-repository contrib non-free
sudo: apt-add-repository: command not found
unuser@TPOS:~/Downloads$ sudo apt install unrar
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package unrar is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'unrar' has no installation candidate
unuser@TPOS:~/Downloads$ sudo apt install unrar-free
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Suggested packages:
  pike8.0
The following NEW packages will be installed:
  unrar-free
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 16.5 kB of archives.
After this operation, 60.4 kB of additional disk space will be used.
Get:1 http://deb.debian.org/debian bookworm/main amd64 unrar-free amd64 1:0.1.3-1 [16.5 kB]
Fetched 16.5 kB in 0s (151 kB/s)
Selecting previously unselected package unrar-free.
(Reading database ... 114989 files and directories currently installed.)
Preparing to unpack .../unrar-free_1%3a0.1.3-1_amd64.deb ...
Unpacking unrar-free (1:0.1.3-1) ...
Setting up unrar-free (1:0.1.3-1) ...
update-alternatives: using /usr/bin/unrar-free to provide /usr/bin/unrar (unrar) in auto mode
Processing triggers for man-db (2.11.2-2) ...
unuser@TPOS:~/Downloads$ ls
meow
unuser@TPOS:~/Downloads$ mv meow meow.rar
unuser@TPOS:~/Downloads$ unrar
unrar: Archive not specified

Try `unrar-free --help' or `unrar-free --usage' for more information.
unuser@TPOS:~/Downloads$ unrar meow.rar

unrar-free 0.1.3  Copyright (C) 2004  Ben Asselstine, Jeroen Dekkers


Extracting from /home/unuser/Downloads/meow.rar

Extracting  meow                                                      OK

All OK
unuser@TPOS:~/Downloads$ ls
meow  meow.rar
unuser@TPOS:~/Downloads$ rm meow.rar
unuser@TPOS:~/Downloads$ file meow
meow: gzip compressed data, from Unix, original size modulo 2^32 145049600 gzip compressed data, reserved method, has CRC, extra field, has comment, from FAT filesystem (MS-DOS, OS/2, NT), original size modulo 2^32 145049600
unuser@TPOS:~/Downloads$ mv meow meow.gzip
unuser@TPOS:~/Downloads$ ls
meow.gzip
unuser@TPOS:~/Downloads$ mv meow.gzip meow.gz
unuser@TPOS:~/Downloads$ gzip -d meow.gz
unuser@TPOS:~/Downloads$ ls
meow
unuser@TPOS:~/Downloads$ file meow
meow: POSIX tar archive (GNU)
unuser@TPOS:~/Downloads$ mv meow meow.tar
unuser@TPOS:~/Downloads$ tar -xf meow.tar
unuser@TPOS:~/Downloads$ ls
dawa  meow.tar
```

```bash
unuser@TPOS:~/Downloads/dawa$ find ~/Downloads/dawa/ -size 15M
/home/unuser/Downloads/dawa/folder31/19/file39
```

```bash
unuser@TPOS:~/Downloads/dawa$ grep -rnw ~/Downloads/dawa/ -e "77777*"
/home/unuser/Downloads/dawa/folder43/38/file41:1:77777777777
```

```bash
unuser@TPOS:~/Downloads/dawa$ find ~/Downloads/dawa/ -name "cookie"
/home/unuser/Downloads/dawa/folder14/25/cookie
```

```bash
unuser@TPOS:~/Downloads/dawa$ find ~/Downloads/dawa/ -name ".*"
/home/unuser/Downloads/dawa/folder32/14/.hidden_file
```