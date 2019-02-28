# Sincronismo NTP para instalação do Kudu

* **Criado por:** Anselmo Borges
* **Ultima Atualização:** 28.02.2018

## Pre-reqs do Playbook
Esse playbook realiza o sincronismo do time entre os servidores do Cluster Cloudera, ativando todos os deamons necessários para a instalação e utilização do Kudu. Será necessária a edição apenas dos 2 arquivos de configuração citados abaixo colocando o endereço do seu NTP server (de preferencia 1 se houver diferença entre eles), deve ser alterado tambem o alias do grupo de hosts onde serão executados os comandos do playbook, deixei o nome que usei aqui "ndevs".
* ntp.conf
* chrony.conf

## O que o playbook faz?
Esse playbook faz as seguintes funções:
* Copia o arquivo de configuração do NTP para os hosts
* Copia o arquivo de configuração do Chrony para os hosts
* Restarta o daemon do NTPD
* Habilita o daemon do Chronyd
* Inicia o deamon do Chronyd
* Realiza um sync do time entre os nodes do cluster

## Como executar:
Apoś configurado o Ansible (adição do hosts e chave ssh), a execução do playbook é feita com o comando abaixo:
```
ansible_playbook sync_kudu.yml
```


