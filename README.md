# Agente Zabbix

Atualiza ou instala o agente do zabbix em maquinas com gerenciadores de pacote Linux (Red Hat base)
Esse script não alterar nenhuma configuração no servidor do zabbix.
Necessário que o zabbix_get esteja instalado no servidor do zabbix para realizar o teste.

## Estrutura do diretório

  - [group_vars](./group_vars/)
  > [all] - Contém as variáveis utilizadas para definir a versão do agente a ser instalada e arquivo de configuraçao
  - [roles](./roles/)
  > /remove/tasks/main.yml - Apenas remove o agente do zabbix instalado. Util para testes do ansible
  > /instala/tasks/main.yml - Instala ou atualiza o agente do zabbix 
  > /teste/tasks/main.yml - Testa a conexão do servidor do zabbix com o servidor
  - [hosts](./hosts)
  > Arquivo com o nome dos hosts com dois grupos: \[servidor\]=> servidor(es) do zabbix, \[agentes\]=> onde os agentes serão instalados/atualizados/removidos
  


  - main.yml (arquivo)
  > Apontamento das roles descritas acima



## Antes de executar o script leia com atenção:
  - Adicionar o nome dos hosts no arquivo [hosts](./hosts)
  - Editar o arquivo [all](group_vars/all) alterando as variaveis necessárias.


### Execução

Exemplo de execução do script

```sh
$ git clone $this_repo
$ cd kubernetes
$ ansible-playbook -i hosts main -u usuario_permissao_sudo -k -vv --become
```

### Autores

João Vitorino

Leandro Rafael

