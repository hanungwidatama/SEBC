Setup for 5 Machines using google cloud <br>
Hostname = chl1,chl2,chl3 <br>
  Specs    = 2vCPUs  7,5GB memory 80GB disk Centos 6 <br>
  Hostname = chl4,chl5 <br>
  Specs    = 1vCPUs  3,75GB memory 80GB disk Centos 6 <br>
  <br>
  
  REPOLIST<br>
[prima_tableau@chl1 ~]$ yum repolist enabled<br>
Loaded plugins: fastestmirror, security<br>
Determining fastest mirrors<br>
 * base: mirrors.gigenet.com<br>
 * extras: mirrors.liquidweb.com<br>
 * updates: centos.firehosted.com<br>
google-cloud-compute                                                        4/4<br>
repo id                              repo name                            status<br>
base                                 CentOS-6 - Base                      6,696<br>
centos-sclo-rh                       CentOS-6 - SCLo rh                   4,955<br>
centos-sclo-sclo                     CentOS-6 - SCLo sclo                   257<br>
extras                               CentOS-6 - Extras                       63<br>
google-cloud-compute                 Google Cloud Compute                     4<br>
updates                              CentOS-6 - Updates                     825<br>
repolist: 12,800<br>
[prima_tableau@chl1 ~]$<br>
<br>
USER<br>
[root@chl1 ~]# useradd raffles -u 2000<br>
[root@chl1 ~]# useradd fullerton -u 3000<br>
[root@chl1 ~]# groupadd hotel<br>
[root@chl1 ~]# groupadd shop<br>
[root@chl1 ~]# passwd "raffles"<br>
Changing password for user raffles.<br>
New password:<br>
BAD PASSWORD: it is WAY too short<br>
BAD PASSWORD: is too simple<br>
Retype new password:<br>
passwd: all authentication tokens updated successfully.<br>
[root@chl1 ~]# passwd "fullerton"<br>
Changing password for user fullerton.<br>
New password:<br>
BAD PASSWORD: it is WAY too short<br>
BAD PASSWORD: is too simple<br>
Retype new password:<br>
passwd: all authentication tokens updated successfully.<br>
[root@chl1 ~]# usermod -a -G hotel fullerton<br>
[root@chl1 ~]# usermod -a -G shop raffles<br>
<br>
LIST /ETC/PASSWD<br>
[root@chl1 ~]# more /etc/passwd<br>
root:x:0:0:root:/root:/bin/bash<br>
bin:x:1:1:bin:/bin:/sbin/nologin<br>
daemon:x:2:2:daemon:/sbin:/sbin/nologin<br>
adm:x:3:4:adm:/var/adm:/sbin/nologin<br>
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin<br>
sync:x:5:0:sync:/sbin:/bin/sync<br>
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown<br>
halt:x:7:0:halt:/sbin:/sbin/halt<br>
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin<br>
uucp:x:10:14:uucp:/var/spool/uucp:/sbin/nologin<br>
operator:x:11:0:operator:/root:/sbin/nologin<br>
games:x:12:100:games:/usr/games:/sbin/nologin<br>
gopher:x:13:30:gopher:/var/gopher:/sbin/nologin<br>
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin<br>
nobody:x:99:99:Nobody:/:/sbin/nologin<br>
dbus:x:81:81:System message bus:/:/sbin/nologin<br>
vcsa:x:69:69:virtual console memory owner:/dev:/sbin/nologin<br>
abrt:x:173:173::/etc/abrt:/sbin/nologin<br>
haldaemon:x:68:68:HAL daemon:/:/sbin/nologin<br>
ntp:x:38:38::/etc/ntp:/sbin/nologin<br>
saslauth:x:499:76:Saslauthd user:/var/empty/saslauth:/sbin/nologin<br>
postfix:x:89:89::/var/spool/postfix:/sbin/nologin<br>
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin<br>
tcpdump:x:72:72::/:/sbin/nologin<br>
prima_tableau:x:500:501::/home/prima_tableau:/bin/bash<br>
donald:x:2700:2700::/home/donald:/bin/bash<br>
vladimir:x:2800:2800::/home/vladimir:/bin/bash<br>
raffles:x:2000:2000::/home/raffles:/bin/bash<br>
fullerton:x:3000:3000::/home/fullerton:/bin/bash<br>
[root@chl1 ~]#<br>
<br>
LIST /ETC/GROUP<br>
[root@chl1 ~]# more /etc/group<br>
root:x:0:<br>
bin:x:1:bin,daemon<br>
daemon:x:2:bin,daemon<br>
sys:x:3:bin,adm<br>
adm:x:4:adm,daemon,prima_tableau<br>
tty:x:5:<br>
disk:x:6:<br>
lp:x:7:daemon<br>
mem:x:8:<br>
kmem:x:9:<br>
wheel:x:10:<br>
mail:x:12:mail,postfix<br>
uucp:x:14:<br>
man:x:15:<br>
games:x:20:<br>
gopher:x:30:<br><br><br>
video:x:39:prima_tableau<br><br>
dip:x:40:prima_tableau<br>
ftp:x:50:<br>
lock:x:54:<br>
audio:x:63:<br>
nobody:x:99:<br>
users:x:100:<br>
dbus:x:81:<br>
utmp:x:22:<br>
utempter:x:35:<br>
floppy:x:19:<br>
vcsa:x:69:<br>
abrt:x:173:<br>
cdrom:x:11:<br>
tape:x:33:<br>
dialout:x:18:<br>
haldaemon:x:68:haldaemon<br>
ntp:x:38:<br>
saslauth:x:76:<br>
postdrop:x:90:<br>
postfix:x:89:<br>
sshd:x:74:<br>
tcpdump:x:72:<br>
stapusr:x:156:<br>
stapsys:x:157:<br>
stapdev:x:158:<br>
slocate:x:21:<br>
google-sudoers:x:500:prima_tableau<br>
prima_tableau:x:501:<br>
donald:x:2700:<br>
vladimir:x:2800:<br>
hackers:x:2801:vladimir<br><br>
crackers:x:2802:donald<br>
raffles:x:2000:<br>
fullerton:x:3000:<br>
hotel:x:3001:fullerton<br>
shop:x:3002:raffles<br>
