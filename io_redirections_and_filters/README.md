# SHELL, I/O REDIRECTIONS AND FILTERS

## Résumé:


Le Shell, la redirection d'E/S, et les filtres sont des concepts essentiels en programmation et administration système.

1. Shell :

* Le Shell est une interface en ligne de commande permettant aux utilisateurs d'interagir avec le système d'exploitation en saisissant des commandes.
* Il offre un environnement pour l'exécution de scripts, la gestion des processus, et la manipulation des fichiers.

2. Redirection d'E/S :

* La redirection d'E/S permet de gérer le flux d'entrée/sortie des commandes.
* Les opérateurs tels que >, <, et | sont utilisés pour rediriger la sortie vers un fichier, lire l'entrée depuis un fichier, ou connecter la sortie d'une commande à l'entrée d'une autre.

3. Filtres :

* Les filtres sont des commandes qui traitent ou modifient le flux de données.
* Des commandes courantes, comme grep, sed, et awk, sont utilisées pour filtrer, rechercher, et transformer des données textuelles.

En résumé, le Shell offre une interface puissante pour interagir avec le système. La redirection d'E/S permet de contrôler le flux des données, tandis que les filtres facilitent le traitement et la manipulation des données. Ces concepts sont fondamentaux pour la programmation et l'administration système.

