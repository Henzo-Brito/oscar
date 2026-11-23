# Gabarito — Exercícios SQL Oscar

Banco: `oscar_database`  
Tabela: `indicados_ao_oscar`  
Colunas: `id_registro`, `ano_filmagem`, `ano_cerimonia`, `edicao_cerimonia`, `categoria`, `nome_indicado`, `nome_filme`, `vencedor`

---

## Nível 1: Primeiros Passos

### 1.1 — Total de registros

```sql
SELECT COUNT(*) AS total_registros
FROM indicados_ao_oscar;
```

### 1.2.1 — Categorias únicas

```sql
SELECT DISTINCT categoria
FROM indicados_ao_oscar
ORDER BY categoria;
```

### 1.2.2 — Quantidade de categorias únicas

```sql
SELECT COUNT(DISTINCT categoria) AS total_categorias
FROM indicados_ao_oscar;
```

### 1.3 — Primeiro ano de cerimônia

```sql
SELECT MIN(ano_cerimonia) AS primeiro_ano
FROM indicados_ao_oscar;
-- R: 1928
```

### 1.4 — Último ano de cerimônia

```sql
SELECT MAX(ano_cerimonia) AS ultimo_ano
FROM indicados_ao_oscar;
```

### 1.5 — Total de cerimônias

```sql
SELECT COUNT(DISTINCT ano_cerimonia) AS total_cerimonias
FROM indicados_ao_oscar;
```

### 1.6 — Oscar 2025 e 2026

Os dados do Oscar 2025 abaixo são reais (97ª cerimônia, março de 2025). Os do Oscar 2026 são fictícios para fins do exercício.

```sql
-- Oscar 2025 (97ª cerimônia)
INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, edicao_cerimonia, categoria, nome_indicado, nome_filme, vencedor)
VALUES
  (2024, 2025, 97, 'BEST PICTURE',                    'Protagonists Pictures',   'Anora',                      true),
  (2024, 2025, 97, 'BEST PICTURE',                    'Universal Pictures',      'The Brutalist',              false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Warner Bros.',            'Conclave',                   false),
  (2024, 2025, 97, 'BEST PICTURE',                    'A24',                     'I''m Still Here',            false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Netflix',                 'Nickel Boys',                false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Sony Pictures',           'The Substance',              false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Walt Disney Pictures',    'Wicked',                     false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Universal Pictures',      'A Complete Unknown',         false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Columbia Pictures',       'Emilia Pérez',               false),
  (2024, 2025, 97, 'BEST PICTURE',                    'Searchlight Pictures',    'September 5',                false),

  (2024, 2025, 97, 'ACTOR IN A LEADING ROLE',         'Adrien Brody',            'The Brutalist',              true),
  (2024, 2025, 97, 'ACTOR IN A LEADING ROLE',         'Timothée Chalamet',       'A Complete Unknown',         false),
  (2024, 2025, 97, 'ACTOR IN A LEADING ROLE',         'Colman Domingo',          'Sing Sing',                  false),
  (2024, 2025, 97, 'ACTOR IN A LEADING ROLE',         'Ralph Fiennes',           'Conclave',                   false),
  (2024, 2025, 97, 'ACTOR IN A LEADING ROLE',         'Sebastian Stan',          'A Different Man',            false),

  (2024, 2025, 97, 'ACTRESS IN A LEADING ROLE',       'Demi Moore',              'The Substance',              true),
  (2024, 2025, 97, 'ACTRESS IN A LEADING ROLE',       'Cynthia Erivo',           'Wicked',                     false),
  (2024, 2025, 97, 'ACTRESS IN A LEADING ROLE',       'Karla Sofía Gascón',     'Emilia Pérez',               false),
  (2024, 2025, 97, 'ACTRESS IN A LEADING ROLE',       'Mikey Madison',           'Anora',                      false),
  (2024, 2025, 97, 'ACTRESS IN A LEADING ROLE',       'Fernanda Torres',         'I''m Still Here',            false),

  (2024, 2025, 97, 'ACTOR IN A SUPPORTING ROLE',      'Kieran Culkin',           'A Real Pain',                true),
  (2024, 2025, 97, 'ACTOR IN A SUPPORTING ROLE',      'Yura Borisov',            'Anora',                      false),
  (2024, 2025, 97, 'ACTOR IN A SUPPORTING ROLE',      'Edward Norton',           'A Complete Unknown',         false),
  (2024, 2025, 97, 'ACTOR IN A SUPPORTING ROLE',      'Jeremy Strong',           'The Apprentice',             false),
  (2024, 2025, 97, 'ACTOR IN A SUPPORTING ROLE',      'Zach Galifianakis',       'A Real Pain',                false),

  (2024, 2025, 97, 'ACTRESS IN A SUPPORTING ROLE',    'Zoe Saldana',             'Emilia Pérez',               true),
  (2024, 2025, 97, 'ACTRESS IN A SUPPORTING ROLE',    'Monica Barbaro',          'A Complete Unknown',         false),
  (2024, 2025, 97, 'ACTRESS IN A SUPPORTING ROLE',    'Ariana Grande',           'Wicked',                     false),
  (2024, 2025, 97, 'ACTRESS IN A SUPPORTING ROLE',    'Felicity Jones',          'The Brutalist',              false),
  (2024, 2025, 97, 'ACTRESS IN A SUPPORTING ROLE',    'Isabella Rossellini',     'Conclave',                   false),

  (2024, 2025, 97, 'DIRECTING',                       'Sean Baker',              'Anora',                      true),
  (2024, 2025, 97, 'DIRECTING',                       'Brady Corbet',            'The Brutalist',              false),
  (2024, 2025, 97, 'DIRECTING',                       'James Mangold',           'A Complete Unknown',         false),
  (2024, 2025, 97, 'DIRECTING',                       'Jacques Audiard',         'Emilia Pérez',               false),
  (2024, 2025, 97, 'DIRECTING',                       'Coralie Fargeat',         'The Substance',              false),

  (2024, 2025, 97, 'BEST INTERNATIONAL FEATURE FILM', 'Walter Salles',           'I''m Still Here',            true),
  (2024, 2025, 97, 'BEST INTERNATIONAL FEATURE FILM', 'Jacques Audiard',         'Emilia Pérez',               false),
  (2024, 2025, 97, 'BEST INTERNATIONAL FEATURE FILM', 'Various',                 'The Girl with the Needle',   false),
  (2024, 2025, 97, 'BEST INTERNATIONAL FEATURE FILM', 'Various',                 'The Seed of the Sacred Fig', false),
  (2024, 2025, 97, 'BEST INTERNATIONAL FEATURE FILM', 'Various',                 'Flow',                       false),

  (2024, 2025, 97, 'ANIMATED FEATURE FILM',           'Various',                 'Flow',                       true),
  (2024, 2025, 97, 'ANIMATED FEATURE FILM',           'Pixar',                   'Inside Out 2',               false),
  (2024, 2025, 97, 'ANIMATED FEATURE FILM',           'Sony Pictures Animation', 'The Wild Robot',             false),

  (2024, 2025, 97, 'WRITING (Adapted Screenplay)',    'Sean Baker',              'Anora',                      true),
  (2024, 2025, 97, 'WRITING (Original Screenplay)',   'Brady Corbet; Mona Fastvold', 'The Brutalist',          true);

-- Oscar 2026 (98ª cerimônia — fictício)
INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, edicao_cerimonia, categoria, nome_indicado, nome_filme, vencedor)
VALUES
  (2025, 2026, 98, 'BEST PICTURE',               'Various',             'The Odyssey',    true),
  (2025, 2026, 98, 'BEST PICTURE',               'Various',             'Eddington',      false),
  (2025, 2026, 98, 'BEST PICTURE',               'Various',             'Materialists',   false),
  (2025, 2026, 98, 'ACTOR IN A LEADING ROLE',    'Tom Hanks',           'The Odyssey',    true),
  (2025, 2026, 98, 'ACTRESS IN A LEADING ROLE',  'Cate Blanchett',      'Eddington',      true),
  (2025, 2026, 98, 'DIRECTING',                  'Christopher Nolan',   'The Odyssey',    true);
```

