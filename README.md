# CassandraDB - Apresentação e Guia Prático

## Autor

**Pedro Nicolas Costa**  
Graduando em Ciência da Computação na Universidade Municipal de São Caetano do Sul (USCS)  
Disciplina: Bancos de Dados Não Relacionais  
Professor: Ricardo Resende de Mendonça

---

## Objetivos do Trabalho

O objetivo deste trabalho é apresentar o banco de dados **CassandraDB**, explicando como ele surgiu, suas principais características técnicas e casos de uso. Também foi desenvolvido um guia prático de instalação, testes com scripts básicos e um quiz interativo para reforçar os conhecimentos abordados na apresentação.

---

## Conteúdo da Apresentação

A apresentação aborda os seguintes tópicos:

- O que é o CassandraDB?
- Como surgiu?
- Modelagem
- Linguagem de Consulta CassandraDB (CQL)
- Caso de uso real: Netflix
- Guia de instalação via Docker
- Scripts básicos para demonstração
- Quiz interativo

📄 [Clique aqui para acessar o PDF da apresentação](https://link-para-o-pdf.com)

---

## Guia de Instalação com Docker

### 1. Pré-requisitos

- [Download Docker](https://www.docker.com)
- Atualizar o WSL com ```wsl.exe --update```

### 2. Inicializar um container CassandraDB

```bash
docker pull cassandra
docker run --name cassandra-db -p 9042:9042 -d cassandra
```

---

## Scripts para Teste

Acesse o terminal e utilize o `cqlsh` para executar os comandos abaixo:

### Conectar ao Cassandra

```bash
cqlsh localhost
```

### Criar uma Tabela

```sql
CREATE KEYSPACE exemplo
WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};

USE exemplo;

CREATE TABLE usuarios (
    id UUID PRIMARY KEY,
    nome TEXT,
    email TEXT
);

INSERT INTO usuarios (id, nome, email)
VALUES (uuid(), 'Pedro', 'pedro@email.com');

SELECT * FROM usuarios;
```

---

## Quiz Interativo

Teste seus conhecimentos com perguntas relacionadas ao conteúdo apresentado:

🧠 [Acesse o Quiz sobre CassandraDB](https://link-para-o-quiz.com)

---

## Referências Bibliográficas

- [Apache Cassandra - Documentação Oficial](https://cassandra.apache.org/doc/latest/)
- [Download do Cassandra](https://cassandra.apache.org/_/download.html)
- [Docker - Site Oficial](https://www.docker.com)
- Hewitt, E. (2010). *Cassandra: The Definitive Guide*. O’Reilly Media.
- [Caso de uso na Netflix](https://netflixtechblog.com/building-netflixs-distributed-tracing-infrastructure-bb856c319304)
- https://www.baeldung.com/cassandra
- https://www.geeksforgeeks.org/apache-cassandra/

---
