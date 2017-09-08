# falcon-agent

#mail: 826167518@qq.com

#author: zhangqi

文件目录结构：

falcon-agent <br />
├── ansible.cfg <br />
├── hosts<br />
├── inventory<br />
│ ........├── group_vars<br />
│ ........│ ........└── all<br />
│ ........├── hosts.yml<br />
│ ........└── host_vars<br />
│ .......................└── zt-ce01.yml<br />
├── playbooks<br />
│ ........├── falcon-agent.yml<br />
│ ........├── supervisor.yml<br />
│ ........├── useradd.yml<br />
│ ........└── zabbix.yml<br />
├── README.md<br />
├── roles<br />
│ ........├── falcon-agent<br />
│ ........│ ........├── defaults<br />
│ ........│ ........│ ........└── main.yml<br />
│ ........│ ........├── tasks<br />
│ ........│ ........│ ........└── main.yml<br />
│ ........│ ........└── templates<br />
│ ........│ ........................├── cfg.json.j2<br />
│ ........│ ........................└── falcon_agent.ini.j2<br />
│ ........├── iptables<br />
│ ........│ ........└── tasks<br />
│ ........│ ........................└── main.yml<br />
│ ........├── repo<br />
│ ........│ ........├── tasks<br />
│ ........│ ........│ ........└── main.yml<br />
│ ........│ ........└── templates<br />
│ ........│ ........................├── epel.repo.j2<br />
│ ........│ ........................└── szy.repo.j2<br />
│ ........├── supervisord<br />
│ ........│ ........├── defaults<br />
│ ........│ ........├── tasks<br />
│ ........│ ........│ ........└── main.yml<br />
│ ........│ ........└── templates<br />
│ ........│ ........................├── supervisord.conf.j2<br />
│ ........│ ........................└── supervisord.j2<br />
│ ........├── user<br />
│ ........│ ........├── defaults<br />
│ ........│ ........│ ........└── main.yml<br />
│ ........│ ........└── tasks<br />
│ ........│ ........................└── main.yml<br />
│ ........└── zabbix<br />
│ ................├── defaults<br />
│ ................│ ........└── main.yml<br />
│ ................├── handlers<br />
│ ................├── meta<br />
│ ................├── tasks<br />
│ ................│ ................└── main.yml<br />
│ ................└── templates<br />
│ ................................└── zabbix_agentd.conf<br />
└── task<br />
........├── install.sh<br />
........├── LICENSE<br />
........└── README.md<br />


安装完毕ansible之后，直接进入到该文件的ansible.cfg的同级目录下

更改inventory/hosts.yml对应的主机名即可
inventory/group_vars/all 为全局变量。

安装supervisor+falcon-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/supervisor.yml 

安装falcon-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/falcon-agent.yml

安装zabbix-agent命令：
ansible-playbook -i inventory/hosts.yml playbooks/ssy/zabbix.yml
