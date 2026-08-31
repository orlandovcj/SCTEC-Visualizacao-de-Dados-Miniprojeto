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
2. **Inspeção estrutural:** Verificação inicial dos arquivos anuais para mapear discrepâncias de *encoding*, separadores de colunas, nomes de variáveis e tipos de dados entre os diferentes anos. *(Nota: Adicione aqui se encontrou diferenças de colunas entre os anos e como procedeu).*
3. **Importação e Padronização:** Leitura individual dos arquivos `.csv` `[Atualizar nesta seção como foi feita essa importaão e padronização dos dados]`. Padronização dos nomes das colunas e correção de problemas de codificação de caracteres (ex: *UTF-8*).
4. **Tratamento de Tipos e Inconsistências:** Ajuste dos tipos de dados (garantindo que datas estejam no formato adequado e valores monetários/quantidades sejam numéricos). Verificação de valores nulos, vazios e avaliação de registros duplicados.
5. **Concatenação (*Append*):** Junção vertical das bases anuais em uma única estrutura tabular unificada, garantindo o alinhamento correto das colunas.
6. **Rastreabilidade:** Manutenção de uma coluna identificadora do ano da compra (ou derivação da data) para permitir filtragens temporais futuras.
7. **Exportação:** Geração e salvamento do arquivo consolidado final com o nome `BPS_20_26_OrlandoCastro.csv`.

---

*(Documentação a ser atualizada nas próximas etapas)*

## 5. Tratamentos e transformações realizadas nos dados

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