---

## Nível 2: Explorando Categorias

### 2.1 — Indicações por categoria

```sql
SELECT categoria, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY categoria
ORDER BY total_indicacoes DESC;
```

### 2.2 — Categoria com mais indicações

```sql
SELECT categoria, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY categoria
ORDER BY total_indicacoes DESC
LIMIT 1;
```

### 2.3 — Categoria com menos indicações

```sql
SELECT categoria, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY categoria
ORDER BY total_indicacoes ASC
LIMIT 1;
```

### 2.4 — Último ano da categoria "ACTRESS"

```sql
SELECT MAX(ano_cerimonia) AS ultimo_ano
FROM indicados_ao_oscar
WHERE categoria = 'ACTRESS';
```

### 2.5 — Categorias da 1ª cerimônia que não existem mais

```sql
SELECT DISTINCT categoria
FROM indicados_ao_oscar
WHERE ano_cerimonia = 1928
  AND categoria NOT IN (
    SELECT DISTINCT categoria
    FROM indicados_ao_oscar
    WHERE ano_cerimonia = (SELECT MAX(ano_cerimonia) FROM indicados_ao_oscar)
  );
```

### 2.6 — Categorias com "DIRECTING" no nome

```sql
SELECT DISTINCT categoria
FROM indicados_ao_oscar
WHERE categoria LIKE '%DIRECTING%'
ORDER BY categoria;
```

---

## Nível 3: Atores e Atrizes Famosos

### 3.1 — Indicações de Natalie Portman

```sql
SELECT COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Natalie Portman%';
```

### 3.2 — Oscars de Natalie Portman

```sql
SELECT COUNT(*) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Natalie Portman%'
  AND vencedor = true;
```

### 3.3 — Anos e filmes de Natalie Portman

```sql
SELECT ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Natalie Portman%'
ORDER BY ano_cerimonia;
```

### 3.4 — Todas as indicações de Natalie Portman

```sql
SELECT ano_cerimonia, categoria, nome_filme, vencedor
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Natalie Portman%'
ORDER BY ano_cerimonia;
```

