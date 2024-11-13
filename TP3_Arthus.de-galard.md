# TP3 permissions

## Partie I 

### 1.liste des users

```bash
unuser@TPOS:/etc$ cat passwd | grep unuser
unuser:x:1000:1000:unuser,,,:/home/unuser:/bin/bash
```

```bash
unuser@TPOS:/etc$ cat passwd | grep -E "unuser|root"
root:x:0:0:root:/root:/bin/bash
unuser:x:1000:1000:unuser,,,:/home/unuser:/bin/bash
```

```bash
unuser@TPOS:/etc$ cat group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:
tty:x:5:
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:unuser
floppy:x:25:unuser
tape:x:26:
sudo:x:27:unuser
audio:x:29:pulse,unuser
dip:x:30:unuser
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
shadow:x:42:
utmp:x:43:
video:x:44:unuser
sasl:x:45:
plugdev:x:46:unuser
staff:x:50:
games:x:60:
users:x:100:unuser
nogroup:x:65534:
systemd-journal:x:999:
systemd-network:x:998:
crontab:x:101:
input:x:102:
sgx:x:103:
kvm:x:104:
render:x:105:
netdev:x:106:unuser
systemd-timesync:x:997:
messagebus:x:107:
_ssh:x:108:
ssl-cert:x:109:
avahi-autoipd:x:110:
bluetooth:x:111:unuser
avahi:x:112:
lpadmin:x:113:unuser
pulse:x:114:
pulse-access:x:115:
scanner:x:116:saned,unuser
saned:x:117:
lightdm:x:118:
polkitd:x:996:
rtkit:x:119:
colord:x:120:
unuser:x:1000:
```

```bash
cat passwd | cut -d":" -f1,3 | grep -E "unuser|root"
root:0
unuser:1000
```

```bash
unuser@TPOS:/etc$ cat passwd | cut -d":" -f1,6 | grep -E "unuser|root"
root:/root
unuser:/home/unuser
```
### 2. Hash des passwords
```bash 
unuser@TPOS:/etc$ sudo cat /etc/shadow | grep unuser | cut -d":" -f1,2
unuser:$y$j9T$bc3CecNMtXN6l0mPobHVU/$0AHmJQH6.daXKXddnq5j7bA8oZM9k2ZGs42SAi/jyG7
```

### 3.Sudo

#### B. Practice

```bash
unuser@TPOS:/etc$ sudo addgroup stronk_admins
Adding group `stronk_admins' (GID 1001) ...
Done.

```

```bash
unuser@TPOS:/etc$ sudo adduser imbob
Adding user `imbob' ...
Adding new group `imbob' (1002) ...
Adding new user `imbob' (1002) with group `imbob (1002)' ...
Creating home directory `/home/imbob' ...
Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for imbob
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n] Y
Adding new user `imbob' to supplemental / extra groups `users' ...
Adding user `imbob' to group `users' ...
```

```bash
unuser@TPOS:~$ sudo usermod -a -G stronk_admins imbob
```

```bash
unuser@TPOS:~$ cat /etc/passwd | grep imbob
imbob:x:1002:1002:,,,:/home/imbob:/bin/bash
```

```bash
unuser@TPOS:~$ sudo cat /etc/shadow | grep imbob
imbob:$y$j9T$ivjCqcF8pIPOIsqIVdhmg1$3NfoQGszBeF.b1a5asKMiXqF37UeQFLvL0DZWrAOEJ1:20039:0:99999:7:::
```


```bash 
unuser@TPOS:~$ cat /etc/group | grep stronk_admins
stronk_admins:x:1001:imbob
```



```bash
unuser@TPOS:~$ cat /etc/passwd | grep imnotbobsorry
imnotbobsorry:x:1003:1003::/home/imnotbobsorry:/bin/bash

unuser@TPOS:~$ cat /etc/group | grep imnotbobsorry
imnotbobsorry:x:1003:
```

```bash
unuser@TPOS:~$ sudo usermod -a -G sudo imbob
```


```bash
unuser@TPOS:/home$ sudo usermod -d /home/goodguy imbob
unuser@TPOS:/home$ cat /etc/passwd | grep imbob
imbob:x:1002:1002:,,,:/home/goodguy:/bin/bash
```
```bash
unuser@TPOS:~$ sudo usermod -d /home/badguy imnotbobsorry
unuser@TPOS:~$ unuser@TPOS:~$ cat /etc/passwd | grep imnotbobsorry
imnotbobsorry:x:1003:1003::/home/badguy:/bin/bash
```

```bash
drwxr-xr-x  5 root          root          4096 Nov 12 12:34 .
drwxr-xr-x 19 root          root          4096 Nov  6 11:49 ..
drwxr-xr-x  2 root          root          4096 Nov 12 12:21 goodguy
drwx------  2 imnotbobsorry imnotbobsorry 4096 Nov 12 12:32 imnotbobsorry
drwx------ 16 unuser        unuser        4096 Nov 12 11:07 unuser
```
on peut voir ici que le dossier goodguy est posséder par root   

```bash
unuser@TPOS:/home$ sudo chown imbob goodguy
unuser@TPOS:/home$ ls -la
total 20
drwxr-xr-x  5 root          root          4096 Nov 12 12:34 .
drwxr-xr-x 19 root          root          4096 Nov  6 11:49 ..
drwxr-xr-x  2 imbob         root          4096 Nov 12 12:21 goodguy
drwx------  2 imnotbobsorry imnotbobsorry 4096 Nov 12 12:32 imnotbobsorry
drwx------ 16 unuser        unuser        4096 Nov 12 11:07 unuser
```


```bash
unuser@TPOS:~$ sudo chown imnotbobsorry /home/badguy/
unuser@TPOS:/home$ ls -la
total 20
drwxr-xr-x  5 root          root   4096 Nov 12 12:56 .
drwxr-xr-x 19 root          root   4096 Nov  6 11:49 ..
drwxr-xr-x  2 imnotbobsorry root   4096 Nov 12 12:48 badguy
drwxr-xr-x  2 imbob         root   4096 Nov 12 12:47 goodguy
drwx------ 16 unuser        unuser 4096 Nov 12 11:07 unuser
```


```bash 
imbob@TPOS:~$ cd
imbob@TPOS:~$ pwd
/home/goodguy
```

```bash
imbob@TPOS:~$ sudo echo meow
meow
```

```bash
imnotbobsorry@TPOS:/home/unuser$ cd
imnotbobsorry@TPOS:~$ pwd
/home/badguy
```

```bash 
imnotbobsorry@TPOS:~$ sudo echo meow
[sudo] password for imnotbobsorry:
imnotbobsorry is not in the sudoers file.
```

```bash
imnotbobsorry@TPOS:~$ pwd
/home/badguy

