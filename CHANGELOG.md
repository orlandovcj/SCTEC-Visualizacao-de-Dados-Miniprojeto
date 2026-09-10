# Changelog

Este arquivo documenta as evoluções, alterações e correções do projeto do Dashboard do Banco de Preços em Saúde (BPS).

O formato é baseado no padrão [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/), e este projeto orienta-se pelas Sprints estabelecidas nas instruções do Mini-Projeto Avaliativo.

---

## [5.0.0] - 2026-09-10

### Adicionado

- Adicionada versão final do dashboard `Dashboard_BPS.pibx`contendo cinco abas: Visão Geral, UF/Municípios, Fornecedores, Fabricantes e Materiais.
- Imagens dos paineis do dashboard foram incluídas em `/imagens`.

### Atualizado

- `README.md` atualizado com as descrições de cada aba do dashboard.

---

## [4.0.0] - 2026-09-09

### Adicionado

- Modelo dimensional (esquema estrela) importado e configurado no **Power BI Desktop**, com a tabela fato `Fato_BPS_20_2026` relacionada às sete tabelas de dimensão (`Dim_instituicoes`, `Dim_municipios`, `Dim_materiais`, `Dim_fornecedor`, `Dim_fabricante`, `Dim_modalidade_compra`, `Dim_tipo_compra`).
- Criação da tabela de medidas `Medidas_BPS`, centralizando os cálculos DAX do dashboard.
- Implementação das seis medidas obrigatórias: Valor Total Registrado, Quantidade Total de Itens, Número de Registros de Compra, Instituições Compradoras, Fornecedores e Preço Unitário Médio Ponderado (calculado via `DIVIDE`, e não por média aritmética simples).
- Construção dos paineis do dashboard, com cartões de KPI, filtros interativos (Ano, UF, Tipo de Compra, Modalidade de Compra) e cinco visuais: evolução anual de compras, valor total por UF, compras por modalidade, tipo de compra e ranking de fornecedores.
- Redação dos itens 8 (Descrição das principais colunas utilizadas) e 9 (Definição dos KPIs e das métricas) do `README.md`.
- Redação dos itens 10 a 14 do `README.md` (link/imagens do dashboard, principais análises e descobertas, recomendações baseadas nos dados, limitações identificadas e instruções para reprodução do projeto).

### Atualizado

- `README.md` atualizado com a decisão de substituir o Google Data Studio (Looker Studio) pelo Power BI como ferramenta de construção do dashboard, em razão de limitações no upload da base consolidada na ferramenta do Google.
- Renomeada a pasta `dados_tratados` (usada nas versões [2.0.0] e [3.0.0]) para `dados_silver` e `dados_gold`, separando de forma explícita a camada de dados tratados/preliminares (Prata) da camada de dados modelados em esquema estrela (Ouro), alinhando a nomenclatura das pastas à Arquitetura Medalhão descrita no `README.md`.
- Ajustada a agregação padrão da coluna `ano_compra` no modelo do Power BI para "Não resumir", evitando somatórios indevidos sobre um campo categórico/temporal.

### Corrigido

- Identificada e revisada divergência entre as colunas `preco_total`/`preco_unitario` originais e as colunas `preco_total_reais`/`preco_unitario_reais` criadas durante o tratamento no Power Query, padronizando o uso das colunas `_reais` nas medidas DAX do dashboard.

---

## [3.0.0] - 2026-09-07

### Adicionado

- Realizada a etapa de modelagem dos dados criando um esquema estrela a partir dos dados em CSV preliminarmente tratados com o uso do notebook `modelagem_dados.ipynb` na pasta `dados_tratados`.
- Resultado da modelagem de dados se encontra do arquivo `dados_tratados.zip`.
- Adicionado o `README.md`na pasta `dados_tratados`com detalhes sobre o processo de modelagem dos dados.

---

## [2.0.0] - 2026-09-02

### Adicionado

- Realizada a etapa de tratamento preliminar dos dados com o uso do notebook `analise_preliminar.ipynb` na pasta `dados`.
- Resultado do tratamento preliminar se encontra do arquivo `BPS_20_26_OrlandoCastro_atualizado.zip`.

### Atualizado

- Atualizado o `README.md` na pasta `dados` com detalhes sobre o tratamento preliminar dos dados.

---

## [1.0.0] - 2026-08-31

### Adicionado

- Criação da estrutura inicial do repositório no GitHub.
- Criação e estruturação do arquivo `README.md` contendo os 4 primeiros tópicos exigidos (Objetivo, Contextualização, Fonte dos dados e Procedimentos de concatenação).
- Criação deste arquivo `CHANGELOG.md` para versionamento das etapas.
- Download dos arquivos `.csv` do BPS referentes aos anos de 2020 a 2026 no Portal de Dados Abertos.
- Consulta ao dicionário de dados oficial para mapeamento inicial das colunas.

---
