etapa2_resumo.md
# 🚀 Resumo Executivo — Alavancas de Priorização (Etapa 2)

Após a estruturação do painel diagnóstico da Zoop, identificamos as seguintes alavancas críticas para atuação imediata da diretoria:

* **Alavanca 1: Monitoramento do Antifraude na Madrugada (00h-05h)**
  * **Problema:** Queda acentuada na Taxa de Aprovação acompanhada de picos de transações de alto valor (> R$ 1.500) identificadas no Top 200 de risco.
  * **Ação:** Ajustar os limiares de score de risco do antifraude especificamente para transações noturnas no canal digital.

* **Alavanca 2: Correção de Divergência de Valores por Canal**
  * **Problema:** Identificação de canais/métodos com mais de 4% de transações apresentando divergência superior a 10% entre o valor pago e o previsto.
  * **Ação:** Auditoria técnica na API do gateway de pagamento para garantir a consistência das regras de preço e descontos aplicados.

* **Alavanca 3: Mitigação de Chargebacks Reincidentes**
  * **Problema:** Concentração de disputas de chargeback em categorias e canais específicos mapeados no painel de Risco.
  * **Ação:** Implementação de dupla autenticação (3DS) nos métodos de pagamento com maior taxa de contestação.