### 3.5 — Indicações de Viola Davis

```sql
SELECT COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Viola Davis%';
-- R: 4
```

### 3.6 — Oscars de Viola Davis

```sql
SELECT COUNT(*) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Viola Davis%'
  AND vencedor = true;
-- R: 1
```

### 3.7 — Filmes de Viola Davis

```sql
SELECT ano_cerimonia, categoria, nome_filme, vencedor
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Viola Davis%'
ORDER BY ano_cerimonia;
```

### 3.8 — Amy Adams já ganhou algum Oscar?

```sql
SELECT COUNT(*) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Amy Adams%'
  AND vencedor = true;
-- R: 0
```

### 3.9 — Indicações de Amy Adams sem vitória

```sql
SELECT COUNT(*) AS indicacoes_sem_vitoria
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Amy Adams%'
  AND vencedor = false;
```

### 3.10 — Denzel Washington já ganhou algum Oscar?

```sql
SELECT COUNT(*) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Denzel Washington%'
  AND vencedor = true;
-- R: 2
```

### 3.11 — Total de indicações de Denzel Washington

```sql
SELECT COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Denzel Washington%';
```

### 3.12 — Oscars de Denzel Washington

```sql
SELECT ano_cerimonia, categoria, nome_filme
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Denzel Washington%'
  AND vencedor = true
ORDER BY ano_cerimonia;
```

---

## Nível 4: Vencedores Históricos

### 4.1 — Primeira vencedora de Melhor Atriz

```sql
SELECT nome_indicado, ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE categoria = 'ACTRESS'
  AND vencedor = true
ORDER BY ano_cerimonia ASC
LIMIT 1;
-- R: Janet Gaynor, 1928, 7th Heaven
```

### 4.2 — Primeiro vencedor de Melhor Ator

```sql
SELECT nome_indicado, ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE categoria = 'ACTOR'
  AND vencedor = true
ORDER BY ano_cerimonia ASC
LIMIT 1;
-- R: Emil Jannings, 1928, The Last Command
```

### 4.3 — Total de vencedores

```sql
SELECT COUNT(*) AS total_vencedores
FROM indicados_ao_oscar
WHERE vencedor = true;
```

### 4.4 — Vencedores de Melhor Filme

```sql
SELECT ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE categoria IN ('OUTSTANDING PICTURE', 'BEST PICTURE')
  AND vencedor = true
ORDER BY ano_cerimonia;
```

### 4.5 — Filmes diferentes que já ganharam

```sql
SELECT COUNT(DISTINCT nome_filme) AS filmes_vencedores
FROM indicados_ao_oscar
WHERE vencedor = true;
```

---

## Nível 5: Análise de Indicações

### 5.1 — Indicados mais de uma vez

```sql
SELECT nome_indicado, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY nome_indicado
HAVING total_indicacoes > 1
ORDER BY total_indicacoes DESC;
```

### 5.2 — Recordista de indicações

```sql
SELECT nome_indicado, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY nome_indicado
ORDER BY total_indicacoes DESC
LIMIT 1;
```

### 5.3 — Mais de 3 indicações, zero vitórias

```sql
SELECT nome_indicado, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY nome_indicado
HAVING total_indicacoes > 3
   AND SUM(vencedor) = 0
ORDER BY total_indicacoes DESC;
```

> `SUM(vencedor)` funciona direto porque MySQL trata `true` como 1 e `false` como 0.

### 5.4 — Artistas indicados em categorias diferentes

```sql
SELECT
  nome_indicado,
  COUNT(DISTINCT categoria) AS categorias_distintas,
  GROUP_CONCAT(DISTINCT categoria ORDER BY categoria SEPARATOR ', ') AS categorias
FROM indicados_ao_oscar
GROUP BY nome_indicado
HAVING categorias_distintas > 1
ORDER BY categorias_distintas DESC;
```

### 5.5 — Indicados com exatamente 1 indicação

```sql
SELECT COUNT(*) AS indicados_uma_vez
FROM (
  SELECT nome_indicado
  FROM indicados_ao_oscar
  GROUP BY nome_indicado
  HAVING COUNT(*) = 1
) AS sub;
```

### 5.6 — Maior número de indicados em um único ano

```sql
SELECT ano_cerimonia, COUNT(*) AS total_indicados
FROM indicados_ao_oscar
GROUP BY ano_cerimonia
ORDER BY total_indicados DESC
LIMIT 1;
```

---

## Nível 6: Análise de Filmes

### 6.1 — Anos em que Toy Story ganhou

```sql
SELECT ano_cerimonia, nome_filme, categoria
FROM indicados_ao_oscar
WHERE nome_filme LIKE '%Toy Story%'
  AND vencedor = true
ORDER BY ano_cerimonia;
```

### 6.2 — Total de indicações da franquia Toy Story

```sql
SELECT COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_filme LIKE '%Toy Story%';
```

### 6.3 — Categorias da franquia Toy Story

```sql
SELECT DISTINCT categoria
FROM indicados_ao_oscar
WHERE nome_filme LIKE '%Toy Story%'
ORDER BY categoria;
```

