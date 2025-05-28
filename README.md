# CassandraDB - Apresentação e Guia Prático

## Autor

**Pedro Nicolas Costa**  
Graduando em Ciência da Computação na Universidade Municipal de São Caetano do Sul (USCS)  
Disciplina: Bancos de Dados Não Relacionais  
Professor: Ricardo Resende de Mendonça

---

## Objetivos do Trabalho

O objetivo deste trabalho é apresentar o banco de dados **CassandraDB**, explicando como ele surgiu, suas principais características técnicas, vantagens, e casos de uso. Também foi desenvolvido um guia prático de instalação, testes com scripts básicos e um quiz interativo para reforçar os conhecimentos abordados na apresentação.

---

## Conteúdo da Apresentação

A apresentação aborda os seguintes tópicos:

- O que é o CassandraDB?
- Origem e história do projeto
- Arquitetura distribuída e modelo de dados
- Principais vantagens e desvantagens
- Caso de uso real: Netflix
- Guia de instalação com e sem Docker
- Scripts básicos para teste
- Quiz interativo

📄 [Clique aqui para acessar o PDF da apresentação](https://link-para-o-pdf.com)

---

## Guia de Instalação

### 1. Pré-requisitos

- [Java 8 ou superior](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
- [Docker (opcional)](https://www.docker.com)
- Sistema operacional Windows, Linux ou Mac

### 2. Instalação via Docker (Recomendado)

```bash
docker pull cassandra
docker run --name cassandra-db -p 9042:9042 -d cassandra
```

### 3. Instalação Manual

Você pode fazer o download manual do Cassandra diretamente pelo link abaixo e seguir o guia oficial:

🔗 [Download do Cassandra](https://cassandra.apache.org/_/download.html)

---

## Scripts para Teste

Acesse o terminal e utilize o `cqlsh` para executar os comandos abaixo:

### Conectar ao Cassandra

```bash
cqlsh localhost
```

### Criar Keyspace e Tabela

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
