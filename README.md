# 📊 Business Intelligence & Analytics na Saúde (Power BI)

Este repositório apresenta arquiteturas de indicadores (KPIs), modelagem dimensional (Star Schema) e regras de negócios em DAX voltadas para a gestão estratégica de hospitais e clínicas.

---

## 🎯 O Problema de Negócio
Muitas instituições de saúde possuem grande volume de dados transacionais no ERP, mas enfrentam lentidão na tomada de decisão devido a planilhas manuais, falta de padronização de indicadores e dificuldade em cruzar dados assistenciais com resultados financeiros.

## 💡 A Solução Técnica
Desenvolvimento de painéis executivos em **Power BI** conectados diretamente a bases relacionais (SQL Server / MySQL), com foco em performance, governança de dados e clareza visual para diretoria e gerências.

### Principais Painéis Estruturados:
* **Painel Executivo de Faturamento & Glosas:** Acompanhamento diário de produção médica, faturamento enviado vs. glosado, índice de recuperação de glosas e ticket médio por convênio.
* **Controladoria de Estoque & Suprimentos:** Giro de estoque, cobertura em dias, curva ABC de consumo e alertas preventivos de ruptura ou vencimento de lotes.
* **Eficiência Operacional & PEP:** Taxa de ocupação hospitalar, tempo médio de permanência (TMP) e auditoria de registros assistenciais.

---

## ⚙️ Exemplo de Medida DAX (Índice de Glosa Técnica)

```dax
% Indice de Glosa = 
VAR ValorFaturado = SUM(fFaturamento[Valor_Apresentado])
VAR ValorGlosado = SUM(fFaturamento[Valor_Glosado])
RETURN
    DIVIDE(ValorGlosado, ValorFaturado, 0)
