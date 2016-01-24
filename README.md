# genRouter
Gentoo Router Setup Scripts with Wifi

### Init (setup ssh and start scripts)
Type these commands onto your router booted with the Gentoo install CD.
```bash
useradd -m -G users,wheel admin
passwd admin
passwd root
/etc/init.d/sshd start

ifconfig
```

Take note of the routers ips from the ifconfig command. Then run this command from the root dir of this repo:
```bash
rsync ./* admin@<router_ip>:~
```

### Start scripts on the router
Ssh to the router and start the scripts.
```bash
ssh admin@<router_ip>
./preinstall
```
This script will stop at times and prompt you to check things over,  This is done in a sub bash shell after you are finished at each step run exit that bash shell and the script will continue.

