# exert ansible

因为以来 Linux 环境 Ansible 无法在 Windows 下直接执行，所以可以在 WSL2 里面执行。

```bash
pip install ansible
```

/etc/ansible/hosts
```ini
#web1.ansible.com
192.168.1.101

[webservers]
192.168.1.102
192.168.1.103
192.168.1.104
```

```bash
# 指定 IP ping
ansible 192.168.1.111 -m ping

# 指定 IP组 ping
ansible webservers -m ping
```
