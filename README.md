# Para usuários Linux

Olá pessoal, tudo bem?

Nós modificamos as variáveis de ambiente do ElasticSearch no docker-compose.yaml, descrito na aula "Iniciando com Elasticsearch e Kibana", para ficar compatível com o ambiente Linux.

Antes de executar o docker-compose up, crie a rede observability com o comando
```bash
$ docker network create observability 
```

Também é necessário criar a pasta elasticsearch_data no poc-observabilidade-elastic na máquina local manualmente para evitar erro de permissionamento
```bash
$ mkdir elasticsearch_data 
```

Na pasta /beats/metric execute o seguinte comando:
```bash
$ sudo chown root metricbeat.yml
```

Caso ocorra o erro 
```bash
bootstrap check failure [1] of [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
```

Execute o comando 
```bash
$ sysctl -w vm.max_map_count=262144
```