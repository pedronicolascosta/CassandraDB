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

```cql
CREATE TABLE IF NOT EXISTS usuarios (
    id UUID PRIMARY KEY,
    nome TEXT,
    email TEXT,
    telefone TEXT
);
```

### Inserindo 5 Registros

```cql
-- Inserir com todos os dados
INSERT INTO usuarios (id, nome, email, telefone)
VALUES (uuid(), 'Ana Silva', 'ana@email.com', '11999990001');

-- Sem telefone
INSERT INTO usuarios (id, nome, email)
VALUES (uuid(), 'Carlos Lima', 'carlos@email.com');

-- Sem email
INSERT INTO usuarios (id, nome, telefone)
VALUES (uuid(), 'Mariana Costa', '11988880002');

-- Apenas nome
INSERT INTO usuarios (id, nome)
VALUES (uuid(), 'João Mendes');

-- Nome e email
INSERT INTO usuarios (id, nome, email)
VALUES (uuid(), 'Luciana Rocha', 'luciana@email.com');

);
```

### Select

```cql
SELECT * FROM usuarios;
```

### Update

```cql
UPDATE usuarios SET telefone = '11999997777'
WHERE id = ;
```

### Delete de coluna

```cql
DELETE telefone FROM usuarios
WHERE id = ;
```

### Delete de linha

```cql
DELETE FROM usuarios
WHERE id = ;
```

### Delete All

```cql
TRUNCATE usuarios;
```
---

## Quiz Interativo

Teste seus conhecimentos com perguntas relacionadas ao conteúdo apresentado:

🧠 [Acesse o Quiz sobre CassandraDB](https://link-para-o-quiz.com)

---

## Referências Bibliográficas

- [Apache Cassandra - Documentação Oficial](https://cassandra.apache.org/doc/latest/)
- [Docker - Site Oficial](https://www.docker.com)
- [Caso de uso na Netflix](https://netflixtechblog.com/building-netflixs-distributed-tracing-infrastructure-bb856c319304)