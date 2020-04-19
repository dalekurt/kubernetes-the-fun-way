# Install Raspbian
> Note Rasbian is a 32-bit OS
Download Raspbian

Flash

Enable SSH

```bash
sudo touch /Volume/boot/ssh
sudo umount /Volume/boot
```
Update the hostname

```bash
sudo hostnamectl set-hostname master <node-01>
```

Update /etc/hosts file

```bash
127.0.0.1       localhost
::1             localhost ip6-localhost ip6-loopback
ff02::1         ip6-allnodes
ff02::2         ip6-allrouters

127.0.1.1       raspberrypi
```

To get the kernel run the usual 

```bash
sudo rpi-update
```

to get the latest kernel. If you want to switch to 64-bit kernel add to `/boot/config.txt`

```bash
arm_64bit=1
```
```bash
sudo nano /boot/cmdline.txt
```

```bash
cgroup_enable=cpuset cgroup_memory=1 cgroup_enable=memory
```

Now reboot

```bash
sudo reboot
```

 ```
 $ uname -a
Linux master 4.19.97-v8+ #1294 SMP PREEMPT Thu Jan 30 13:27:08 GMT 2020 aarch64 GNU/Linux
```
