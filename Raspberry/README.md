# kubernetes Raspberry Pi 4
## Install MicroK8S Ubuntu 20.10 Server

```console
$ sudo vi /boot/firmware/cmdline.txt
$ cgroup_enable=cpuset cgroup_enable=memory cgroup_memory=1 
$ sudo snap install microk8s --classic
$ sudo usermod -a -G microk8s $USER
$ sudo chown -f -R $USER ~/.kube
$ sudo iptables -P FORWARD ACCEPT
$ sudo nano /etc/docker/daemon.json

            {
                "insecure-registries" : ["localhost:32000"]
            }

$nano .bashrc 

        alias kubectl='microk8s kubectl'
        alias k='kubectl'
$ microk8s enable dns
$ sudo reboot
```
## Install MicroK8S.Helm3 Ubuntu 20.10 Server
```console
$ microk8s enable helm3
$ helm init --tiller-image=jessestuart/tiller