### 6.4 — Edição em que "Crash" concorreu

```sql
SELECT DISTINCT ano_cerimonia, edicao_cerimonia
FROM indicados_ao_oscar
WHERE nome_filme = 'Crash';
```

### 6.5 — Total de indicações de "Crash"

```sql
SELECT COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_filme = 'Crash';
```

### 6.6 — "Crash" ganhou Melhor Filme?

```sql
SELECT nome_filme, categoria, vencedor
FROM indicados_ao_oscar
WHERE nome_filme = 'Crash'
  AND categoria = 'BEST PICTURE';
-- R: Sim
```

### 6.7 — "Central do Brasil" aparece no banco?

```sql
SELECT *
FROM indicados_ao_oscar
WHERE nome_filme LIKE '%Central do Brasil%'
   OR nome_filme LIKE '%Central Station%';
```

### 6.8 — Indicações de "Central do Brasil"

```sql
SELECT COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_filme LIKE '%Central do Brasil%'
   OR nome_filme LIKE '%Central Station%';
```

---

## Nível 7: Operações de Atualização

### 7.1 — Converter vencedor de string para booleano

Se a coluna for `BOOLEAN` mas os dados vieram como strings:

```sql
UPDATE indicados_ao_oscar SET vencedor = true  WHERE vencedor = 'true';
UPDATE indicados_ao_oscar SET vencedor = false WHERE vencedor = 'false';
```

Se a coluna for `VARCHAR`, migre o tipo em três passos:

```sql
ALTER TABLE indicados_ao_oscar ADD COLUMN vencedor_bool BOOLEAN;

UPDATE indicados_ao_oscar
SET vencedor_bool = CASE
  WHEN LOWER(vencedor) = 'true'  THEN true
  WHEN LOWER(vencedor) = 'false' THEN false
  ELSE NULL
END;

ALTER TABLE indicados_ao_oscar DROP COLUMN vencedor;
ALTER TABLE indicados_ao_oscar RENAME COLUMN vencedor_bool TO vencedor;
```

### 7.2 — 3 filmes que nunca foram nomeados mas merecem

```sql
INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, edicao_cerimonia, categoria, nome_indicado, nome_filme, vencedor)
VALUES
  (2002, 2003, 75, 'BEST PICTURE',          'O2 Filmes',                 'City of God',              false),
  (1999, 2000, 72, 'MUSIC (Original Score)', 'Various',                   'Princess Mononoke',        false),
  (1994, 1995, 67, 'BEST PICTURE',           'Castle Rock Entertainment', 'The Shawshank Redemption', false);
```

> "City of God" e "The Shawshank Redemption" já têm registros reais no banco. Esses INSERTs são só para o exercício.

### 7.3 — Categoria "BEST INTERNATIONAL FEATURE FILM" com vencedores recentes

```sql
INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, edicao_cerimonia, categoria, nome_indicado, nome_filme, vencedor)
VALUES
  (2019, 2020, 92, 'BEST INTERNATIONAL FEATURE FILM', 'CJ Entertainment', 'Parasite',                       true),
  (2019, 2020, 92, 'BEST INTERNATIONAL FEATURE FILM', 'Rohfilm Factory',  'Corpus Christi',                 false),
  (2019, 2020, 92, 'BEST INTERNATIONAL FEATURE FILM', 'Neon',             'Pain and Glory',                 false),
  (2020, 2021, 93, 'BEST INTERNATIONAL FEATURE FILM', 'Various',          'Another Round',                  true),
  (2020, 2021, 93, 'BEST INTERNATIONAL FEATURE FILM', 'Mubi',             'Better Days',                    false),
  (2021, 2022, 94, 'BEST INTERNATIONAL FEATURE FILM', 'MUBI',             'Drive My Car',                   true),
  (2021, 2022, 94, 'BEST INTERNATIONAL FEATURE FILM', 'Various',          'Flee',                           false),
  (2022, 2023, 95, 'BEST INTERNATIONAL FEATURE FILM', 'Mubi',             'All Quiet on the Western Front', true),
  (2022, 2023, 95, 'BEST INTERNATIONAL FEATURE FILM', 'Various',          'Argentina, 1985',                false),
  (2023, 2024, 96, 'BEST INTERNATIONAL FEATURE FILM', 'Toho',             'The Zone of Interest',           true),
  (2023, 2024, 96, 'BEST INTERNATIONAL FEATURE FILM', 'Mubi',             'Society of the Snow',            false);
```

### 7.4 — Corrigir erros nos nomes dos filmes

Os dados originais têm ponto-e-vírgula no final de alguns filmes (ex: `'The Dove;'`). Para limpar:

```sql
-- Remove ponto-e-vírgula no final
UPDATE indicados_ao_oscar
SET nome_filme = TRIM(TRAILING ';' FROM nome_filme)
WHERE nome_filme LIKE '%;';

-- Remove espaços extras nas bordas
UPDATE indicados_ao_oscar
SET nome_filme = TRIM(nome_filme)
WHERE nome_filme != TRIM(nome_filme);

-- Colapsa múltiplos espaços internos
UPDATE indicados_ao_oscar
SET nome_filme = REGEXP_REPLACE(nome_filme, '  +', ' ')
WHERE nome_filme REGEXP '  +';
```

