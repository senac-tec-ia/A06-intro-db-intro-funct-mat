---
# ─────────────────────────────────────────────────────────────────
#  AULA 06 — 13/03/2026 (Sexta-feira)
#  BLOCO 1: D08-UC06 · Banco de Dados (3 HA)
#  BLOCO 2: D09-UC07 · Funções Matemáticas (3 HA)
# ─────────────────────────────────────────────────────────────────
theme: ./
colorSchema: dark
title: "Técnico em IA — Aula 06"
author: Leonardo Zanini
courseTitle: Técnico em Inteligência Artificial
aulaNum: "Aula 06"
bgPreset: palette
# ─────────────────────────────────────────────────────────────────
---
!-- capa da aula -->

# Aula 06
## Banco de Dados + Funções Matemáticas

*13 de março de 2026 · Primeira aula de duas novas disciplinas*

---
layout: center
card: true
bgPreset: palette
pulse: true
---

<!-- divisor de bloco 1 -->

# Bloco 1
## Desenvolvimento de Banco de Dados

*D08-UC06 · 7h10 - 9h30 · Indicadores 1 e 2*

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- [DEBATE] abertura: onde estao seus dados -->

# Onde seus dados estão guardados agora?

**Pense nos últimos 10 minutos da sua manhã...**

Você desbloqueou o celular. Abriu o WhatsApp. Viu o cardápio no iFood. Ouviu uma música no Spotify.

*Cada uma dessas ações criou ou leu dados. Mas onde eles ficam?*

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] voce produz dados sem perceber -->

# Você produz dados sem perceber

- **Toda ação digital gera um registro** — hora, local, dispositivo, duração
- O Waze sabe onde você está e como está o trânsito na sua rua agora
- O Instagram mede por quantos segundos você parou em cada post
- O Google sugere a busca antes de você terminar de digitar

> Dados não são novidade. Catálogos telefônicos, fichas de biblioteca, cadernos de recados: sempre foram bancos de dados. O que mudou foi a **escala** e a **velocidade**.

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] evolucao da organizacao de dados - parte 1 -->

# Da anotação manual à planilha pessoal

**Caderno de Recados**

*(busca manual, uma página por vez, uma pessoa por vez)*

![Caderno de recados e agenda de contatos](https://picsum.photos/seed/agenda2026/400/300)

::right::

**Planilha Excel**

*(centenas de linhas, uso pessoal, um arquivo por vez)*

![Planilha eletrônica no computador](https://picsum.photos/seed/planilha2026/400/300)

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] evolucao da organizacao de dados - parte 2 -->

# Da planilha pessoal ao banco de dados

**Planilha Excel**

*(centenas de linhas, uso pessoal, um arquivo por vez)*

![Planilha eletrônica no computador](https://picsum.photos/seed/planilha2026/400/300)

::right::

**Banco de Dados**

*(milhões de registros, múltiplos usuários simultâneos, acesso remoto)*

![Servidor de banco de dados](https://picsum.photos/seed/servidor2026/400/300)

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] N1 reconhecimento rapido -->

# Exercício rápido: é banco de dados?

**Levante a mão se você acha que o exemplo abaixo é um banco de dados:**

1. A lista de contatos do seu celular
2. Um cardápio escrito num quadro de giz
3. O histórico de pedidos do iFood
4. Uma foto salva na sua galeria
5. A playlist de músicas do Spotify

> **Spoiler:** quase todos os exemplos são ou dependem de um banco de dados. Até a foto salva nos servidores do Google Fotos conta! Vamos entender o porquê.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] excel como banco de dados -->

# Excel: o banco de dados que você já conhece

Quando você cria uma planilha com nome de alunos e notas, você está **modelando dados**. A estrutura é exatamente a mesma:

- **Planilha (aba)** — equivale a uma **tabela** no banco de dados
- **Linha** — um **registro** (um aluno, um produto, um pedido)
- **Coluna** — um **atributo** (nome, nota, telefone, cidade)
- **Célula** — um **valor individual** (o cruzamento de linha e coluna)

> Se você já usou Excel, você já praticou os conceitos fundamentais de banco de dados. O vocabulário muda, mas a lógica é a mesma.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] anatomia de uma tabela de dados -->

