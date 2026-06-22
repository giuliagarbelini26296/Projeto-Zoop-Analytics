_report_qualidade.md
# 📑 Relatório de Qualidade e Sanidade de Dados — Etapa 1

Este documento registra as análises de integridade, volumetria e as decisões tomadas durante a fase de limpeza e unificação das bases de dados da Zoop.

## 1. Inspeção Inicial e Tipagem
* **Datas:** Identificadas e padronizadas para o formato `YYYY-MM-DD` nas colunas de vendas e pagamentos para evitar quebras na modelagem temporal.
* **Valores Numéricos:** Campos de quantidade, preço unitário, frete e custo validados como numéricos, garantindo a execução correta dos cálculos de agregados.

## 2. Validação de Chaves e Duplicidades (PK/FK)
* **Unicidade de Vendas:** O campo `id_venda` na tabela original de vendas foi verificado e não apresentou duplicidades, garantindo que cada linha represente um evento único.
* **Transações Duplicadas (pagamentos):** Foram mapeadas ocorrências de `transaction_id` duplicados na base de pagamentos. Optou-se por **manter as duplicidades** no modelo unificado para fins de auditoria, aplicando-se a sinalização de risco (Heurística R04).
* **Integridade Referencial (Órfãos):** Verificação de consistência feita para assegurar que todas as chaves estrangeiras de `id_cliente` e `id_produto` na tabela fato possuam correspondência exata em suas respectivas tabelas de dimensão.

## 3. Coerência de Valores (Previsto vs. Vendido)
* **Cálculo de Verificação:** O valor previsto foi recalculado internamente através da fórmula padrão:  
  `valor_previsto_calc = receita_bruta - valor_desconto + valor_frete`
* **Análise de Divergências:** Ao comparar o valor original com o calculado, pequenas variações decorrentes de arredondamentos decimais foram ignoradas (dentro da tolerância de < 0,01). Casos com divergências relevantes (> 10%) foram mantidos e sinalizados com a `flag_divergencia` para alimentar o painel de risco.

## 4. Artefatos Gerados
* `data/fato_vendas_pagamentos.csv`: Base unificada, higienizada e enriquecida com dados de dimensões.
* `data/top200_suspeitas.csv`: Ranking contendo as 200 transações com maior score acumulado de risco com base nas heurísticas pré-definidas.