### 7.5 — Remover registros com nome_filme NULL

```sql
-- Confira antes
SELECT * FROM indicados_ao_oscar WHERE nome_filme IS NULL;

DELETE FROM indicados_ao_oscar
WHERE nome_filme IS NULL;
```

---

## Nível 8: Análise Temporal

### 8.1 — Indicações por década

```sql
SELECT
  CONCAT(FLOOR(ano_cerimonia / 10) * 10, 's') AS decada,
  COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY decada
ORDER BY decada;
```

### 8.2 — Década com mais indicações

```sql
SELECT
  CONCAT(FLOOR(ano_cerimonia / 10) * 10, 's') AS decada,
  COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY decada
ORDER BY total_indicacoes DESC
LIMIT 1;
```

### 8.3 — Categorias únicas por década

```sql
SELECT
  CONCAT(FLOOR(ano_cerimonia / 10) * 10, 's') AS decada,
  COUNT(DISTINCT categoria) AS categorias_unicas
FROM indicados_ao_oscar
GROUP BY decada
ORDER BY decada;
```

### 8.4 — Ano com mais indicações

```sql
SELECT ano_cerimonia, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY ano_cerimonia
ORDER BY total_indicacoes DESC
LIMIT 1;
```

### 8.5 — Crescimento entre primeira e última década

```sql
SELECT
  primeira.total AS indicacoes_primeira_decada,
  ultima.total   AS indicacoes_ultima_decada,
  ROUND(((ultima.total - primeira.total) / primeira.total) * 100, 2) AS crescimento_percentual
FROM
  (SELECT COUNT(*) AS total FROM indicados_ao_oscar
   WHERE ano_cerimonia BETWEEN 1928 AND 1937) AS primeira,
  (SELECT COUNT(*) AS total FROM indicados_ao_oscar
   WHERE ano_cerimonia >= (SELECT FLOOR(MAX(ano_cerimonia) / 10) * 10 FROM indicados_ao_oscar)) AS ultima;
```

---

## Nível 9: Questões Históricas e Sociais

### 9.1 — Primeira indicação de Sidney Poitier

```sql
SELECT nome_indicado, MIN(ano_cerimonia) AS primeiro_ano, nome_filme
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Sidney Poitier%'
GROUP BY nome_indicado, nome_filme
ORDER BY primeiro_ano ASC
LIMIT 1;
```

### 9.2 — Sidney Poitier ganhou?

```sql
SELECT ano_cerimonia, nome_filme, categoria, vencedor
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Sidney Poitier%'
ORDER BY ano_cerimonia;
```

### 9.3 — Indicados em ACTOR ou ACTRESS antes de 1970

O banco não tem campo de etnia, então a query retorna todos os indicados nessas categorias antes de 1970. A identificação de quem é negro exige pesquisa externa.

```sql
SELECT DISTINCT nome_indicado, ano_cerimonia, nome_filme, vencedor
FROM indicados_ao_oscar
WHERE categoria IN ('ACTOR', 'ACTRESS')
  AND ano_cerimonia < 1970
ORDER BY ano_cerimonia;
-- Marcos conhecidos: Dorothy Dandridge (1954), Sidney Poitier (1958)
```

### 9.4 — Filmes dirigidos por mulheres que ganharam Oscar

O banco não tem campo de gênero. A query filtra por nomes conhecidos:

```sql
SELECT nome_indicado, ano_cerimonia, nome_filme, categoria
FROM indicados_ao_oscar
WHERE categoria LIKE '%DIRECTING%'
  AND vencedor = true
  AND nome_indicado IN (
    'Kathryn Bigelow', 'Jane Campion', 'Sofia Coppola',
    'Greta Gerwig', 'Coralie Fargeat'
  )
ORDER BY ano_cerimonia;
-- Kathryn Bigelow (The Hurt Locker, 2010) foi a primeira.
```

### 9.5 e 9.6 — Denzel Washington e Jamie Foxx no mesmo ano

```sql
SELECT
  d.ano_cerimonia,
  d.nome_indicado AS denzel, d.nome_filme AS filme_denzel, d.vencedor AS denzel_venceu,
  j.nome_indicado AS jamie,  j.nome_filme AS filme_jamie,  j.vencedor AS jamie_venceu
FROM indicados_ao_oscar d
JOIN indicados_ao_oscar j
  ON d.ano_cerimonia = j.ano_cerimonia
  AND d.categoria = j.categoria
WHERE d.nome_indicado LIKE '%Denzel Washington%'
  AND j.nome_indicado LIKE '%Jamie Foxx%';
-- R: 2005 — Jamie Foxx ganhou por "Ray", Denzel concorreu por "Man on Fire"
```

### 9.7 — Mesmo filme vencendo múltiplas categorias na mesma cerimônia

```sql
SELECT ano_cerimonia, nome_filme, COUNT(*) AS categorias_vencidas
FROM indicados_ao_oscar
WHERE vencedor = true
GROUP BY ano_cerimonia, nome_filme
HAVING categorias_vencidas > 1
ORDER BY categorias_vencidas DESC;
```

