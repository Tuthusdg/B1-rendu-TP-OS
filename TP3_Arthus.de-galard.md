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
```