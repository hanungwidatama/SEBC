[root@chl1 yum.repos.d]# more mysql-community.repo <br>
[mysql-connectors-community] <br>
name=MySQL Connectors Community <br>
baseurl=http://repo.mysql.com/yum/mysql-connectors-community/el/5/$basearch/ <br>
enabled=1<br>
gpgcheck=1<br>
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql <br>
<br>
# Enable to use MySQL 5.6 <br>
[mysql56-community] <br>
name=MySQL 5.6 Community Server <br>
baseurl=http://repo.mysql.com/yum/mysql-5.6-community/el/5/$basearch/ <br>
enabled=0 <br>
gpgcheck=1 <br>
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql <br>
<br>
[mysql57-community] <br>
name=MySQL 5.7 Community Server <br>
baseurl=http://repo.mysql.com/yum/mysql-5.7-community/el/5/$basearch/ <br>
enabled=0 <br>
gpgcheck=1 <br>
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql <br>
[root@chl1 yum.repos.d]#<br>