---

## Nível 10: Análise Avançada

### 10.1 — Filmes que ganharam Melhor Filme e Melhor Diretor na mesma cerimônia

```sql
SELECT bp.ano_cerimonia, bp.nome_filme
FROM indicados_ao_oscar bp
JOIN indicados_ao_oscar dir
  ON bp.ano_cerimonia = dir.ano_cerimonia
  AND bp.nome_filme   = dir.nome_filme
WHERE bp.categoria  IN ('OUTSTANDING PICTURE', 'BEST PICTURE')      AND bp.vencedor  = true
  AND dir.categoria IN ('DIRECTING', 'DIRECTING (Dramatic Picture)') AND dir.vencedor = true
ORDER BY bp.ano_cerimonia;
```

### 10.2 — Filme com mais indicações em uma única cerimônia

```sql
SELECT ano_cerimonia, nome_filme, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
GROUP BY ano_cerimonia, nome_filme
ORDER BY total_indicacoes DESC
LIMIT 1;
```

### 10.3 — Filme com maior taxa de conversão

```sql
SELECT
  nome_filme,
  COUNT(*)           AS total_indicacoes,
  SUM(vencedor)      AS total_vitorias,
  ROUND(SUM(vencedor) / COUNT(*) * 100, 2) AS taxa_conversao_pct
FROM indicados_ao_oscar
WHERE nome_filme IS NOT NULL
GROUP BY nome_filme
HAVING total_indicacoes >= 3
ORDER BY taxa_conversao_pct DESC
LIMIT 10;
```

### 10.4 — Atores indicados em anos consecutivos

```sql
SELECT a.nome_indicado, a.ano_cerimonia AS ano1, b.ano_cerimonia AS ano2
FROM indicados_ao_oscar a
JOIN indicados_ao_oscar b
  ON a.nome_indicado    = b.nome_indicado
  AND b.ano_cerimonia   = a.ano_cerimonia + 1
GROUP BY a.nome_indicado, ano1, ano2
ORDER BY a.nome_indicado, ano1;
```

### 10.5 — Média de indicações por cerimônia

```sql
SELECT ROUND(COUNT(*) / COUNT(DISTINCT ano_cerimonia), 2) AS media_indicacoes_por_cerimonia
FROM indicados_ao_oscar;
```

### 10.6 — Indicados em categorias principais cujo filme teve só uma indicação

```sql
SELECT i.nome_indicado, i.ano_cerimonia, i.categoria, i.nome_filme, i.vencedor
FROM indicados_ao_oscar i
JOIN (
  SELECT nome_filme, ano_cerimonia
  FROM indicados_ao_oscar
  GROUP BY nome_filme, ano_cerimonia
  HAVING COUNT(*) = 1
) AS filmes_com_uma
  ON i.nome_filme     = filmes_com_uma.nome_filme
  AND i.ano_cerimonia = filmes_com_uma.ano_cerimonia
WHERE i.categoria IN (
  'ACTOR', 'ACTRESS',
  'ACTOR IN A LEADING ROLE', 'ACTRESS IN A LEADING ROLE',
  'OUTSTANDING PICTURE', 'BEST PICTURE'
)
ORDER BY i.ano_cerimonia;
```

---

## Nível 11: Desafios Complexos

### 11.1 — Top 10 filmes mais premiados

```sql
SELECT nome_filme, SUM(vencedor) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_filme IS NOT NULL
GROUP BY nome_filme
ORDER BY oscars_ganhos DESC
LIMIT 10;
```

### 11.2 — Top 10 artistas mais indicados

```sql
SELECT nome_indicado, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_indicado IS NOT NULL
GROUP BY nome_indicado
ORDER BY total_indicacoes DESC
LIMIT 10;
```

### 11.3 — Mais de 5 indicações e 0 vitórias

```sql
SELECT nome_indicado, COUNT(*) AS total_indicacoes
FROM indicados_ao_oscar
WHERE nome_indicado IS NOT NULL
GROUP BY nome_indicado
HAVING total_indicacoes > 5
   AND SUM(vencedor) = 0
ORDER BY total_indicacoes DESC;
```

### 11.4 — Categoria com menos vencedores diferentes

```sql
SELECT categoria, COUNT(DISTINCT nome_indicado) AS vencedores_distintos, SUM(vencedor) AS total_vitorias
FROM indicados_ao_oscar
WHERE vencedor = true
GROUP BY categoria
ORDER BY vencedores_distintos ASC
LIMIT 10;
```

### 11.5 — Competitividade por categoria

```sql
SELECT
  categoria,
  COUNT(*) AS total_indicacoes,
  COUNT(DISTINCT ano_cerimonia) AS cerimonias,
  ROUND(COUNT(*) / COUNT(DISTINCT ano_cerimonia), 2) AS media_indicados_por_cerimonia
FROM indicados_ao_oscar
GROUP BY categoria
ORDER BY media_indicados_por_cerimonia DESC;
```

### 11.6 — Filmes indicados em um ano e vencedores em outro

