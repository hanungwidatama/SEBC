[root@chl2 schema]# ls /etc/yum.repos.d <br>
CentOS-Base.repo       CentOS-fasttrack.repo  CentOS-SCLo-scl.repo     CentOS-Vault.repo      google-cloud.repo <br>
CentOS-Debuginfo.repo  CentOS-Media.repo      CentOS-SCLo-scl-rh.repo  cloudera-manager.repo <br>
[root@chl2 schema]# <br>
[root@chl2 schema]# ./scm_prepare_database.sh mysql -h chl1 scm root <br>
