# Level 30 al 31

## Objetivo.

Hay un repositorio de git en ssh://bandit30-git@localhost/home/bandit30-git/repo. La contraseña para el usuario bandit30-git es la misma que para el usuario bandit30.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel.

bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución.

bandit29@bandit:~$ 
/tmp/tmp.5fXimVYant
bandit29@bandit:~$ cd /tmp/tmp.5fXimVYant
bandit29@bandit:/tmp/tmp.5fXimVYant$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
Permission denied, please try again.
bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.5fXimVYant$ ls
repo
bandit29@bandit:/tmp/tmp.5fXimVYant$ cd repo/
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Mar  6 03:27 .
drwx------ 3 bandit29 bandit29 4096 Mar  6 03:27 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Mar  6 03:27 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Mar  6 03:27 README.md
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30

bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ ls -la
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Mar  6 03:29 .
drwx------ 3 bandit29 bandit29 4096 Mar  6 03:27 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Mar  6 03:29 code
drwxrwxr-x 8 bandit29 bandit29 4096 Mar  6 03:29 .git
-rw-rw-r-- 1 bandit29 bandit29  134 Mar  6 03:29 README.md
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ logout
Connection to bandit.labs.overthewire.org closed.
PS C:\Users\Acer> ssh bandit30@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30@bandit.labs.overthewire.org's password:

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

 Both python2 and python3 are installed.

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit30@bandit:~$ mktemp -d
/tmp/tmp.gHrnAGLL4N
bandit30@bandit:~$ cd /tmp/tmp.gHrnAGLL4N
bandit30@bandit:/tmp/tmp.gHrnAGLL4N$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/tmp.gHrnAGLL4N$ ls
repo
bandit30@bandit:/tmp/tmp.gHrnAGLL4N$ cd repo
bandit30@bandit:/tmp/tmp.gHrnAGLL4N/repo$ ls -la
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Mar  6 03:37 .
drwx------ 3 bandit30 bandit30 4096 Mar  6 03:37 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Mar  6 03:37 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Mar  6 03:37 README.md
bandit30@bandit:/tmp/tmp.gHrnAGLL4N/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.gHrnAGLL4N/repo$ git tag
secret
bandit30@bandit:/tmp/tmp.gHrnAGLL4N/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Notas opcionales.

El etiquetado de Git es una forma de marcar puntos específicos en la historia del repositorio. Un ejemplo sería marcar puntos de lanzamiento del software. El comando para ver las etiquetas es git tag. Para crear una etiqueta, el comando es git tag -a <tag_name> -m <"tag description/message">.

## Referencias.

https://overthewire.org/wargames/bandit/bandit31.html
https://mayadevbe.me/posts/overthewire/bandit/level31/