```sql
SELECT
  a.nome_filme,
  a.ano_cerimonia AS ano_indicacao, a.categoria AS categoria_indicacao,
  b.ano_cerimonia AS ano_vitoria,   b.categoria AS categoria_vitoria
FROM indicados_ao_oscar a
JOIN indicados_ao_oscar b
  ON a.nome_filme    = b.nome_filme
  AND a.ano_cerimonia <> b.ano_cerimonia
  AND a.categoria     <> b.categoria
  AND a.vencedor = false
  AND b.vencedor = true
ORDER BY a.nome_filme, a.ano_cerimonia;
```

---

## Nível 12: Casos Práticos

### 12.1 — 20 filmes mais premiados

```sql
SELECT nome_filme, SUM(vencedor) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_filme IS NOT NULL
GROUP BY nome_filme
ORDER BY oscars_ganhos DESC
LIMIT 20;
```

### 12.2 — 5 filmes por década com pelo menos um Oscar

```sql
SELECT decada, nome_filme, oscars_ganhos
FROM (
  SELECT
    CONCAT(FLOOR(ano_cerimonia / 10) * 10, 's') AS decada,
    nome_filme,
    SUM(vencedor) AS oscars_ganhos,
    ROW_NUMBER() OVER (
      PARTITION BY FLOOR(ano_cerimonia / 10) * 10
      ORDER BY SUM(vencedor) DESC
    ) AS ranking
  FROM indicados_ao_oscar
  WHERE nome_filme IS NOT NULL
  GROUP BY decada, nome_filme
  HAVING oscars_ganhos > 0
) AS sub
WHERE ranking <= 5
ORDER BY decada, ranking;
```

### 12.3 — Clássicos de mais de 50 anos

```sql
SELECT nome_filme, ano_cerimonia, SUM(vencedor) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE vencedor = true
  AND ano_cerimonia <= YEAR(CURDATE()) - 50
GROUP BY nome_filme, ano_cerimonia
ORDER BY oscars_ganhos DESC;
```

### 12.4 — 5 cerimônias com mais prêmios

```sql
SELECT ano_cerimonia, edicao_cerimonia, SUM(vencedor) AS total_premios
FROM indicados_ao_oscar
GROUP BY ano_cerimonia, edicao_cerimonia
ORDER BY total_premios DESC
LIMIT 5;
```

### 12.5 — Marcos históricos

```sql
-- Primeira vencedora de Melhor Atriz
SELECT 'Primeira Melhor Atriz' AS marco, nome_indicado, ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE categoria = 'ACTRESS' AND vencedor = true
ORDER BY ano_cerimonia LIMIT 1;

-- Primeiro vencedor de Melhor Ator
SELECT 'Primeiro Melhor Ator' AS marco, nome_indicado, ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE categoria = 'ACTOR' AND vencedor = true
ORDER BY ano_cerimonia LIMIT 1;

-- Primeira diretora vencedora
SELECT 'Primeira Diretora Vencedora' AS marco, nome_indicado, ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE categoria LIKE '%DIRECTING%'
  AND vencedor = true
  AND nome_indicado = 'Kathryn Bigelow'
ORDER BY ano_cerimonia LIMIT 1;

-- Primeiro vencedor de Melhor Filme Internacional
SELECT 'Primeiro Melhor Filme Internacional' AS marco, nome_indicado, ano_cerimonia, nome_filme
FROM indicados_ao_oscar
WHERE (categoria LIKE '%FOREIGN%' OR categoria LIKE '%INTERNATIONAL%')
  AND vencedor = true
ORDER BY ano_cerimonia LIMIT 1;
```

### 12.6 — Muito indicados, nunca ganharam

```sql
SELECT nome_indicado, COUNT(*) AS indicacoes, SUM(vencedor) AS vitorias
FROM indicados_ao_oscar
WHERE nome_indicado IS NOT NULL
GROUP BY nome_indicado
HAVING indicacoes >= 4 AND vitorias = 0
ORDER BY indicacoes DESC;
```

### 12.7 — Probabilidade de filme com 10+ indicações ganhar Melhor Filme

```sql
SELECT
  COUNT(DISTINCT f.nome_filme) AS filmes_com_10_indicacoes,
  SUM(CASE WHEN bp.vencedor = true THEN 1 ELSE 0 END) AS ganharam_melhor_filme,
  ROUND(
    SUM(CASE WHEN bp.vencedor = true THEN 1 ELSE 0 END) /
    COUNT(DISTINCT f.nome_filme) * 100, 2
  ) AS probabilidade_pct
FROM (
  SELECT nome_filme, ano_cerimonia
  FROM indicados_ao_oscar
  GROUP BY nome_filme, ano_cerimonia
  HAVING COUNT(*) >= 10
) AS f
LEFT JOIN indicados_ao_oscar bp
  ON f.nome_filme     = bp.nome_filme
  AND f.ano_cerimonia = bp.ano_cerimonia
  AND bp.categoria IN ('OUTSTANDING PICTURE', 'BEST PICTURE')
  AND bp.vencedor = true;
```

### 12.8 — Média de indicações antes da primeira vitória em Melhor Ator

