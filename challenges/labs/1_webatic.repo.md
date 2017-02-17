[root@chl1 yum.repos.d]# more webtatic.repo <br>
[webtatic]<br>
name=Webtatic Repository EL6 - $basearch<br>
#baseurl=https://repo.webtatic.com/yum/el6/$basearch/<br>
mirrorlist=https://mirror.webtatic.com/yum/el6/$basearch/mirrorlist<br>
failovermethod=priority<br>
enabled=1<br>
gpgcheck=1<br>
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-webtatic-el6<br>
<br>
[webtatic-debuginfo]<br>
name=Webtatic Repository EL6 - $basearch - Debug <br>
#baseurl=https://repo.webtatic.com/yum/el6/$basearch/debug/<br>
mirrorlist=https://mirror.webtatic.com/yum/el6/$basearch/debug/mirrorlist<br>
failovermethod=priority<br>
enabled=0<br>
gpgcheck=1<br>
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-webtatic-el6<br>
<br>
[webtatic-source]<br>
name=Webtatic Repository EL6 - $basearch - Source<br>
#baseurl=https://repo.webtatic.com/yum/el6/SRPMS/<br>
mirrorlist=https://mirror.webtatic.com/yum/el6/SRPMS/mirrorlist<br>
failovermethod=priority<br>
enabled=0<br>
gpgcheck=1<br>
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-webtatic-el6<br>
[root@chl1 yum.repos.d]#<br>
