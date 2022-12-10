# exert ansible

因为依赖 Linux 环境 Ansible 无法在 Windows 下直接执行，所以可以在 WSL2 里面执行。

```bash
pip install ansible
```

默认使用公钥通过 SSH 执行，所以要把公钥部署到要管理的服务器上。

默认的 inventory 配置路径 /etc/ansible/hosts
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

# 执行 shell
ansible webservers -m shell -a 'ps -ef'

# 执行 shell 指定 inventory 配置
ansible webservers -m shell -a 'ps -ef' -i my.cfg

# 执行命令
ansible webservers -m command -a 'ps -ef'

# 执行命令 指定 inventory 配置
ansible webservers -m command -a 'ps -ef' -i my.cfg
```