```sql
SELECT ROUND(AVG(indicacoes_antes), 2) AS media_indicacoes_antes_da_vitoria
FROM (
  SELECT
    nome_indicado,
    MIN(CASE WHEN vencedor = true THEN ano_cerimonia END) AS ano_vitoria,
    COUNT(CASE WHEN vencedor = false THEN 1 END) AS indicacoes_antes
  FROM indicados_ao_oscar
  WHERE categoria IN ('ACTOR', 'ACTOR IN A LEADING ROLE')
  GROUP BY nome_indicado
  HAVING ano_vitoria IS NOT NULL
) AS sub;
```

### 12.9 — Categorias com vencedores mais previsíveis

```sql
SELECT categoria, nome_indicado, COUNT(*) AS vezes_venceu
FROM indicados_ao_oscar
WHERE vencedor = true AND nome_indicado IS NOT NULL
GROUP BY categoria, nome_indicado
HAVING vezes_venceu > 1
ORDER BY vezes_venceu DESC
LIMIT 20;
```

---

## Nível 13: Queries Criativas

### 13.1 — Filmes que começam com "The" e ganharam Oscar

```sql
SELECT DISTINCT nome_filme, SUM(vencedor) AS oscars_ganhos
FROM indicados_ao_oscar
WHERE nome_filme LIKE 'The %'
  AND vencedor = true
GROUP BY nome_filme
ORDER BY oscars_ganhos DESC;
```

### 13.2 — Indicados com nome composto (hífen)

```sql
SELECT DISTINCT nome_indicado
FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%-%'
ORDER BY nome_indicado;
```

### 13.3 — Cerimônias com empate (múltiplos vencedores na mesma categoria)

```sql
SELECT ano_cerimonia, categoria, COUNT(*) AS vencedores
FROM indicados_ao_oscar
WHERE vencedor = true
GROUP BY ano_cerimonia, categoria
HAVING vencedores > 1
ORDER BY ano_cerimonia;
```

### 13.4 — 5 vencedores de Melhor Filme aleatórios

```sql
SELECT nome_filme, ano_cerimonia
FROM indicados_ao_oscar
WHERE categoria IN ('OUTSTANDING PICTURE', 'BEST PICTURE')
  AND vencedor = true
ORDER BY RAND()
LIMIT 5;
```

### 13.5 — Número de palavras nos títulos vencedores de Melhor Filme

```sql
SELECT
  LENGTH(nome_filme) - LENGTH(REPLACE(nome_filme, ' ', '')) + 1 AS num_palavras,
  COUNT(*) AS quantidade_filmes
FROM indicados_ao_oscar
WHERE categoria IN ('OUTSTANDING PICTURE', 'BEST PICTURE')
  AND vencedor = true
  AND nome_filme IS NOT NULL
GROUP BY num_palavras
ORDER BY num_palavras;
```

---

## Nível 14: Dashboard Completo

### 14.1 — Tudo em uma query

```sql
SELECT
  (SELECT COUNT(*) FROM indicados_ao_oscar)                              AS total_indicacoes,
  (SELECT COUNT(DISTINCT ano_cerimonia) FROM indicados_ao_oscar)         AS total_cerimonias,
  (SELECT COUNT(*) FROM indicados_ao_oscar WHERE vencedor = true)        AS total_vencedores,
  (SELECT COUNT(DISTINCT categoria) FROM indicados_ao_oscar)             AS total_categorias_unicas,

  (SELECT categoria FROM indicados_ao_oscar
   GROUP BY categoria ORDER BY COUNT(*) DESC LIMIT 1)                   AS categoria_mais_indicacoes,

  (SELECT nome_filme FROM indicados_ao_oscar
   WHERE nome_filme IS NOT NULL
   GROUP BY nome_filme ORDER BY SUM(vencedor) DESC LIMIT 1)             AS filme_mais_premiado,

  (SELECT nome_indicado FROM indicados_ao_oscar
   WHERE nome_indicado IS NOT NULL
   GROUP BY nome_indicado ORDER BY COUNT(*) DESC LIMIT 1)               AS artista_mais_indicado,

  (SELECT CONCAT(FLOOR(ano_cerimonia / 10) * 10, 's')
   FROM indicados_ao_oscar
   GROUP BY FLOOR(ano_cerimonia / 10) * 10
   ORDER BY COUNT(*) DESC LIMIT 1)                                      AS decada_mais_indicacoes;
```

---

## Referência: estrutura da tabela

| Coluna              | Tipo         | Descrição                              |
|---------------------|--------------|----------------------------------------|
| `id_registro`       | INT PK AI    | Identificador único                    |
| `ano_filmagem`      | INT NOT NULL | Ano de lançamento do filme             |
| `ano_cerimonia`     | INT          | Ano da cerimônia                       |
| `edicao_cerimonia`  | INT NOT NULL | Número da edição                       |
| `categoria`         | VARCHAR(255) | Nome da categoria                      |
| `nome_indicado`     | VARCHAR(512) | Nome do indicado                       |
| `nome_filme`        | VARCHAR(255) | Título do filme                        |
| `vencedor`          | BOOLEAN      | `true` = ganhou, `false` = não ganhou  |