# Anatomia de uma tabela de dados

| id | nome | nota | cidade |
|---|---|---|---|
| 1 | Ana Silva | 8,5 | São Paulo |
| 2 | Bruno Costa | 7,2 | Campinas |
| 3 | Carla Mota | 9,0 | Santos |

**Regras de ouro de uma boa tabela:**

- Cada linha tem um **id único** — a chave primária (não se repete nunca)
- Cada coluna armazena **um único tipo de informação**
- Nenhuma célula fica vazia sem necessidade real

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] N2 monte sua tabela -->

# Exercício 01: monte uma tabela

**Contexto:** você trabalha numa loja de games e precisa organizar o estoque.

No papel ou no bloco de notas, crie uma tabela com:

1. Pelo menos **4 colunas** relevantes para um produto de games
2. Pelo menos **3 linhas** com dados fictícios
3. Defina qual coluna seria a **chave primária** (identificador único)
4. Escreva uma "pergunta" que você faria a essa tabela

> **Exemplo de pergunta:** "Quais jogos de PS5 custam menos de R$200?"
> Em banco de dados, essa pergunta vira uma **query** (consulta). É exatamente o que o SQL resolve.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] quando o excel nao basta -->

# Quando o Excel começa a "travar"

**O Excel funciona bem para:** planilhas pessoais, relatórios mensais, até ~50 mil linhas.

**O Excel sofre quando:**

- Você tem **1 milhão de registros** (pedidos de um e-commerce)
- **Várias pessoas** precisam editar ao mesmo tempo (estoque de loja)
- Dados precisam se **relacionar**: uma venda tem um cliente, que tem um endereço...
- Você precisa de **segurança**: quem pode ver o CPF dos clientes?

> O banco de dados existe exatamente para resolver esses problemas em escala.

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- [DEBATE] o tamanho do banco do ifood -->

# Qual o tamanho do "Excel" do iFood?

Em 2023, o iFood processou mais de **600 milhões de pedidos**.

Cada pedido tem: cliente, restaurante, itens, preço, horário, endereço, avaliação...

*Uma planilha com 600 milhões de linhas pesaria mais de 100 GB e travaria qualquer computador ao abrir.*

**Para isso existe o SGBD.**

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] o que e um SGBD -->

# SGBD: o programa que cuida de tudo

**SGBD** — Sistema de Gerenciamento de Banco de Dados

É o software que fica entre os dados e o usuário, garantindo:

- **Velocidade** — busca entre milhões de registros em milissegundos
- **Segurança** — controle de quem pode ver ou editar cada dado
- **Integridade** — impede dados inválidos (nota = "banana"? Bloqueado!)
- **Simultaneidade** — mil pessoas acessando ao mesmo tempo, sem conflito

**Exemplos do mercado:** MySQL (mais usado no mundo), PostgreSQL (open source robusto), SQLite (leve, está no seu celular), Oracle (grandes empresas)

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] ambiente de pratica sql -->

# Nosso laboratório de SQL hoje

Vamos usar um banco de dados real e praticar direto no navegador, sem instalar nada:

**Acesse:** `w3schools.com/sql/trysql.asp`

O banco já vem pronto com 8 tabelas reais:

| Tabela | O que é | Registros |
|---|---|---|
| `Customers` | Clientes (nome, cidade, país) | 91 |
| `Products` | Produtos (nome, preço, categoria) | 77 |
| `Orders` | Pedidos de venda | 196 |
| `Employees` | Funcionários da empresa | 10 |
| `OrderDetails` | Itens de cada pedido | 518 |

> Todo exercício desta aula é para rodar nesse editor. Abra agora e teste: `SELECT * FROM Customers`

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] excel vs sql comparacao -->

# Excel e SQL: a mesma língua, dois dialetos

## No Excel você...

- Seleciona colunas específicas para ver
- Filtra linhas por condição (ex: nota > 7)
- Ordena os resultados de A a Z
- Conta quantas linhas atendem a um critério
- Soma os valores de uma coluna

::right::

## Em SQL você escreve...

- `SELECT nome, nota`
- `FROM alunos`
- `WHERE nota > 7`
- `ORDER BY nome ASC`
- `COUNT(*)` / `SUM(nota)`

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] comando SELECT -->

