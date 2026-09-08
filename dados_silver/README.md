# Análise Preliminar de Dados

Este diretório contém a base de dados utilizada no projeto e a documentação sobre o seu tratamento inicial.



## Análise Preliminar e Tratamento

A análise preliminar e o tratamento dos dados foram realizados através do notebook `analise_preliminar.ipynb`, com o objetivo de garantir a integridade e consistência das informações.

### Fluxo de Trabalho

1. **Verificações Iniciais**:
   
   * Análise da estrutura do arquivo `BPS_20_26_OrlandoCastro.csv`.
   * Identificação e remoção de linhas duplicadas.
   * Mapeamento de valores nulos em todas as colunas.

2. **Tratamento de Dados Nulos e Padronização**:
   
   * **Capacidades e Unidades de Medida**: Para registros onde a `unidade_fornecimento_capacidade` era igual à `unidade_fornecimento`, a `capacidade` foi fixada em `1.0` e a `unidade_medida` foi preenchida com o valor da unidade de fornecimento.
   * **Unidades Nulas**: Registros com `unidade_fornecimento` nula, mas com `unidade_medida` preenchida, foram padronizados como "unidade".
   * **Referência Temporal**: A coluna `insercao` foi removida, utilizando-se a coluna `compra` como única referência temporal para evitar inconsistências.
   * **Simplificação de Itens**: As colunas `generico` e `anvisa` foram removidas devido ao alto índice de valores nulos (aprox. 50%), mantendo-se a `descricao_catmat` para a identificação dos itens.

3. **Enriquecimento de Dados**:
   
   * **Recuperação de Instituições**: Para os 157 registros com `nome_instituicao` nulo, foi realizada uma consulta automatizada à API do [OpenCNPJ.org](https://api.opencnpj.org) utilizando o `cnpj_instituicao` para recuperar as razões sociais correspondentes.

### Resultado Final

O processo resultou na criação do arquivo consolidado e limpo: `BPS_20_26_OrlandoCastro_atualizado.csv`, apresentado aqui em formato ZIP por limitações de tamanho de upload no GitHub. Este arquivo contém os dados tratados e está pronto para ser utilizado em análises subsequentes, incluindo a modelagem dimensional descrita no diretório `dados_gold`.


