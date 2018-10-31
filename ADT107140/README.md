##第一題
*創建mygroup nogroup

*利用useradd -G mygroup myuser1~3(建立myuser1~3時同時加入mygroup)
*同理nogroup 和nouser1~3一樣的方式
![](./01.png)
![](./03.png)
*id 每個user
![](./04.png)
*mkdir /srv/myproject
*chgrp mygroup /srv/myproject
*chmod 770 /srv/project
![](./05.png)
*切換myuser1 touch myuser1.data
![](./06.png)
*cp /usr/bin/ls /usr/local/bin/myls
*切換nouser1 myls /srv/myproject :permission denied
![](./07.png)
*su - root 把/srv/myproject的user setuid 
*nouser1即可myls /srv/myproject
![](./08.png)
##第二題
*ps aux | grep rsyslog pid為990 command /usr/sbin/rsyslogd-n
![](./09.png)
*top  pr20 ni0
![](./10.png)
*ps aux | grep rsyslog > /root/process_syslog.txt
*vi process_syslog.txt
![](./11.png)
##第三題
*以照此網址find教學:https://blog.gtwang.org/linux/unix-linux-find-command-examples/
*find /usr/bin /usr/sbin -perm /4000
*4為suid
![](./12.png)
*find /usr/bin /usr/sbin -perm /4000 -exec ls -l {} \;
![](./14.png)
*find /usr/bin /usr/sbin -perm /4000 -exec ls -l {} \; >  /root/findsuidsgid.txt
*vi findsuidsgid.txt
![](./15.png)

