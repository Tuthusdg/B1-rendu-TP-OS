# TP2 Terminal Linux

## 1. Fichiers

### A.find me

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

## 2. Users 

### A. Nouveau user
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