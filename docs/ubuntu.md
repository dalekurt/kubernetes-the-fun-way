## Enable container features
We need to enable container features in the kernel, edit `/boot/firmware/cmdline.txt` and add the following to the end of the line:

Update `sudo vim /boot/firmware/cmdline.txt`

```bash
cgroup_enable=cpuset cgroup_memory=1 cgroup_enable=memory
```

## Change the hostname using hostnamectl. 

```bash
sudo hostnamectl set-hostname master
```

## Edit the cloud.cfg file.

```bash
sudo vim /etc/cloud/cloud.cfg
```

Search for preserve_hostname and change the value from false to true:

```bash
# This will cause the set+update hostname module to not operate (if true)
preserve_hostname: true
```

## Verify the change 

To verify that the hostname was successfully changed, once again use the hostnamectl command:

```bash
hostnamectl
```
