# Redis Ansible

使用 Ansible 搭建 Redis 集群

## 使用

```sh
git clone git@github.com:aisuhua/redis-ansible.git
cd redis-ansible

# 按需修改主机 IP、安装目录等
vim hosts.yaml

ansible-playbook playbook.yaml
```

## 卸载

```sh
ansible-playbook remove.yaml
```

## 测试

```sh
# 查看集群节点状态
$ /opt/redis/7.2.4/node1-redis1/bin/redis-cli -h 172.31.96.151 -p 7000 -a Luck@u99 cluster nodes
Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
0d9a0cdffd1bc63328901884077b8a8fbb635c14 172.31.96.151:7003@17003 slave 82e1270978c13aecbd60d826850988a478a66dd1 0 1725538671000 2 connected
82e1270978c13aecbd60d826850988a478a66dd1 172.31.96.151:7005@17005 master - 0 1725538672291 2 connected 5461-10922
1f311a69bf7b4d4f351ff037a2e900e589f7acba 172.31.96.151:7002@17002 master - 0 1725538672000 3 connected 10923-16383
35c0a22e9c9ba33de7aaee0345e399aaa015c02a 172.31.96.151:7000@17000 myself,slave 1f311a69bf7b4d4f351ff037a2e900e589f7acba 0 1725538670000 3 connected
686ed17207629b5752f7c5d69ae48ea6c1e94e79 172.31.96.151:7001@17001 master - 0 1725538673295 1 connected 0-5460
83b30291b1a1bb34d0ba6070a3a938a85c79787b 172.31.96.151:7004@17004 slave 686ed17207629b5752f7c5d69ae48ea6c1e94e79 0 1725538671000 1 connected
```

## Ref

- https://github.com/OT-OSM/redis-setup
