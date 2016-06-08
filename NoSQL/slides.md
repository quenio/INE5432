name: inverse
layout: true
class: center, middle, inverse
---
template: inverse
# NoSQL
.footnote[Gilherme - Quenio - Ranieri]
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

    - Não usam o SQL como linguagem de consulta.
]
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
]
.right-column[
- Não seguem o modelo relacional.

    - Não usam o SQL como linguagem de consulta.

- Tem sua própria linguagem ou API para consultas.

    - MongoDB tem uma linguagem de consulta baseada em JSON.

    - CouchDB permite visões materializadas usando MapReduce.

- Porém, alguns têm linguagem de consulta baseada no SQL.

    - Cassandra: CQL - Cassandra Query Language
]

???

Pesquisar:
- CQL
- Visões MapReduce do CouchDB 
---
layout: false
.left-column[
  ### Não-Relacional
  ### Sem SQL
  ### _Open-Source_
]
.right-column[
- Não seguem o modelo relacional.

    - Não usam o SQL como linguagem de consulta.

- Tem sua própria linguagem ou API para consultas.

    - MongoDB tem uma linguagem de consulta baseada em JSON.

    - CouchDB permite visões materializadas usando MapReduce.

- Porém, alguns têm linguagem de consulta baseada no SQL.

    - Cassandra: CQL - Cassandra Query Language

- Na maioria, projetos open-source.
    - Porém, já existem algumas opções comerciais.
]

???

Pesquisar:
- Opções comerciais
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

    - Alguns focam na modelagem de dados mais complexos.

    - Como é o caso dos Graph Databases.
]
    
???
    
Pesquisar:
    - Sharding
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
- Baseadas em tabelas _hash_.
    
    - Para cada chave há um valor.
    
    - Tipos de valores: lists, sets, hashes, strings, numbers, object (em alguns)
    
    - Tipos de operações: range, diff, union, intersection
]

???

Exemplo em código.

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
|--------------:|----|:------------------|
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
    
        - Pedidos

    - _Caching_
    
        - Opções do Pedido
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
    
        - Pedidos

    - _Caching_
    
        - Opções do Pedido
- Deficiências:

    - Dados com relacionamentos

    - Transações
    
        - Aplicação precisa implementar _locking_.

    - Consultas por valores ao invés de chaves
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
| Relacional    |    | Document Databases |
|--------------:|----|:-------------------|
| Table         | -> | Collection         |
| Row           | -> | Document           |
| Row Id        | -> | _id                |
| Join          | -> | DBRef (MongoDB)    |
]

???

- Exemplo de código

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
## _Column-Family Stores_
]
.right-column[
- Armazena dicionários de tuplas.

    - Cada tupla pode ter campos diferentes.
    
    - Estrutura flexível; não é definida por _schema_.
]

???

- Pesquisar

---
layout: false
.left-column[
## _Column-Family Stores_
### Exemplos
]
.right-column[
- Armazena dicionários de tuplas.

    - Cada tupla pode ter campos diferentes.
    
    - Estrutura flexível; não é definida por _schema_.
    
- Exemplos:
    
    - Cassandra
    
    - HBase
    
    - HyperTable
    
    - SimpleDB
]
---
layout: false
.left-column[
## _Column-Family Stores_
### Exemplos
### Terminologia
]
.right-column[
| Relacional    |    | Column-Family Stores |
|--------------:|----|:---------------------|
| Database      | -> | Keyspace             |
| Table         | -> | Column Family        |
| Row           | -> | Row                  |
| Column        | -> | Column (pode variar em cada Row) |
]

???

- Exemplo em código.

---
layout: false
.left-column[
## _Column-Family Stores_
### Exemplos
### Terminologia
### Casos de Uso
]
.right-column[
- Casos de uso típicos:

    - _Event Logging_
    
    - _Analytics_

    - _Statistics_ / _Data Analysis_
]
    
    
???
    
- Pesquisar
    
