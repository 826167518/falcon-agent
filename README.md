# falcon-agent

#mail: 826167518@qq.com

#author: zhangqi

文件目录结构：

falcon-agent <br />
├── ansible.cfg <br />
├── hosts<br />
├── inventory<br />
│ &nbsp;&nbsp;&nbsp;  ├── group_vars<br />
│ &nbsp;&nbsp;&nbsp;  │ &nbsp;&nbsp;&nbsp;  └── all<br />
│ &nbsp;&nbsp;&nbsp; ├── hosts.yml<br />
│ &nbsp;&nbsp;&nbsp; └── host_vars<br />
│ .......................└── zt-ce01.yml<br />
├── playbooks<br />
│ &nbsp;&nbsp;&nbsp;  ├── falcon-agent.yml<br />
│ &nbsp;&nbsp;&nbsp;  ├── supervisor.yml<br />
│ &nbsp;&nbsp;&nbsp;  ├── useradd.yml<br />
│ &nbsp;&nbsp;&nbsp;  └── zabbix.yml<br />
├── README.md<br />
├── roles<br />
│ &nbsp;&nbsp;&nbsp;  ├── falcon-agent<br />
│ &nbsp;&nbsp;&nbsp;  │   ├── defaults<br />
│ &nbsp;&nbsp;&nbsp;  │   │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  │   ├── tasks<br />
│ &nbsp;&nbsp;&nbsp;  │   │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  │   └── templates<br />
│ &nbsp;&nbsp;&nbsp;  │       ├── cfg.json.j2<br />
│ &nbsp;&nbsp;&nbsp;  │       └── falcon_agent.ini.j2<br />
│ &nbsp;&nbsp;&nbsp;  ├── iptables<br />
│ &nbsp;&nbsp;&nbsp;  │   └── tasks<br />
│ &nbsp;&nbsp;&nbsp;  │       └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  ├── repo<br />
│ &nbsp;&nbsp;&nbsp;  │   ├── tasks<br />
│ &nbsp;&nbsp;&nbsp;  │   │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  │   └── templates<br />
│ &nbsp;&nbsp;&nbsp;  │       ├── epel.repo.j2<br />
│ &nbsp;&nbsp;&nbsp;  │       └── szy.repo.j2<br />
│ &nbsp;&nbsp;&nbsp;  ├── supervisord<br />
│ &nbsp;&nbsp;&nbsp;  │   ├── defaults<br />
│ &nbsp;&nbsp;&nbsp;  │   ├── tasks<br />
│ &nbsp;&nbsp;&nbsp;  │   │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  │   └── templates<br />
│ &nbsp;&nbsp;&nbsp;  │       ├── supervisord.conf.j2<br />
│ &nbsp;&nbsp;&nbsp; │       └── supervisord.j2<br />
│ &nbsp;&nbsp;&nbsp;  ├── user<br />
│ &nbsp;&nbsp;&nbsp;  │   ├── defaults<br />
│ &nbsp;&nbsp;&nbsp;  │   │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  │   └── tasks<br />
│ &nbsp;&nbsp;&nbsp;  │       └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;  └── zabbix<br />
│ &nbsp;&nbsp;&nbsp;      ├── defaults<br />
│ &nbsp;&nbsp;&nbsp;      │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;      ├── handlers<br />
│ &nbsp;&nbsp;&nbsp;      ├── meta<br />
│ &nbsp;&nbsp;&nbsp;      ├── tasks<br />
│ &nbsp;&nbsp;&nbsp;      │   └── main.yml<br />
│ &nbsp;&nbsp;&nbsp;      └── templates<br />
│ &nbsp;&nbsp;&nbsp;          └── zabbix_agentd.conf<br />
└── task<br />
&nbsp;&nbsp;├── install.sh<br />
&nbsp;&nbsp;├── LICENSE<br />
&nbsp;&nbsp;└── README.md<br />


安装完毕ansible之后，直接进入到该文件的ansible.cfg的同级目录下

更改inventory/hosts.yml对应的主机名即可
inventory/group_vars/all 为全局变量。

安装supervisor+falcon-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/supervisor.yml 

安装falcon-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/falcon-agent.yml

安装zabbix-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/zabbix.yml
