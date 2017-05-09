# Docker: Zabbix agent

## Getting started

    ansible-galaxy install -p roles/ -r requirements.yml --force
    packer build centos.json

## How to use this image    
    docker run --name zabbix-agent -e ZABBIX_HOSTNAME="some-hostname" -e ZABBIX_SERVER_HOST="some-zabbix-server" --privileged -d shomatan/zabbix-agent:3.2-centos

## Environment Variables

### ZABBIX_AGENT_HOSTNAME
This variable is unique, case sensitive hostname. By default, value is hostname of the container. It is Hostname parameter in `zabbix_agentd.conf`.

### ZABBIX_SERVER_HOST
This variable is IP or DNS name of Zabbix server or Zabbix proxy. By default, value is `zabbix-server`. It is Server parameter in zabbix_agentd.conf. It is allowed to specify Zabbix server or Zabbix proxy port number using ZBX_SERVER_PORT variable. It make sense in case of non-default port for active checks.