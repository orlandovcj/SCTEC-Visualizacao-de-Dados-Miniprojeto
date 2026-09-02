# Mini-Projeto Avaliativo: Dashboard Banco de Preços em Saúde (BPS)

Este repositório documenta o desenvolvimento do Mini-Projeto Avaliativo do Módulo 2, focado na criação de uma solução de Business Intelligence (BI) para análise de compras públicas de medicamentos e dispositivos médicos.

## 1. Objetivo do projeto

Desenvolver um dashboard analítico para acompanhar e explorar as compras registradas no Banco de Preços em Saúde (BPS) entre os anos de 2020 e 2026. O objetivo é transformar grandes volumes de dados públicos em informações estratégicas por meio de KPIs, métricas e visuais interativos, permitindo identificar tendências temporais, avaliar a distribuição geográfica das compras e investigar variações de preços unitários para apoiar a gestão eficiente de recursos públicos na saúde.

## 2. Contextualização do problema

A aquisição de medicamentos e materiais hospitalares por órgãos governamentais envolve um alto volume financeiro, múltiplas modalidades de compra e diversos fornecedores. A gestão desses recursos é um desafio constante. Nesse cenário, a análise de dados surge como uma ferramenta essencial para identificar variações relevantes de preços, mapear a distribuição de compras entre estados e municípios e compreender as tendências ao longo do tempo.

É importante ressaltar que diferenças nos preços unitários não implicam, por si só, irregularidades ou sobrepreço; essas variações podem estar atreladas a fatores como fabricante, apresentação do produto, quantidade adquirida, modalidade de compra e período. Portanto, o problema investigado consiste em fornecer transparência e clareza a esse volume de dados, permitindo ao gestor público formular perguntas de negócio e tomar decisões fundamentadas.

## 3. Fonte dos dados

Os dados utilizados neste projeto são públicos e foram extraídos do Portal Brasileiro de Dados Abertos do Ministério da Saúde, especificamente do **Banco de Preços em Saúde (BPS)**.

- **Link do Dataset Principal:** [https://dadosabertos.saude.gov.br/dataset/bps](https://dadosabertos.saude.gov.br/dataset/bps)
- **Dicionário de Dados Oficial:** [Dicionário de Dados do BPS](https://dadosabertos.saude.gov.br/dataset/bps/resource/0e76f527-5e7e-417d-9d0b-f46d00afb717)

A base reúne informações de compras públicas e privadas, com a finalidade de subsidiar negociações e compras mais eficientes no setor de saúde.

## 4. Procedimentos utilizados para baixar e concatenar as bases anuais

O processo de preparação e consolidação dos dados históricos seguiu as seguintes etapas técnicas:

1. **Aquisição dos dados:** Download manual dos arquivos `.csv` referentes aos anos de 2020, 2021, 2022, 2023, 2024, 2025 e 2026 diretamente do portal de dados abertos. Os dados estão disponíveis publicamente no Banco de Preços em Saúde (BPF) mantido pelo Ministério da Saúde.
2. **Inspeção estrutural:** Verificação inicial dos arquivos anuais para mapear discrepâncias de *encoding*, separadores de colunas, nomes de variáveis e tipos de dados entre os diferentes anos. **Não foram identificadas diferenças de colunas entre os anos**.
3. **Importação e Padronização:** Leitura individual dos arquivos `.csv` e agragação em um único arquivo por meio de script Python em um notebook `consolidacao_dados.ipynb`.
4. **Concatenação (*Append*):** Junção vertical das bases anuais em uma única estrutura tabular unificada, garantindo o alinhamento correto das colunas.
5. **Rastreabilidade:** Manutenção de uma coluna identificadora do ano da compra (ou derivação da data) para permitir filtragens temporais futuras.
6. **Exportação:** Geração e salvamento do arquivo consolidado final com o nome `BPS_20_26_OrlandoCastro.csv`.

## 5. Tratamentos e transformações realizadas nos dados

Após a junção dos arquivos de dados anuais em um único `.csv`, foi criado o notebook `analise_preliminar.ipynb` que realiza a análise preliminar e o tratamento dos dados, garantindo a integridade e consistência das informações antes de prosseguir com análises mais aprofundadas.

Este notebook utiliza como arquivo de entrada os dados em `BPS_20_26_OrlandoCastro.csv` e tem como resultado o arquivo de saída: `BPS_20_26_OrlandoCastro_atualizado.csv`.

Todas as etapas da preparação do arquivo de dados se encontram detalhadamente documentadas no notebook `analise_preliminar.ipynb`. 

As principais verificações incluem:

1. **Verificação de duplicidade de registros:** Foram identificados e removidos registros duplicados, garantindo que cada compra seja representada apenas uma vez no arquivo consolidado.
2. **Verificação de consistência de tipos de dados:** Foram verificadas as colunas do arquivo consolidado para garantir que os tipos de dados estejam corretos e consistentes com as definições originais dos arquivos CSV. Isso inclui a verificação de campos numéricos, datas e strings, garantindo que os dados estejam formatados corretamente para análise.
3. **Verificação de valores nulos:** Foram realizadas verificações adicionais para identificar e tratar valores nulos em colunas críticas, garantindo que os dados estejam completos e consistentes para análise. Isso inclui a verificação de campos obrigatórios, como `compra`, `descricao_catmat` e `cnpj_instituicao`, garantindo que não haja registros com informações ausentes que possam comprometer a análise.

---

*(A ser preenchido após a conclusão da Sprint 2)*

## 6. Descrição das principais colunas utilizadas

*(A ser preenchido após a conclusão da Sprint 2)*

## 7. Definição dos KPIs e das métricas

*(A ser preenchido após a conclusão da Sprint 3)*

## 8. Link ou imagens do dashboard

*(A ser preenchido após a conclusão da Sprint 4)*

## 9. Principais análises e descobertas

*(A ser preenchido após a conclusão da Sprint 5)*

## 10. Recomendações baseadas nos dados

*(A ser preenchido após a conclusão da Sprint 5)*

## 11. Limitações identificadas na base ou na análise

*(A ser preenchido após a conclusão da Sprint 5)*

## 12. Instruções para reprodução do projeto

*(A ser preenchido após a conclusão da Sprint 6)*