# SELECT: escolha o que quer ver

**No Excel:** você oculta colunas que não precisa ou seleciona apenas as relevantes.

**Em SQL:** `SELECT` faz exatamente isso, em texto.

```sql
-- Mostrar TODAS as colunas de todos os clientes:
SELECT * FROM Customers

-- Mostrar apenas nome e país:
SELECT CustomerName, Country FROM Customers
```

- `*` significa "todas as colunas"
- Liste os nomes separados por vírgula para escolher quais exibir
- A ordem das colunas no `SELECT` define a ordem exibida

> Todo `SELECT` precisa de um `FROM`. Sem ele, o banco não sabe de qual tabela buscar.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] mini SELECT -->

# Mini-exercício: SELECT

**Tabela usada:** `Customers` (CustomerID, CustomerName, ContactName, City, Country)

**Execute no editor em `w3schools.com/sql/trysql.asp`:**

1. Mostrar **todas** as colunas de todos os clientes
2. Mostrar apenas `CustomerName` e `City`
3. Mostrar apenas `CustomerName` e `Country`

```sql
-- Dica de modelo:
SELECT ___, ___ FROM Customers
```

> Tempo: 3 minutos. Veja o resultado aparecer na tela antes de comparar com o colega.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] comando WHERE sintaxe -->

# WHERE: filtre só o que importa

**No Excel:** você usa o filtro automático para exibir apenas as linhas que atendem a uma condição.

**Em SQL:** `WHERE` faz o mesmo, em texto.

```sql
-- Clientes do Brasil:
SELECT CustomerName, City FROM Customers
WHERE Country = 'Brazil'

-- Produtos com preço maior que 50:
SELECT ProductName, Price FROM Products
WHERE Price > 50
```

> Textos usam aspas simples `'Brazil'`. Números não precisam de aspas.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] comando WHERE operadores -->

# WHERE: os operadores disponíveis

| Símbolo | Significado | Exemplo |
|---|---|---|
| `=` | igual a | `WHERE Country = 'Germany'` |
| `>` | maior que | `WHERE Price > 20` |
| `<` | menor que | `WHERE Price < 10` |
| `>=` | maior ou igual | `WHERE Price >= 20` |
| `<=` | menor ou igual | `WHERE Price <= 50` |
| `<>` | diferente de | `WHERE Country <> 'Germany'` |

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] mini WHERE -->

# Mini-exercício: WHERE

**Execute no editor. Use `Customers` e `Products`:**

1. Clientes do país `'Germany'` (mostre `CustomerName` e `City`)
2. Produtos com `Price` maior que `50` (mostre `ProductName` e `Price`)
3. Clientes da cidade `'London'` (mostre `CustomerName` e `Country`)

```sql
-- Dica de modelo:
SELECT ___, ___ FROM ___
WHERE ___ ___ ___
```

> Atenção ao tipo: `'Germany'` leva aspas simples (texto). `50` não leva aspas (número).

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] comando ORDER BY -->

# ORDER BY: decida a ordem dos resultados

**No Excel:** você clica no cabeçalho de uma coluna para ordenar de A a Z ou do maior para o menor.

**Em SQL:** `ORDER BY` faz o mesmo.

```sql
-- Produtos do mais caro ao mais barato:
SELECT ProductName, Price FROM Products
ORDER BY Price DESC

-- Clientes em ordem alfabética:
SELECT CustomerName, Country FROM Customers
ORDER BY CustomerName ASC
```

- `ASC` — crescente (padrão, pode omitir)
- `DESC` — decrescente (do maior para o menor, de Z para A)

> `WHERE` e `ORDER BY` podem ser usados juntos: escreva o `WHERE` antes do `ORDER BY`.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] mini ORDER BY -->

# Mini-exercício: ORDER BY

**Execute no editor. Use `Products` e `Customers`:**

1. Todos os produtos ordenados por `Price`, do mais caro ao mais barato
2. `ProductName` e `Price` dos produtos com `Price` menor que `20`, do mais barato ao mais caro
3. Todos os clientes em ordem alfabética de `CustomerName`

```sql
-- Dica de modelo:
SELECT ___, ___ FROM ___
WHERE ___
ORDER BY ___ ___
```

