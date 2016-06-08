name: inverse
layout: true
class: center, middle, inverse
---
template: inverse
# NoSQL
---
template: inverse
## Características
NoSQL
---
layout: false
.left-column[
  ### Não-Relacional
]
.right-column[
- Não seguem o modelo relacional.
    - Não são padronizados no SQL.
]
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
]
.right-column[
- Não seguem o modelo relacional.
    - Não são padronizados no SQL.

- Tem sua própria linguagem ou API para consultas.
    - Porém, alguns têm linguagem de consulta baseada no SQL.
    - MongoDB tem uma linguagem de consulta baseada em JSON.
    - CouchDB permite visões materializadas usando MapReduce.
    - Cassandra: CQL - Cassandra Query Language
]
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
  ### _Open-Source_
]
.right-column[
- Não seguem o modelo relacional.
    - Não são padronizados no SQL.

- Tem sua própria linguagem ou API para consultas.
    - Porém, alguns têm linguagem de consulta baseada no SQL.

- Na maioria, projetos open-source.
    - Porém, já existem algumas opções comerciais.
]
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
  ### _Open-Source_
  ### _Clustering_
]
.right-column[
- Muitos foram projetados para ambientes de cluster.
    - Máquina de pequeno porte.
    - Porém, suportam um número grande de máquinas distribuídas.
    - _Clustering_ / _Sharding_ / _Master-Slave_

- Nem todos foram projetados para _Clustering_.
    - Alguns focam em modelar dados mais complexos.
    - Como é o caso dos Graph Databases.
]
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
  ### _Open-Source_
  ### _Clustering_
  ### Não-ACID
]
.right-column[
- Opções de consistência mais fracas do que transações ACID.
    - Aplicações precisam garantir a integridade dos dados.
    - Porém mais escaláveis para aplicações Big Data.
]
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
  ### _Open-Source_
  ### _Clustering_
  ### Não-ACID
  ### Sem _Schema_
]
.right-column[
- Opções de consistência mais fracas do que transações ACID.
    - Aplicações precisam garantir a integridade dos dados.
    - Porém mais escaláveis para aplicações Big Data.

- Não possuem _data schema_.
    - Permitem que campos sejam adicionados aos registros livremente.
    - Sem alteração prévia da estrutura de dados.
]
---
template: inverse
## Tipos
NoSQL
---
layout: false
.left-column[
## _Key-Value Stores_
]
.right-column[
- Baseadas em tabelas _hash_
    
    - Para cada chave há um valor.
    
    - Tipos de valores: lists, sets, hashes, strings, numbers, object (em alguns)
    
    - Tipos de operações: range, diff, union, intersection
]
---
layout: false
.left-column[
## _Key-Value Stores_
### Exemplos
]
.right-column[
- Baseadas em tabelas _hash_

    - Para cada chave há um valor.

    - Tipos de valores: lists, sets, hashes, strings, numbers, object (em alguns)

    - Tipos de operações: range, diff, union, intersection
    
- Exemplos:

    - Redis

    - Riak 

    - BerkeleyDB

    - DynamoDB

    - Voldermot
]
---
layout: false
.left-column[
## _Key-Value Stores_
### Exemplos
### Terminologia
]
.right-column[
| Relacional    |    | Key-Values Stores |
|--------------:|----|-------------------|
| Database      | -> | Cluster           |
| Table         | -> | Bucket (Riak)     |
| Row           | -> | Key-Value         |
| Row Id        | -> | Key               |
]
---
layout: false
.left-column[
## _Key-Value Stores_
### Exemplos
### Terminologia
### Casos de Uso 
]
.right-column[
- Casos de uso típicos:

    - _Session Data_

    - _Caching_
]
---
layout: false
.left-column[
## _Key-Value Stores_
### Exemplos
### Terminologia
### Casos de Uso
### Deficiências
]
.right-column[
- Casos de uso típicos:

    - _Session Data_

    - _Caching_
    
- Deficiências:

    - Dados com relacionamentos

    - Transações

    - Consultas por valores ao invés de chaves

    - Agregação de dados
]
---
layout: false
.left-column[
## _Document Databases_
]
.right-column[
- Baseados em documents XML, JSON, BSON, etc.

    - Dados auto-descritivos
    
    - Hierárquicos 
    
    - Estruturados
]
---
layout: false
.left-column[
## _Document Databases_
### Exemplos
]
.right-column[
- Baseados em documents XML, JSON, BSON, etc.

    - Dados auto-descritivos
    
    - Hierárquicos 
    
    - Estruturados
    
- Exemplos:
    
    - MongoDB
    
    - CouchDB
    
    - OrientDB
    
    - RavenDB
]
---
layout: false
.left-column[
## _Document Databases_
### Exemplos
### Terminologia
]
.right-column[
| Relacional    |    | Key-Values Stores |
|--------------:|----|-------------------|
| Table         | -> | Collection        |
| Row           | -> | Document          |
| Row Id        | -> | _id (MongoDB)     |
| Join          | -> | DBRef (MongoDB)   |
]
---
layout: false
.left-column[
## _Document Databases_
### Exemplos
### Terminologia
### Casos de Uso
]
.right-column[
- Casos de uso típicos:

    - _Content Management_
    
    - _Event Logging_
    
    - _Analytics_
]
---
layout: false
.left-column[
## _Document Databases_
### Exemplos
### Terminologia
### Casos de Uso
### Deficiências
]
.right-column[
- Dificuldade de agregação de dados na consultas
    - Porém, permitem fazer consultas no conteúdo de documentos.
    - Alguns oferecem suporte a _MapReduce_.

- Transações
    - Atomicidade somente por documento.
    - RavenDB permite transações em mais de uma operação.

- Consistência
    - Cliente pode escolher:
        - O número de _slaves_ de uma escrita antes da operação sem considerada bem-sucedida.
        - Se permite leitura dos _slaves_ ou não.

]
---
layout: false
.left-column[
## _Document Databases_
]
.right-column[
]
---
template: inverse
# MongoDB