## Resources:
* [Shell, I/O Redirection](https://linuxcommand.org/lc3_lts0070.php)
* [Special Characters](https://mywiki.wooledge.org/BashGuide/SpecialCharacters)

## Requirements:

* Allowed editors: vi, vim, emacs
* All your scripts will be tested on Ubuntu 20.04 LTS
* All your scripts should be exactly two lines long ($ wc -l file should print 2)
* All your files should end with a new line (why?)
* The first line of all your files should be exactly #!/bin/bash
* A README.md file, at the root of the folder of the project, describing what each script is doing
* You are not allowed to use backticks, &&, || or ;
* All your files must be executable
* You are not allowed to use sed or awk

## TASKS: 

### 0. Hello World
Write a script that prints “Hello, World”, followed by a new line to the standard output.

```bash
mathieu@ubuntu:/tmp/h$ ./0-hello_world 
Hello, World
mathieu@ubuntu:/tmp/h$ ./0-hello_world | cat -e
Hello, World$
```

### 1. Confused smiley
Write a script that displays a confused smiley "(Ôo)'.

```bash
mathieu@ubuntu:/tmp/h$ ./1-confused_smiley 
"(Ôo)'
```

### 2. Let's display a file
Display the content of the /etc/passwd file.

```bash
$ ./2-hellofile
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
_installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
_lp:*:26:26:Printing Services:/var/spool/cups:/usr/bin/false
_postfix:*:27:27:Postfix Mail Server:/var/spool/postfix:/usr/bin/false
_scsd:*:31:31:Service Configuration Service:/var/empty:/usr/bin/false
_ces:*:32:32:Certificate Enrollment Service:/var/empty:/usr/bin/false
_mcxalr:*:54:54:MCX AppLaunch:/var/empty:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
$
```

### 3. What about 2?
Display the content of /etc/passwd and /etc/hosts

```bash
$ ./3-twofiles
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting. Do not change this entry.
##
127.0.0.1   localhost
255.255.255.255 broadcasthost
::1 localhost
$
```

### 4. Last lines of a file
Display the last 10 lines of /etc/passwd

```bash
$ ./4-lastlines
_assetcache:*:235:235:Asset Cache Service:/var/empty:/usr/bin/false
_coremediaiod:*:236:236:Core Media IO Daemon:/var/empty:/usr/bin/false
_launchservicesd:*:239:239:_launchservicesd:/var/empty:/usr/bin/false
_iconservices:*:240:240:IconServices:/var/empty:/usr/bin/false
_distnote:*:241:241:DistNote:/var/empty:/usr/bin/false
_nsurlsessiond:*:242:242:NSURLSession Daemon:/var/db/nsurlsessiond:/usr/bin/false
_nsurlstoraged:*:243:243:NSURLStorage Daemon:/var/empty:/usr/bin/false
_displaypolicyd:*:244:244:Display Policy Daemon:/var/empty:/usr/bin/false
_astris:*:245:245:Astris Services:/var/db/astris:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
```

### 5. I'd prefer the first ones actually
Display the first 10 lines of /etc/passwd

```bash
$ ./5-firstlines
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
$
```

### 6. Line #2
Write a script that displays the third line of the file iacta.

The file iacta will be in the working directory

You’re not allowed to use sed

```bash
mathieu@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
mathieu@ubuntu:/tmp/h$ ./6-third_line 
Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
```

### 7. It is a good file that cuts iron without making a noise
Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.

```bash
mathieu@ubuntu:~/shell$ ls && ./7-file && ls -l && cat -e \\*
0-mac_and_cheese 7-file 7-file~ Makefile
total 20
-rwxrw-r-- 1 mathieu mathieu 79 Jan 20 06:24 0-mac_and_cheese
-rwxrw-r-- 1 mathieu mathieu 90 Jan 20 06:40 7-file
-rwxrw-r-- 1 mathieu mathieu 69 Jan 20 06:37 7-file~
-rw-rw-r-- 1 mathieu mathieu 14 Jan 20 06:38 Makefile
-rw-rw-r-- 1 mathieu mathieu 17 Jan 20 06:40 '\*\\'"Best School"\'\\*$\?\*\*\*\*\*:)'
Best School$
```

### 8. Save current state of directory
Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.

```bash
mathieu@ubuntu:/tmp/h$ ls -la
total 20
drwxrwxr-x  2 mathieu mathieu 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 mathieu mathieu   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  mathieu   23 Sep 20 14:25 hello
-rw-rw-r--  1 mathieu mathieu  926 Sep 20 17:52 iacta

mathieu@ubuntu:/tmp/h$ ./8-cwd_state 
mathieu@ubuntu:/tmp/h$ ls -la
total 24
drwxrwxr-x  2 mathieu mathieu 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 mathieu mathieu   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  mathieu   23 Sep 20 14:25 hello
-rw-rw-r--  1 mathieu mathieu  926 Sep 20 17:52 iacta
-rw-rw-r--  1 mathieu mathieu  329 Sep 20 18:18 ls_cwd_content

mathieu@ubuntu:/tmp/h$ cat ls_cwd_content 
total 20
drwxrwxr-x  2 mathieu mathieu 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 mathieu mathieu   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  mathieu   23 Sep 20 14:25 hello
-rw-rw-r--  1 mathieu mathieu  926 Sep 20 17:52 iacta
-rw-rw-r--  1 mathieu mathieu    0 Sep 20 18:18 ls_cwd_content
```

### 9. Duplicate last line
Write a script that duplicates the last line of the file iacta

The file iacta will be in the working directory

```bash
mathieu@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est

mathieu@ubuntu:/tmp/h$ ./9-duplicate_last_line 
mathieu@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
```

### 10. No more javascript
Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.

```bash
mathieu@ubuntu:/tmp/h$ ls -lR
.:
total 24
-rwxrw-r-- 1 mathieu mathieu   49 Sep 20 18:29 10-no_more_js
drwxrwxr-x 2 mathieu mathieu 4096 Sep 20 18:23 dir1
drwxrwxr-x 2 mathieu mathieu 4096 Sep 20 18:24 dir.js
-rw-rw-r-- 1 betty  mathieu   23 Sep 20 14:25 hello
-rw-rw-r-- 1 mathieu mathieu  982 Sep 20 18:21 iacta
-rw-rw-r-- 1 mathieu mathieu  329 Sep 20 18:18 ls_cwd_content
-rw-rw-r-- 1 mathieu mathieu    0 Sep 20 18:23 main.js

./dir1:
total 0
-rw-rw-r-- 1 mathieu mathieu 0 Sep 20 18:23 code.js

./dir.js:
total 0

mathieu@ubuntu:/tmp/h$ ./10-no_more_js 
mathieu@ubuntu:/tmp/h$ ls -lR
.:
total 24
-rwxrw-r-- 1 mathieu mathieu   49 Sep 20 18:29 10-no_more_js
drwxrwxr-x 2 mathieu mathieu 4096 Sep 20 18:29 dir1
drwxrwxr-x 2 mathieu mathieu 4096 Sep 20 18:24 dir.js
-rw-rw-r-- 1 betty  mathieu   23 Sep 20 14:25 hello
-rw-rw-r-- 1 mathieu mathieu  982 Sep 20 18:21 iacta
-rw-rw-r-- 1 mathieu mathieu  329 Sep 20 18:18 ls_cwd_content

./dir1:
total 0

./dir.js:
total 0
```

### 11. Don't just count your directories, make your directories count
Write a script that counts the number of directories and sub-directories in the current directory.

The current and parent directories should not be taken into account
Hidden directories should be counted

```bash
mathieu@production-503e7013:~/shell/fun_with_the_shell$ ls -lRa
.:
total 32
drwxrwxr-x 3 mathieu mathieu 4096 Jan 20 03:53 .
drwxrwxr-x 3 mathieu mathieu 4096 Jan 20 02:58 ..
-rwxr--r-- 1 mathieu mathieu 43 Jan 20 02:59 0-commas
-rwxr--r-- 1 mathieu mathieu 47 Jan 20 02:50 1-empty_casks
-rwxrw-r-- 1 mathieu mathieu 68 Jan 20 03:35 2-gifs
-rwxrw-r-- 1 mathieu mathieu 47 Jan 20 03:53 3-directories
-rw-rw-r-- 1 mathieu mathieu 14 Jan 20 03:35 Makefile
drwxrwxr-x 4 mathieu mathieu 4096 Jan 20 03:42 test_dir

./test_dir:
total 16
drwxrwxr-x 4 mathieu mathieu 4096 Jan 20 03:42 .
drwxrwxr-x 3 mathieu mathieu 4096 Jan 20 03:53 ..
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:40 .horrible_selfie.gif
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:23 README.md
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:17 docker.gif
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:17 file.sh
drwxrwxr-x 2 mathieu mathieu 4096 Jan 20 03:23 photos
drwxrwxr-x 2 mathieu mathieu 4096 Jan 20 03:23 rep.gif

./test_dir/photos:
total 8
drwxrwxr-x 2 mathieu mathieu 4096 Jan 20 03:23 .
drwxrwxr-x 4 mathieu mathieu 4096 Jan 20 03:42 ..
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:23 cat.gif
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:22 index.html
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:23 main.gif
-rw-rw-r-- 1 mathieu mathieu 0 Jan 20 03:23 rudy_rigot.gif

./test_dir/rep.gif:
total 8
drwxrwxr-x 2 mathieu mathieu 4096 Jan 20 03:23 .
drwxrwxr-x 4 mathieu mathieu 4096 Jan 20 03:42 ..
mathieu@production-503e7013:~/shell/fun_with_the_shell$ ./11-directories
3
mathieu@production-503e7013:~/shell/fun_with_the_shell$
```

### 12. What’s new
Create a script that displays the 10 newest files in the current directory.

Requirements:

One file per line
Sorted from the newest to the oldest

```bash
mathieu@ubuntu:/tmp$ ls -l
total 7
-rwxr-xr-x 1 501 dialout  32 Sep 27 23:51 0-hello_world
-rwxr-xr-x 1 501 dialout  46 Sep 28 11:09 10-no_more_js
-rwxr-xr-x 1 501 dialout  43 Sep 28 11:19 11-directories
-rwxr-xr-x 1 501 dialout  30 Sep 29 13:43 12-newest_files
-rwxr-xr-x 1 501 dialout  28 Sep 27 23:54 1-confused_smiley
-rwxr-xr-x 1 501 dialout  28 Sep 27 23:58 2-hellofile
-rwxr-xr-x 1 501 dialout  39 Sep 27 23:58 3-twofiles
-rwxr-xr-x 1 501 dialout  33 Sep 27 23:59 4-lastlines
-rwxr-xr-x 1 501 dialout  33 Sep 28 00:00 5-firstlines
-rwxr-xr-x 1 501 dialout  28 Sep 28 00:25 6-third_line
-rwxr-xr-x 1 501 dialout 110 Sep 28 00:34 7-file
-rwxr-xr-x 1 501 dialout  36 Sep 28 00:34 8-cwd_state
-rwxr-xr-x 1 501 dialout  35 Sep 28 00:35 9-duplicate_last_line
-rw-r--r-- 1 501 dialout  19 Sep 27 23:51 README.md

mathieu@ubuntu:/tmp$ ./12-newest_files 
12-newest_files
11-directories
10-no_more_js
9-duplicate_last_line
7-file
8-cwd_state
6-third_line
5-firstlines
4-lastlines
3-twofiles
```

### 13. Being unique is better than being perfect
Create a script that takes a list of words as input and prints only words that appear exactly once.

Input format: One line, one word
Output format: One line, one word
Words should be sorted

```bash
mathieu@ubuntu:/tmp/0x02$ cat list 
C#
C
Javascript
Perl
PHP
PHP
ASP
R
Go
C#
C++
R
Perl
Javascript
Javascript
Python
Javascript
Javascript
Javascript
Java
Java
Python
Javascript
Javascript
Javascript
ASP

mathieu@ubuntu:/tmp/0x02$ cat list | ./13-unique 
C
C++
Go
```

### 14. It must be in that file
Display lines containing the pattern “root” from the file /etc/passwd

```bash
$ ./14-findthatword
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
$
```

### 15. Count that word
Display the number of lines that contain the pattern “bin” in the file /etc/passwd

```bash
$ ./15-countthatword
81
$ 
```

### 16. What's next?
Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.

```bash
$ ./16-whatsnext
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
--
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
_usbmuxd:*:213:213:iPhone OS Device Helper:/var/db/lockdown:/usr/bin/false
_dovecot:*:214:6:Dovecot Administrator:/var/empty:/usr/bin/false
_dpaudio:*:215:215:DP Audio:/var/empty:/usr/bin/false
$
```

### 17. I hate bins
Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.

```bash
$ ./17-hidethisword
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
$
```

### 18. Letters only please
Display all lines of the file /etc/ssh/sshd_config starting with a letter.

include capital letters as well

```bash
$ ./18-letteronly
SyslogFacility AUTHPRIV
AuthorizedKeysFile  .ssh/authorized_keys
UsePrivilegeSeparation sandbox # Default for new installations.
AcceptEnv LANG LC_*
Subsystem   sftp    /usr/libexec/sftp-server
$
```

### 19. A to Z
Replace all characters A and c from input to Z and e respectively.

```bash
mathieu@ubuntu:/tmp/0x02$ echo 'Replace all characters `A` and `c` from input to `Z` and `e`.' | ./19-AZ 
Replaee all eharaeters `Z` and `e` from input to `Z` and `e`.
```

### 20. Without C, you would live in hiago
Create a script that removes all letters c and C from input.

```bash
mathieu@ubuntu:/tmp/0x02$ echo Chicago | ./20-hiago 
hiago
```

### 21. esreveR
Write a script that reverse its input.

```bash
mathieu@ubuntu:/tmp/0x02$ echo "Reverse" | ./21-reverse 
esreveR
```

### 22. DJ Cut Killer
Write a script that displays all users and their home directories, sorted by users.

Based on the the /etc/passwd file

```bash
mathieu@ubuntu:/tmp/0x02$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-timesync:x:100:102:systemd Time Synchronization,,,:/run/systemd:/bin/false
systemd-network:x:101:103:systemd Network Management,,,:/run/systemd/netif:/bin/false
systemd-resolve:x:102:104:systemd Resolver,,,:/run/systemd/resolve:/bin/false
systemd-bus-proxy:x:103:105:systemd Bus Proxy,,,:/run/systemd:/bin/false
syslog:x:104:108::/home/syslog:/bin/false
_apt:x:105:65534::/nonexistent:/bin/false
messagebus:x:106:110::/var/run/dbus:/bin/false
uuidd:x:107:111::/run/uuidd:/bin/false
lightdm:x:108:114:Light Display Manager:/var/lib/lightdm:/bin/false
whoopsie:x:109:116::/nonexistent:/bin/false
avahi-autoipd:x:110:119:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/bin/false
avahi:x:111:120:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/bin/false
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/bin/false
colord:x:113:123:colord colour management daemon,,,:/var/lib/colord:/bin/false
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/var/run/speech-dispatcher:/bin/false
hplip:x:115:7:HPLIP system user,,,:/var/run/hplip:/bin/false
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/bin/false
pulse:x:117:124:PulseAudio daemon,,,:/var/run/pulse:/bin/false
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
julien:x:1000:1000:Julien Barbier,,,:/home/julien:/bin/bash
guillaume:x:1001:1001:,,,:/home/guillaume:/bin/bash
betty:x:1002:1002::/home/betty:

mathieu@ubuntu:/tmp/0x02$
mathieu@ubuntu:/tmp/0x02$ ./22-users_and_homes 
_apt:/nonexistent
avahi-autoipd:/var/lib/avahi-autoipd
avahi:/var/run/avahi-daemon
backup:/var/backups
betty:/home/betty
bin:/bin
colord:/var/lib/colord
daemon:/usr/sbin
dnsmasq:/var/lib/misc
games:/usr/games
gnats:/var/lib/gnats
guillaume:/home/guillaume
hplip:/var/run/hplip
irc:/var/run/ircd
julien:/home/julien
kernoops:/
lightdm:/var/lib/lightdm
list:/var/list
lp:/var/spool/lpd
mail:/var/mail
man:/var/cache/man
messagebus:/var/run/dbus
news:/var/spool/news
nobody:/nonexistent
proxy:/bin
pulse:/var/run/pulse
root:/root
rtkit:/proc
saned:/var/lib/saned
speech-dispatcher:/var/run/speech-dispatcher
sync:/bin
sys:/dev
syslog:/home/syslog
systemd-bus-proxy:/run/systemd
systemd-network:/run/systemd/netif
systemd-resolve:/run/systemd/resolve
systemd-timesync:/run/systemd
usbmux:/var/lib/usbmux
uucp:/var/spool/uucp
uuidd:/run/uuidd
whoopsie:/nonexistent
www-data:/var/www
mathieu@ubuntu:/tmp/0x02$ 
```