---
layout: false
.left-column[
## _Column-Family Stores_
### Exemplos
### Terminologia
### Casos de Uso
### Deficiências
]
.right-column[
- Casos de uso típicos:

    - _Event Logging_
    
    - _Analytics_

    - _Statistics_ / _Data Analysis_

- Deficiências:

    - Dados com relacionamentos

    - Transações
        - No Cassandra, transação é atomica no nível de _rows_.

    - Consistência:
        - QUORUM: Cassandra tem não tem master; escrita e leitura em qualquer nó.
]
---
layout: false
.left-column[
## _Graph Databases_
]
.right-column[
- Permitem armazenar entidades e seus relacionamentos mais complexos.

    - São baseados grafos com nós e suas ligações.
    
    - Ambos os nodos e ligações podem ter propriedades associadas.
]
---
layout: false
.left-column[
## _Graph Databases_
### Exemplos
]
.right-column[
- Permitem armazenar entidades e seus relacionamentos mais complexos.

    - São baseados grafos com nós e suas ligações.
    
    - Ambos os nodos e ligações podem ter propriedades associadas.
    
- Exemplos: 
    
    - Neo4J
    
    - Infinite Graph
    
    - FlockDB
]
---
layout: false
.left-column[
## _Graph Databases_
### Exemplos
### Terminologia
]
.right-column[
| Relacional    |    | Graph Databases |
|--------------:|----|:----------------|
| Table Row     | -> | Node            |
| Relation Row  | -> | Links           |
| Column        | -> | Property        |
]
---
layout: false
.left-column[
## _Graph Databases_
### Exemplos
### Terminologia
### Casos de Uso
]
.right-column[
- Casos de uso típicos:

    - Relacionamentos complexos de dados
    
    - Aplicações de roteamento
        - Na área de transporte, por exemplo.
        
    - Logística
        
    - Localização
        
    - Serviços de recomendação    
]
---
layout: false
.left-column[
## _Graph Databases_
### Exemplos
### Terminologia
### Casos de Uso
### Deficiências
]
.right-column[
- Deficiências:
        
    - _Bulk update_
        
    - _Bancos de dados muito grandes_
        
    - Transação / Consistência
        - NeoJ oferece ACID no master e replicação para os slaves.
        - Infinite Graph oferece distribuição de nós entre o cluster. 
]
---
layout: false
.left-column[
## _SQL + Documents_
]
.right-column[
- Oracle suporta JSON and XML como tipos de dados nativos
    
    - Provê transações, indices, consultas, views.

    - Permite fazer JOIN entre tabelas e JSON + XML.

    - Também permite projetas dados JSON + XML como se fossem tabelas.

    - Consultar JSON + XML armazenado fora do banco de dados.
]
---
layout: false
.left-column[
## _SQL + Documents_
### Exemplos
]
.right-column[
_Schema_:

```sql
CREATE TABLE j_purchaseorder
   (id          RAW (16) NOT NULL,
    date_loaded TIMESTAMP WITH TIME ZONE,
    po_document CLOB
    CONSTRAINT ensure_json CHECK (po_document IS JSON));
```

Inserir _JSON_:

```sql
INSERT INTO j_purchaseorder
  VALUES (SYS_GUID(),
          SYSTIMESTAMP,
          '{"PONumber"             : 1600,
            "Reference"            : "ABULL-20140421",
            "Requestor"            : "Alexis Bull",
            "User"                 : "ABULL",
            "CostCenter"           : "A50",
            "ShippingInstructions" : {...},
            "AllowPartialShipment" : true,
            "LineItems"            : [...]}');
```

Consultar _JSON_:

```sql
SELECT po.po_document.PONumber 
    FROM j_purchaseorder po;
SELECT po.po_document.ShippingInstructions.Phone 
    FROM j_purchaseorder po;
```
]
---
layout: false
.left-column[
## _Referências_
]
.right-column[
- _NoSQL Distilled_
    - Autores: Pramod J. Sadalage & Martin Fowler

- _Seven Databases in Seven Weeks_
    - Autores: Eric Redmond & Jim R. Wilson
    - Redis, Neo4J, CouchDB, MongoDB, HBase, Riak, and Postgres
]
---
template: inverse
# MongoDB & Redis