> Desafio: mostre apenas os **5 produtos mais caros**. Pesquise a palavra-chave `LIMIT`.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] funcoes de agregacao -->

# COUNT, SUM, AVG: resumindo os dados

**No Excel:** você usa `=CONT.SE(...)`, `=SOMA(...)`, `=MÉDIA(...)` no rodapé de uma coluna.

**Em SQL:** são as funções de agregação.

```sql
-- Quantos clientes existem?
SELECT COUNT(*) FROM Customers

-- Preço médio dos produtos:
SELECT AVG(Price) FROM Products

-- Produto mais caro:
SELECT MAX(Price) FROM Products

-- Produto mais barato:
SELECT MIN(Price) FROM Products
```

> Essas funções resumem várias linhas em um único número. São a base de qualquer dashboard ou relatório.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] mini agregacao -->

# Mini-exercício: COUNT e amigos

**Execute no editor. Use `Customers` e `Products`:**

1. Quantos clientes existem na tabela `Customers`?
2. Qual o preço médio dos produtos? (`AVG`)
3. Qual o preço do produto mais caro? (`MAX`)
4. **(Desafio)** Quantos clientes são da `'Germany'`?

```sql
-- Dica para o desafio: combine COUNT com WHERE
SELECT COUNT(*) FROM Customers
WHERE Country = ___
```

> Toda vez que você vê "Total: 1.847 registros" numa tela, tem um `COUNT(*)` por trás.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] N2 jogo diga em SQL -->

# Jogo rápido: diga em SQL!

**Eu descrevo a ação no Excel, você completa a palavra-chave SQL:**

| Ação descrita | Palavra-chave SQL |
|---|---|
| "Mostrar" as colunas que quero ver | `___________` |
| "De qual tabela?" pegamos os dados | `___________` |
| "Filtrar" apenas linhas que atendem a condição | `___________` |
| "Ordenar" os resultados | `___________` |

> **Respostas:** SELECT / FROM / WHERE / ORDER BY
> O SQL foi criado para soar como inglês comum: *"Select CustomerName from Customers where Country = 'Brazil'"* qualquer pessoa entende!

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] primeira query SQL -->

# Sua primeira query SQL completa

**Tabela:** `Products` com as colunas: `ProductName`, `Price`, `CategoryID`

**Pergunta:** como ver o nome e preço dos produtos que custam pelo menos R$20, do mais caro para o mais barato?

```sql
SELECT ProductName, Price
FROM Products
WHERE Price >= 20
ORDER BY Price DESC
```

**Lendo em voz alta:** selecione nome do produto e preço / da tabela Products / onde o preço for maior ou igual a 20 / ordenado por preço de forma decrescente.

> Execute agora no editor e veja o resultado real!

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] N3 traduza para SQL -->

# Exercício 02: explore o banco do W3Schools

**Use o editor em `w3schools.com/sql/trysql.asp`. Tabelas: `Products` e `Customers`.**

Escreva e execute a query para cada situação:

1. Mostre `ProductName` e `Price` de **todos** os produtos
2. Mostre produtos com `Price` **menor que 15** (os mais baratos)
3. Mostre clientes do país `'Brazil'` (quantos serão?)
4. **(Desafio)** Mostre os **5 produtos mais caros**, apenas `ProductName` e `Price` (use `LIMIT`)

> Escreva a query, execute, e confirme que o resultado faz sentido. SQL é aprendido **rodando**, não só lendo.

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- [DINAMICA] verdade ou mito BD -->

# Verdade ou Mito: Banco de Dados

**Levante a mão se você acha que é VERDADE:**

1. "Banco de dados e planilha Excel são exatamente a mesma coisa"
2. "O SGBD controla quem pode acessar ou editar os dados"
3. "SQL é uma linguagem de programação igual ao Python"
4. "Uma tabela pode ter duas linhas com o mesmo `id`"

*Vamos discutir cada uma agora, antes do intervalo!*

---
layout: center
card: true
bgPreset: palette
pulse: true
---

<!-- divisor intervalo -->

# INTERVALO
## 9h35 — 9h50

*Descanse, beba água e volte com energia para o Bloco 2!*

---
layout: center
card: true
bgPreset: palette
pulse: true
---

<!-- [ATIV AVALIATIVA] Kahoot banco de dados -->

