# Level 19 al 20

## Objetivo.

Para obtener acceso al siguiente nivel, debe usar el binario setUid en el Homedirectory. Ejecutarlo sin argumentos para averiguar cómo usarlo. La contraseña para este nivel se puede encontrar en el lugar habitual (/etc/bandit_pass), después de haber usado el binario setUid.

## Datos de acceso al nivel.

bandit19
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Solución.

bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Feb 21 22:03 .
drwxr-xr-x 70 root     root      4096 Feb 21 22:04 ..
-rwsr-x---  1 bandit20 bandit19 14876 Feb 21 22:03 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$  ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$  ./bandit20-do ls /etc/bandit_pass
bandit0   bandit11  bandit14  bandit17  bandit2   bandit22  bandit25  bandit28  bandit30  bandit33  bandit6  bandit9
bandit1   bandit12  bandit15  bandit18  bandit20  bandit23  bandit26  bandit29  bandit31  bandit4   bandit7
bandit10  bandit13  bandit16  bandit19  bandit21  bandit24  bandit27  bandit3   bandit32  bandit5   bandit8
bandit19@bandit:~$  ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Notas opcionales.

## Referencias.