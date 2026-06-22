# 📊 Zoop - Finanças, Performance & Prevenção de Perdas

Este repositório contém a solução analítica de ponta a ponta desenvolvida para a fintech **Zoop**. O projeto integra engenharia de dados, modelagem dimensional e inteligência de negócios para monitorar a saúde financeira da operação, identificar gargalos de desempenho e diagnosticar anomalias como fraudes e chargebacks.

---

## 🛠️ Tecnologias Utilizadas
* **Python** (Pandas / Inspeção, Higienização e Engenharia de Dados)
* **Power BI Desktop** (Modelagem Dimensional Star Schema e Design de Dashboards)
* **DAX** (Criação de métricas canônicas de negócio e lógica condicional)
* **Markdown / Git** (Documentação, governança e versionamento)

---

## 📁 Estrutura do Projeto
O repositório está organizado de forma a garantir a governança e a rastreabilidade das decisões tomadas:

```text
├── 📁 data/
│   ├── 📄 fato_vendas_pagamentos.csv  # Tabela fato unificada e enriquecida via Python
│   ├── 📄 top200_suspeitas.csv         # Ranking inicial de risco baseado em heurísticas
│   └── 📝 _report_qualidade.md         # Registro de decisões de qualidade de dados
├── 📁 notes/
│   ├── 📝 etapa2_resumo.md             # Resumo executivo com alavancas estratégicas
│   └── 📊 alert_log.csv                # Log de governança e monitoramento de alertas
├── 🐍 etl_process.py                   # Script Python de engenharia e tratamento de dados
├── 📄 dashboard_zoop_diagnostico.pbix  # Arquivo principal do Power BI
└── 📝 README.md                        # Documentação principal do repositório