<!--
KAHOOT — 15 PERGUNTAS — BANCO DE DADOS
Configure em kahoot.com antes da aula. Tempo sugerido: 20s por pergunta.

P1. O que é um banco de dados?
a) Um arquivo Excel com muitas linhas
b) Um sistema organizado para armazenar e consultar dados  ✅
c) Um programa de e-mail
d) Um tipo de planilha

P2. Em SQL, qual coluna identifica cada linha de forma única?
a) Coluna mestra
b) Chave primária  ✅
c) Índice central
d) Coluna padrão

P3. Qual comando SQL usamos para buscar dados em uma tabela?
a) FIND
b) GET
c) SELECT  ✅
d) SEARCH

P4. Qual palavra-chave SQL filtra os resultados por condição?
a) FILTER
b) WHERE  ✅
c) ONLY
d) LIMIT

P5. O que significa o * em SELECT * FROM Customers?
a) Multiplicar os valores
b) Selecionar apenas a primeira coluna
c) Selecionar todas as colunas  ✅
d) Contar os registros

P6. Qual função SQL conta quantas linhas existem numa tabela?
a) TOTAL()
b) SUM()
c) COUNT()  ✅
d) NUMBER()

P7. Qual a ordem correta das cláusulas SQL?
a) WHERE → SELECT → FROM
b) FROM → SELECT → WHERE
c) SELECT → FROM → WHERE  ✅
d) SELECT → WHERE → FROM

P8. Como ordenar resultados do maior para o menor em SQL?
a) ORDER BY coluna UP
b) ORDER BY coluna DESC  ✅
c) ORDER BY coluna MAX
d) SORT BY coluna DESC

P9. O que é um SGBD?
a) Uma linguagem de programação
b) Um tipo de banco de dados
c) Software que gerencia bancos de dados  ✅
d) Um comando SQL

P10. Qual SGBD é o mais usado no mundo?
a) Oracle
b) PostgreSQL
c) SQLite
d) MySQL  ✅

P11. Na analogia com Excel, uma linha de uma planilha equivale a:
a) Uma coluna no banco de dados
b) Um registro no banco de dados  ✅
c) Uma tabela no banco de dados
d) Um atributo no banco de dados

P12. Qual função SQL calcula a média de uma coluna numérica?
a) MEAN()
b) AVERAGE()
c) AVG()  ✅
d) MED()

P13. Como escrever um texto numa condição WHERE?
a) Sem aspas: WHERE Country = Brazil
b) Com aspas duplas: WHERE Country = "Brazil"
c) Com aspas simples: WHERE Country = 'Brazil'  ✅
d) Com colchetes: WHERE Country = [Brazil]

P14. O que o ORDER BY ASC faz?
a) Ordena do maior para o menor
b) Ordena de Z para A
c) Ordena do menor para o maior  ✅
d) Não ordena nada, é o padrão

P15. Qual a principal vantagem de um BD sobre o Excel?
a) O banco de dados é mais colorido
b) O banco de dados suporta fórmulas melhores
c) O banco de dados escala para milhões de registros com múltiplos usuários  ✅
d) O banco de dados é mais fácil de usar
-->

# KAHOOT: Banco de Dados

**15 perguntas sobre tudo que vimos no Bloco 1!**

Acesse **kahoot.it** no celular

**Código da sala:** *[insira o PIN aqui]*

*Quem acertar mais... ganha o respeito eterno da turma.*

---
layout: center
card: true
bgPreset: palette
pulse: true
---

<!-- divisor bloco 2 -->

# Bloco 2
## Estatística Aplicada e Lógica Matemática

*D09-UC07 · 9h50 - 12h00 · Indicadores 1, 2, 3 e 4*

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- [DEBATE] matematica no cotidiano -->

# Matemática? Você já usa todos os dias!

**Nos últimos 30 minutos, você usou matemática sem perceber:**

- Calculou quanto tempo levaria para chegar aqui
- Olhou quanto de bateria tem no celular (porcentagem!)
- Decidiu se valia pagar mais no lanche ou economizar

*Matemática não é decorar fórmulas. É a linguagem que usamos para descrever como as coisas **mudam**.*

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] o que e uma funcao matematica -->

