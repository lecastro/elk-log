# Descrição do ELK

```
Elasticsearch: O Elasticsearch é o mecanismo de busca e análise de dados propriamente dito.

Logstash: O Logstash é um pipeline gratuito e aberto de processamento de dados do lado do servidor que faz a ingestão de dados de inúmeras fontes. É usado para agregar e processar dados e enviá-los ao Elasticsearch.

Kibana: O Kibana é uma ferramenta de visualização e gerenciamento de dados de fonte aberta para o Elasticsearch. Ele fornece recursos de visualização (histogramas, diferentes tipos de gráficos, mapas, entre outros…) em cima do conteúdo indexado em um cluster Elasticsearch.
```

## Versão ELK

```
Elasticsearch: 8.2
Logstash: 7.16
Kibana: 8.2
```

## Inicia docker
```
docker-compose up -d --build
```


# Enviar dados para logstash
#### POST http://localhost:8080/
```
header:
Content-Type / application/json
Accept / application/json

{
	"data": "test"
}
```

Response:
```
{
	ok
}
```

# Enviar dados para elasticsearch

#### GET http://localhost:9200/
```
header:
Content-Type / application/json
Accept / */*
```

Response:
```
{
    "name": "52714b9074c3",
    "cluster_name": "docker-cluster",
    "cluster_uuid": "l8gBjzl8SqyPQgQC1UftNw",
    "version": {
        "number": "8.2.0",
        "build_flavor": "default",
        "build_type": "docker",
        "build_hash": "b174af62e8dd9f4ac4d25875e9381ffe2b9282c5",
        "build_date": "2022-04-20T10:35:10.180408517Z",
        "build_snapshot": false,
        "lucene_version": "9.1.0",
        "minimum_wire_compatibility_version": "7.17.0",
        "minimum_index_compatibility_version": "7.0.0"
    },
    "tagline": "You Know, for Search"
}
```