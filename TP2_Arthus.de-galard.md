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