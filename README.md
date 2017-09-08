# falcon-agent

#mail: 826167518@qq.com

#author: zhangqi

文件目录结构：

falcon-agent <br />
├── ansible.cfg <br />
├── hosts<br />

├── inventory

│   ├── group_vars

│   │   └── all

│   ├── hosts.yml

│   └── host_vars

│       └── zt-ce01.yml

├── playbooks

│   ├── falcon-agent.yml

│   ├── supervisor.yml

│   ├── useradd.yml

│   └── zabbix.yml

├── README.md

├── roles

│   ├── falcon-agent

│   │   ├── defaults

│   │   │   └── main.yml

│   │   ├── tasks

│   │   │   └── main.yml

│   │   └── templates

│   │       ├── cfg.json.j2

│   │       └── falcon_agent.ini.j2

│   ├── iptables

│   │   └── tasks

│   │       └── main.yml

│   ├── repo

│   │   ├── tasks

│   │   │   └── main.yml

│   │   └── templates

│   │       ├── epel.repo.j2

│   │       └── szy.repo.j2

│   ├── supervisord

│   │   ├── defaults

│   │   ├── tasks

│   │   │   └── main.yml

│   │   └── templates

│   │       ├── supervisord.conf.j2

│   │       └── supervisord.j2

│   ├── user

│   │   ├── defaults

│   │   │   └── main.yml

│   │   └── tasks

│   │       └── main.yml

│   └── zabbix

│       ├── defaults

│       │   └── main.yml

│       ├── handlers

│       ├── meta

│       ├── tasks

│       │   └── main.yml

│       └── templates

│           └── zabbix_agentd.conf

└── task

    ├── install.sh

    ├── LICENSE

    └── README.md


安装完毕ansible之后，直接进入到该文件的ansible.cfg的同级目录下

更改inventory/hosts.yml对应的主机名即可
inventory/group_vars/all 为全局变量。

安装supervisor+falcon-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/supervisor.yml 

安装falcon-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/falcon-agent.yml

安装zabbix-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/zabbix.yml
