# Consolidação dos Dados

Este diretório contém a base de dados consolidada utilizada no projeto e a documentação sobre o processo de contatenação.

Esta pasta contém também os arquivos `.csv` referentes aos anos de 2020, 2021, 2022, 2023, 2024, 2025 e 2026 obtidos diretamente do portal de dados abertos. 

Os dados estão disponíveis publicamente no Banco de Preços em Saúde (BPF) mantido pelo Ministério da Saúde em: [https://dadosabertos.saude.gov.br/dataset/bps](https://dadosabertos.saude.gov.br/dataset/bps).

## Análise Preliminar e Consolidação

Os aquivos anuais em `.csv` foram analizados individualmente para verificar eventuais divergências de nomes e tipos de campos ao longo dos anos.

Para realizar a junção dos arquivos de dados anuais em um único .csv, foi utilziado o notebook `consolidacao_dados.ipynb` com o objetivo de garantir a integridade e consistência das informações.

### Resultado Final

O processo resultou na criação do arquivo consolidado: `BPS_20_26_OrlandoCastro.csv`, apresentado aqui em formato ZIP por limitações de tamanho de upload no GitHub. Este arquivo contém os dados de 2020 a 206 concatenados e está pronto para ser utilizado na próxima etapa de tratamento dos dados. 
