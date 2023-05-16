# Comandos SQL para operações de dados (CRUD)

## Resumo

- C: CREATE (criar dados usando o comando INSERT)
- R: READ (ler dados usando o comando SELECT)
- U: UPDATE (atualizar dados usando o comando UPDATE)
- D: DELETE (excluir dados usando o comando DELETE)

## INSERT

### Tabela Fabricantes

```sql
INSERT INTO fabricantes (nome) VALUES ('Microsoft');
INSERT INTO fabricantes (nome) VALUES ('Asus');
INSERT INTO fabricantes (nome) VALUES ('Dell');

INSERT INTO fabricantes (nome)
VALUES ('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```
### Tabela Produtos

```sql
INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('Ultrabook', 'Laptop de última geração com processador Intel Core I9 e memória de 16GB RAM.', 3);

INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('Tablet Android', 'Tablet com a versão 13 do Android, com tela de 10 polegadas e 64GB de armazenamento.', 6);

INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('iPhone 13 Pro Max', 'Alta durabilidade, processador XYZ 14, 128 GB de armazenamento, 6 GB de RAM e caro pra caramba.', 4);

INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('Geladeira', 'Refrigerador frost-free com acesso à Internet e bla bla bla.', 7);

INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('Xbox 123', 'Vídeo-game de última geração.', 1);

INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('iPad Mini', 'Tablet Apple com tela retina de 4k.', 4);

INSERT INTO produtos(nome, descricao, fabricante_id)
VALUES ('Ultrabook', 'Equipamento com processador AMD Ryzen, 12 GB de RAM.', 2);
```
## SELECT

### Ler dados da tabela Produtos

```sql
SELECT * FROM produtos;
SELECT nome FROM produtos;
SELECT nome, descricao FROM produtos;

-- Exercício: trazer o nome dos produtos apenas da Apple
-- Dica: use o comando WHERE para indicar a condição
SELECT nome FROM produtos WHERE fabricante_id = 4;

-- OPERADOR DIFERENTE: != OU <>
SELECT nome FROM produtos WHERE fabricante_id != 4;
SELECT nome FROM produtos WHERE fabricante_id <> 4;

-- OPERADOR OU: OR
SELECT nome, descricao FROM produtos
WHERE fabricante_id = 2 OR fabricante_id = 3;

-- ORDENANDO POR ORDEM CRESCENTE (ASC - Padrão)
SELECT nome, descricao FROM produtos ORDER BY nome;

-- ORDENANDO POR ORDEM DECRESCENTE (DESC)
SELECT nome, descricao FROM produtos ORDER BY nome DESC;

--COUNT(campo especial) é uma função de contagem de registros
SELECT COUNT(id) FROM produtos;

-- Usando AS para definir um apelido para a coluna de resultados
SELECT COUNT(id) AS quantidade FROM produtos;
```
## UPDATE (💀 SEMPRE COM WHERE!! 💀)

```sql
UPDATE fabricantes SET nome = 'Asus do Brasil' WHERE id = 2;

-- Exercício 1: na tabela de produtos, atualize o produto 'Geladeira'
-- mudando o fabricante de 'Brastemp' para 'Samsung'
UPDATE produtos SET fabricante_id = 6 WHERE id = 4;

-- Exercício 2: na tabela de produtos, referente ao produto 'Xbox 123',
-- mude o nome para 'Xbox One' e a descrição para 'Novo lançamento com parcelamento em 256x'
UPDATE produtos SET nome = 'Xbox One', descricao = 'Novo lançamento com parcelamento em 256x' 
WHERE id = 5;
```
## DELETE (💀👿 SEMPRE COM WHERE!! 👿💀)

```sql
DELETE FROM produtos WHERE id = 3;
DELETE FROM fabricantes WHERE id = 1;
```