# O que é uma função matemática?

Uma função é uma **regra** que transforma uma entrada em uma saída:

$$f(x) = \text{alguma operação com } x$$

**Entrada** → **Regra** → **Saída**

**Exemplos do dia a dia:**

- Termômetro: °C como entrada, °F como saída — a regra é $f(C) = 1{,}8C + 32$
- Uber: quilômetros percorridos como entrada, preço da corrida como saída
- Caixa de futebol: placar do jogo como entrada, resultado como saída

> Toda função tem uma entrada, uma regra e uma saída. Sem exceção.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] mapa dos 4 tipos de funcao -->

# Os 4 tipos de função que veremos hoje

| Tipo | Fórmula | Gráfico | Onde aparece |
|---|---|---|---|
| **Linear** | $f(x) = ax + b$ | Linha reta | Preço de corrida, conta de água |
| **Polinomial** | $f(x) = ax^2 + bx + c$ | Curva (parábola) | Frenagem, trajetória de bola |
| **Exponencial** | $f(x) = a \cdot b^x$ | Curva que dispara | Viral, juros compostos |
| **Logarítmica** | $f(x) = \log_b(x)$ | Curva que abranda | Escala Richter, decíbîis |

> Cada tipo descreve um **padrão de comportamento diferente**. Vamos ver cada um com seu gráfico.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] ferramenta graficos desmos -->

# Visualizando gráficos: Desmos

Para cada função, vamos visualizar o gráfico interativamente:

**Acesse:** `desmos.com/calculator`

Digite qualquer fórmula e o gráfico aparece na hora. Exemplos para testar agora:

- `y = 2x + 3`
- `y = x^2`
- `y = 2^x`
- `y = log(x)`

> Mude os números e observe **o que muda no gráfico**. Isso é o que chamamos de análise de parâmetros.

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] funcao linear -->

# Função Linear: a linha reta

$$f(x) = ax + b$$

onde **a** é a taxa de variação (inclinação) e **b** é o valor de partida (ponto fixo).

**Exemplo: corrida de aplicativo**

- Bandeirada fixa: R$4,50 — esse é o **b**
- Taxa por km: R$1,80 — esse é o **a**
- Fórmula: $f(d) = 1{,}80 \cdot d + 4{,}50$

::right::

## Reconhecendo no cotidiano

- **Plano de telefone:** taxa fixa + custo por GB extra
- **Hora extra no trabalho:** salário base + taxa por hora
- **Conta de água:** taxa mínima + preço por m³ consumido
- **Corrida de ônibus:** tarifa fixa independente da distância

**Gráfico:** linha reta crescendo para a direita. Se dobrar x, o resultado cresce de forma previsível e proporcional.

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] grafico funcao linear -->

# Função Linear: lendo o gráfico

$$f(x) = ax + b$$

**O que o parâmetro `a` controla:**
- `a > 0`: linha sobe da esquerda para a direita
- `a < 0`: linha desce da esquerda para a direita
- `|a|` maior: linha mais inclinada (mais íngreme)
- `|a|` menor: linha mais suave (quase horizontal)

**O que o parâmetro `b` controla:**
- `b` é onde a linha **cruza o eixo vertical** (valor quando x = 0)
- `b` maior: linha começa mais alta

::right::

## Teste no Desmos

Digite em `desmos.com/calculator`:

```
y = 2x + 3
```

Agora altere um parâmetro por vez e observe:

- Troque `2` por `5` → o que mudou?
- Troque `2` por `-2` → o que mudou?
- Troque `3` por `-1` → o que mudou?

> **Correlação direta:** quanto maior o `a`, mais rápido a função cresce. `a` e a inclinação são proporcionais.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] N2 calcule a corrida -->

# Exercício 03: calcule a corrida

**Um aplicativo de mobilidade cobra:**

- Bandeirada: R$4,50
- Taxa por km: R$1,80
- Taxa por minuto parado: R$0,50

**Calcule o valor para cada situação:**

1. Corrida de 5 km sem espera
2. Corrida de 8 km com 3 minutos parado no trânsito
3. **(Desafio)** Com R$25,00 no bolso e sem tempo de espera, qual é a distância máxima que você consegue percorrer?