imnotbobsorry@TPOS:~$ sudo apt update
[sudo] password for imnotbobsorry:
Hit:1 http://security.debian.org/debian-security bookworm-security InRelease
Hit:2 http://deb.debian.org/debian bookworm InRelease
Get:3 http://deb.debian.org/debian bookworm-updates InRelease [55.4 kB]
Fetched 55.4 kB in 1s (82.5 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
66 packages can be upgraded. Run 'apt list --upgradable' to see them.
```


## Partie II  
### 1.Jouer avec la commande ps 
```bash
unuser@TPOS:~$ ps |grep bash
    737 pts/0    00:00:00 bash
```


```bash
unuser@TPOS:~$ ps -ef | grep "unuser   "
unuser       711       1  0 07:53 ?        00:00:00 /lib/systemd/systemd --user
unuser       712     711  0 07:53 ?        00:00:00 (sd-pam)
unuser       729     711  0 07:53 ?        00:00:00 /usr/bin/pulseaudio --daemonize=no --log-target=journal
unuser       732     708  0 07:53 ?        00:00:00 sshd: unuser@pts/0
unuser       737     732  0 07:53 pts/0    00:00:00 -bash
unuser       785     711  0 07:53 ?        00:00:00 /usr/bin/dbus-daemon --session --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
unuser      1057     737  0 07:59 pts/0    00:00:00 ps -ef
unuser      1058     737  0 07:59 pts/0    00:00:00 grep unuser
```

```bash
unuser@TPOS:~$ ps aux --sort -%mem |head -5
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
lightdm      656  0.1 11.7 616220 115368 ?       Ssl  07:53   0:00 /usr/sbin/lightdm-gtk-greeter
root         603  0.1  7.7 353528 76196 tty7     Ssl+ 07:53   0:00 /usr/lib/xorg/Xorg :0 -seat seat0 -auth /var/run/lightdm/root/:0 -nolisten tcp vt7 -novtswitch
root         216  0.0  2.3  65848 23472 ?        Ss   07:53   0:00 /lib/systemd/systemd-journald
root         442  0.0  2.1 258468 21440 ?        Ssl  07:53   0:00 /usr/sbin/NetworkManager --no-daemon
```

```bash
unuser@TPOS:~$ ps -ef --sort -pid | grep sshd | tail -1
root         598       1  0 07:53 ?        00:00:00 sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups
```

```bash
unuser@TPOS:~$ ps -ef --sort -pid | tail -1
root           1       0  0 07:52 ?        00:00:00 /sbin/init
```

### 2.Parent, enfant et meurtre

```bash
unuser@TPOS:~$ ps -ef | grep "bash   "
unuser      1093     737  0 08:10 pts/0    00:00:00 grep bash
```

```bash
unuser@TPOS:~$ ps -ef --sort -pid | grep bash | tail -1
unuser       737     732  0 07:53 pts/0    00:00:00 -bash
```

le ppid de mon terminal est donc 732

```bash
unuser@TPOS:~$ ps -p 732
    PID TTY          TIME CMD
    732 ?        00:00:00 sshd
```

son nom est donc sshd

```bash
unuser@TPOS:~$ ps -ef | grep sleep | head -1
unuser      1253     737  0 09:21 pts/0    00:00:00 sleep 999999
```

on voit que le ppid est 737 soit l'id du bash

```bash
unuser@TPOS:~$ ps -ef | grep sleep | head -1
unuser      1253       1  0 09:21 ?        00:00:00 sleep 999999
```

Donc le processus est encore en cours d'execution


## Partie III 

### 2. analyser  un service existant

```bash
unuser@TPOS:~$ systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/lib/systemd/system/ssh.service; enabled; preset: enabled)
     Active: active (running) since Wed 2024-11-13 07:53:04 CET; 2h 2min ago
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 588 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
   Main PID: 598 (sshd)
      Tasks: 1 (limit: 1077)
     Memory: 5.5M
        CPU: 300ms
     CGroup: /system.slice/ssh.service
             └─598 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"
```

