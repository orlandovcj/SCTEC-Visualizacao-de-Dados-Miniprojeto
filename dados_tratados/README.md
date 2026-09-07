# Dados Tratados - Banco de Preços em Saúde (BPS)

Este diretório contém os arquivos resultantes do processamento de dados realizado no notebook `criacao_base_dados.ipynb`. O objetivo desta etapa foi transformar a base de dados bruta e consolidada em um modelo dimensional (**Star Schema**) para otimizar a performance de consultas e viabilizar a importação para ferramentas de BI (como Google Data Studio), superando limitações de tamanho de arquivo.

## ⚙️ Processamento e Etapas

O processamento foi realizado utilizando **Python** e **DuckDB**, seguindo as etapas abaixo:

### 1. Importação de Dados
Os dados do arquivo `BPS_20_26_OrlandoCastro_atualizado.csv` foram carregados para o DuckDB em uma tabela temporária denominada `bps_data`.

### 2. Modelagem Dimensional (Star Schema)
A base foi decomposta em tabelas de dimensões e uma tabela fato para eliminar a redundância de dados e normalizar as informações:

#### Tabelas de Dimensões
Foram criadas tabelas específicas para cada entidade, onde cada registro único recebeu um identificador numérico (chave primária):
- **Dim_instituicoes**: Cadastro de órgãos compradores (`cod_instituicao`).
- **Dim_municipios**: Localidades das compras (`cod_municipio`).
- **Dim_materiais**: Catálogo de itens, indexado pelo `codigo_br`.
- **Dim_fornecedor**: Cadastro de empresas fornecedoras (`cod_fornecedor`).
- **Dim_fabricante**: Cadastro de fabricantes (`cod_fabricante`).
- **Dim_modalidade_compra**: Tipos de modalidade de licitação (`cod_modalidade`).
- **Dim_tipo_compra**: Tipos de compra (`cod_tipo`).

#### Tabela Fato
A tabela `fato_BPS_20_2026` foi gerada através de JOINs entre a tabela bruta e as dimensões. Ela armazena as métricas quantitativas e as chaves estrangeiras que ligam os fatos às suas respectivas dimensões.

### 3. Exportação
Cada tabela do modelo dimensional foi exportada para o formato `.csv` com separador `;`, permitindo que sejam carregadas individualmente em ferramentas de análise.

## 📂 Estrutura de Arquivos
- `fato_BPS_20_2026.csv`: Tabela central com as métricas de compras.
- `Dim_*.csv`: Tabelas de suporte com os atributos de cada dimensão.

**Os arquivos CSV foram compactados em um arquivo ZIP por questões de limitação no tamanho de upload de arquivos no GitHub e praticidade de download.**