> Escreva a função matemática **antes** de calcular: $f(d) = ?$

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] parametros correlacao linear -->

# Parâmetros e correlação: o que cada número controla?

**Na fórmula $f(x) = ax + b$, cada parâmetro tem uma correlação direta com o gráfico:**

| Parâmetro | Significado real | Efeito no gráfico |
|---|---|---|
| `a` grande | crescimento rápido | linha mais íngreme |
| `a` pequeno | crescimento lento | linha quase plana |
| `a` negativo | diminui conforme x sobe | linha desce |
| `b` positivo | valor inicial alto | linha começa acima do zero |
| `b` = 0 | sem valor fixo inicial | linha passa pela origem |

> Na corrida: `b` é a bandeirada (você paga mesmo sem andar). `a` é a taxa por km (quanto mais anda, mais paga). Mudar qualquer um muda **proporcionalmente** o resultado.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] funcao polinomial -->

# Função Polinomial: quando a curva aparece

$$f(x) = ax^2 + bx + c$$

A variável **x** aparece elevada a uma potência maior que 1. O gráfico não é mais uma linha reta — é uma **curva**.

**Exemplos no cotidiano:**

- **Distância de frenagem de um carro:** dobrar a velocidade não dobra a distância, **quadruplica** (regra do quadrado)
- **Trajetória de uma bola jogada para cima:** sobe e desce desenhando uma parábola
- **Área de uma sala:** se você dobra o lado, o espaço fica 4 vezes maior

> Em IA: as curvas de aprendizado de modelos frequentemente seguem funções polinomiais.

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] grafico funcao polinomial -->

# Função Polinomial: lendo o gráfico

$$f(x) = ax^2 + bx + c$$

**O que o parâmetro `a` controla:**
- `a > 0`: parábola abre para **cima** (forma de tigela)
- `a < 0`: parábola abre para **baixo** (forma de morro)
- `|a|` maior: curva mais estreita e acentuada
- `|a|` menor: curva mais aberta e suave

**O parâmetro `c`:**
- Desloca toda a curva para cima ou para baixo
- É o valor quando $x = 0$

::right::

## Teste no Desmos

Digite em `desmos.com/calculator`:

```
y = x^2
```

Agora altere:

- Troque por `y = 2x^2` → o que mudou?
- Troque por `y = -x^2` → o que mudou?
- Troque por `y = x^2 + 3` → o que mudou?
- Troque por `y = x^2 - 2x + 1` → o que mudou?

> A parábola **nunca é uma linha reta**. Mesmo que cresca, ela cresce cada vez mais rápido.

---
layout: brainstorm
card: true
bgPreset: palette
pulse: true
---

<!-- [DEBATE] crescimento viral -->

# Já viu isso acontecer?

**Um post que do nada explode no Instagram...**

Na 1ª hora: 10 curtidas

Na 2ª hora: 100 curtidas

Na 3ª hora: 1.000 curtidas

Na 4ª hora: 10.000 curtidas

*Qual é o padrão? Cada hora **multiplica** o resultado por 10.*

**Isso não é função linear. É algo completamente diferente.**

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] funcao exponencial -->

# Função Exponencial: crescimento que explode

$$f(x) = a \cdot b^x \quad \text{onde } b > 1$$

A diferença fundamental: **x é o expoente**, não a base. O crescimento acelera cada vez mais rápido.

**Exemplos extremos:**

- **Viral nas redes:** cada compartilhamento gera mais compartilhamentos
- **Juros compostos:** R$1.000 a 10% ao ano vira R$2.594 em 10 anos
- **Crescimento de dados na internet:** o volume dobra aproximadamente a cada 2 anos

> Para a IA: o crescimento de dados que alimenta os modelos é exponencial. Por isso os modelos recentes são muito mais poderosos que os de 5 anos atrás.

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] grafico funcao exponencial -->

# Função Exponencial: lendo o gráfico

$$f(x) = a \cdot b^x$$

**O que o parâmetro `b` controla (a base):**
- `b > 1`: crescimento exponencial (curva dispara para cima)
- `0 < b < 1`: decrescimento exponencial (curva despenca, como bateria descarregando)
- Quanto maior `b`, mais rápido o crescimento

