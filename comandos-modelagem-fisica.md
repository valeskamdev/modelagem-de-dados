# Comandos SQL

Comandos usados para a modelagem física.

## Criar banco de dados

```
CREATE DATABASE exemplo_valeska CHARACTER SET utf8
```

## Entra no banco de dados para usa-lo

```
USE DATABASE exemplo_valeska; (revisar, não funcionou)
```

## Criar a tabela de fabricantes

```
CREATE TABLE fabricantes(
    id TINYINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```

## Criar a tabela de produtos

```
CREATE TABLE produtos(
    id SMALLINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricante_id TINYINT NOT NULL
);
```

## Alterando a tabela produtos para criar relacionamento a partir da coluna fabricante_id, com a coluna id da tabela fabricantes.

```
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);
```

