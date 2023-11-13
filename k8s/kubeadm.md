
> Create a cluster
```sh
# get specific interface ip
# host_ip=$(ip addr show wlp3s0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
# get first interface ip
host_ip=$(hostname -I | awk '{print $1}')
sudo kubeadm init --apiserver-advertise-address $host_ip
```




> Test port
```sh
telnet <host_IP> 6443
netstat -pnlt | grep 6443 # sudo apt install net-tools
```

> join token recreate
```sh
kubeadm token create --print-join-com你的靜態 mand
```
