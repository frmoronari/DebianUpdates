#Debian Updates Monitor

## Em Português

Controle de atualizações para Debian Linux com Zabbix.

Este é um tempalte simples, com apenas duas chaves para verificação de quantidade
e listagem de updates disponíveis para Debian Linux.

Um alerta do tipo atenção é gerado quando o número de updates for <> (diferente) de 0 (zero)


## Instalação:
Editar o arquivo "/etc/zabbix/zabbix_agentd.conf" (ou seu correspondente) e inserir as linhas:

"# Count and list Debian Updates
UserParameter=debian.updt.qt,sudo apt update 2>/dev/null | grep packages | awk '{print $1}'
UserParameter=debian.updt.list,sudo apt list --upgradable 2>/dev/null | awk '{print $1}' | tail -n +2"

Ou usar o comando abaixo com sudo ou usuário "root":

"echo -e '\n# Count and list Debian Updates \nUserParameter=debian.updt.qt,sudo apt update 2>/dev/null | grep packages | awk '{print $1}' \nUserParameter=debian.updt.list,sudo apt list --upgradable 2>/dev/null | awk '{print $1}' | tail -n +2 \n' >> /etc/zabbix/zabbix_agentd.conf"

Realizar o download do arquivo "DebianUpdates.yaml".

Importar em seu Zabbix Server o arquivo de template baixado.

Atribuí-lo ao host ou grupo de hosts a ser monitorado.

## Contribuições

Caso desejar os alertas e descrições em seu idioma, é necessário alterar os textos no template conforme achar necessário.

Toda a contribuição para melhoria desse template é bem vindo.
Faça seu pull request para que possamos melhorar continuamente.

## In English

This is a simple template, with only two keys to check the quantity
and list of updates available for Debian Linux.

A warning type alert is generated when the number of updates is <> (different) from 0 (zero)

For it to work, you need to add two lines to the file "/etc/zabbix/zabbix_agentd.com"
or its equivalent, import the template file to your Zabbix Server and assign it to the
host(s) to be monitored.

## Installation:
Edit the file "/etc/zabbix/zabbix_agentd.conf" (or its equivalent) and insert the lines:

"# Count and list Debian Updates
UserParameter=debian.updt.qt,sudo apt update 2>/dev/null | grep packages | awk '{print $1}'
UserParameter=debian.updt.list,sudo apt list --upgradable 2>/dev/null | awk '{print $1}' | tail -n +2"

Or use the command below with sudo or "root" user:

"echo -e '\n# Count and list Debian Updates \nUserParameter=debian.updt.qt,sudo apt update 2>/dev/null | grep packages | awk '{print $1}' \nUserParameter=debian.updt.list,sudo apt list --upgradable 2>/dev/null | awk '{print $1}' | tail -n +2 \n' >> /etc/zabbix/zabbix_agentd.conf"

Download the file "DebianUpdates.yaml".

Import the downloaded template file to your Zabbix Server.

Assign it to the host or group of hosts to be monitored.

## Contributions

If you want the alerts and descriptions in your language, you must change the texts in the template as you see fit.

Any contribution to improve this template is welcome.
Make your pull request so we can continuously improve it.