**O que o parâmetro `a` controla:**
- É o valor inicial (quando $x = 0$)
- Escala toda a curva verticalmente
- Não muda a **forma**, muda o **ponto de partida**

::right::

## Teste no Desmos

Digite em `desmos.com/calculator`:

```
y = 2^x
```

Agora altere:

- Troque por `y = 3^x` → cresce mais rápido ou mais devagar?
- Troque por `y = 0.5^x` → o que acontece?
- Troque por `y = 2 * 2^x` → o que mudou?

> Correlação: `b` e a **velocidade do crescimento** são diretamente proporcionais quando `b > 1`.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] funcao logaritmica -->

# Função Logarítmica: comprimindo escalas gigantes

$$f(x) = \log_b(x)$$

O logaritmo é o **inverso** da exponencial. Serve para **comparar coisas muito diferentes** numa mesma escala visual.

**Por que isso é necessário?**

- **Escala Richter:** um terremoto 7.0 não é "um pouco" maior que 6.0, é **10 vezes** mais poderoso
- **Decibéis:** uma conversa normal (60 dB) não é o dobro de um sussurro (30 dB) em termos de energia sonora
- **Faturamento de empresas:** comparar startup com R$100 mil e gigante com R$100 bilhões na mesma escala

> Em IA: a função `log` aparece na fórmula de **entropia cruzada**, que é como os modelos medem o próprio erro durante o treinamento.

---
layout: two-cols-text
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] grafico funcao logaritmica -->

# Função Logarítmica: lendo o gráfico

$$f(x) = \log_b(x)$$

**Características do gráfico:**
- Começa crescendo rápido e vai **desacelerando** (o oposto da exponencial)
- Nunca é definida para $x \leq 0$ (não existe log de zero ou negativo)
- Sempre cruza o eixo horizontal em $x = 1$ (pois $\log_b(1) = 0$ para qualquer base)

**Correlação com a base `b`:**
- Base maior: curva cresce mais lentamente
- Base menor (próxima de 1): curva cresce mais rápido
- É o **espelho horizontal** da exponencial de mesma base

::right::

## Teste no Desmos

Digite em `desmos.com/calculator`:

```
y = log(x)
```

Agora compare lado a lado:

```
y = log(x)
y = 10^x
```

- Observe que as duas são **espelhos** em relação à linha $y = x$
- Isso confirma que log e exponencial são **funções inversas**

> Sempre que um fenômeno "desacelera com o tempo", há uma logarítmica por trás.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [TEORIA] comparando os 4 tipos -->

# Comparando os 4 tipos: como identificar pelo comportamento

**A grande questão: como saber qual tipo usar?**

Observe o que acontece quando você **dobra o valor de x**:

| O que acontece com o resultado | Tipo provável |
|---|---|
| Dobra também (cresce de forma igual, constante) | Linear |
| Quadruplica (cresce ao quadrado) | Polinomial grau 2 |
| Aumenta muito mais que dobrar (multiplica por fator enorme) | Exponencial |
| Aumenta, mas bem pouco (vai desacelerando) | Logarítmica |

**Teste rápido no Desmos:** abra `desmos.com/calculator` e coloque as 4 ao mesmo tempo:

```
y = 2x + 1
y = x^2
y = 2^x
y = log(x)
```

> Compare as 4 curvas lado a lado. A exponencial ultrapassa todas as outras para x grande.

---
layout: default
card: true
bgPreset: palette
pulse: true
---

<!-- [EXERCICIO] N3 identifique a funcao -->

# Exercício 04: identifique o tipo de função

**Para cada situação, indique qual tipo melhor descreve o comportamento:**

**Linear / Polinomial / Exponencial / Logarítmica**

1. O preço de um táxi: R$3,00 fixo + R$2,00 por km
2. A trajetória de uma bola lançada para o alto
3. O número de views de um vídeo que viralizou
4. A escala de magnitudes de terremotos (Richter)
5. A área de um quadrado em função do comprimento do lado


---
layout: end
card: true
github: LeoZanini
avatar: https://github.com/LeoZanini.png?size=256
bgPreset: palette
pulse: true
---

# Até a próxima aula!

## O que vem por aí

Banco de Dados: modelagem com múltiplas tabelas e SQL intermediário.

Estatística: probabilidade e medidas de tendência central no cotidiano.

