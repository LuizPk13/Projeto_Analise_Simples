# Etapa 1 — Entendimento do Contexto | Cancelamento de Clientes

## 1. Identificação

| Campo | Descrição |
|---|---|
| **Projeto** | Análise de Cancelamento de Clientes |
| **Autor** | Luiz Fernando de Jesus Silva Homem |
| **Data de início** | 07/10/2026 |
| **Fonte dos dados** | Base da Hashtag Treinamentos, disponibilizada via Kaggle |
| **Período coberto** | Não informado na origem |
| **Natureza dos dados** | Supõe-se anonimizados (sem documentação que confirme; podem ser sintéticos) |
| **Documentação / dicionário** | Não disponível; será inferido a partir das colunas |
| **Contato prévio com a base** | `[Sim: já vi a base em aula, e as hipóteses são influenciadas por isso]` |

---

## 2. Pergunta de Negócio

**Pergunta principal:**
> Por que os clientes estão cancelando o contrato?

| Item | Descrição |
|---|---|
| **Público** | Time de Marketing / Retenção |
| **Decisão apoiada** | Criar campanhas e ações direcionadas para reduzir a taxa de cancelamento |
| **Entregável (critério de pronto)** | Identificar os 3 fatores mais associados ao cancelamento e propor recomendações práticas para cada um |

> Observação: a análise mede **associação**, não causa. "Associado ao cancelamento" ≠ "causa o cancelamento".

---

## 3. Hipóteses e Subperguntas Testáveis

Cada hipótese é uma **afirmação**; cada subpergunta pode ser respondida com **um número ou um gráfico**.

| # | Hipótese (afirmação) | Subpergunta testável | Status |
|---|---|---|---|
| H1 | Clientes que ligam mais para o suporte cancelam mais. | A taxa de cancelamento aumenta conforme cresce o nº de ligações ao suporte? | ⏳ |
| H2 | Clientes com contrato mensal cancelam mais que os de contrato anual. | Qual a taxa de cancelamento por tipo de contrato? | ⏳ |
| H3 | Clientes com atraso de pagamento superior a 20 dias cancelam mais. | A taxa de cancelamento de quem atrasa > 20 dias é maior que a taxa geral? | ⏳ |
| H4 | Clientes de planos mais caros cancelam mais que os de planos básicos. | Qual a taxa de cancelamento por plano / faixa de valor? | ⏳ |
| H5 | Clientes que usam menos o serviço cancelam mais. | A taxa de cancelamento diminui conforme a frequência de uso aumenta? | ⏳ |

**Critério de "diferença relevante":** taxa do grupo ≥ 10 pontos percentuais acima da taxa geral, em grupos de tamanho razoável (evitar conclusões sobre grupos muito pequenos).

**Nota:** os cortes exatos (ex.: "mais de 3 ligações", "20 dias") serão revistos depois de conhecer a unidade e a distribuição das colunas (Etapas 2 e 3).

---

## 4. Expectativas sobre os Dados (a confirmar na Etapa 2)

| Item | Expectativa |
|---|---|
| **Granularidade** | 1 linha = 1 cliente único |
| **Identificador** | Uma coluna de ID com um valor único por cliente |
| **Variável alvo** | Coluna indicando cancelamento (ex.: `churn`, `cancelou`), com valores Sim/Não ou 1/0 |

**Definições de termos do negócio:**
- **Cancelar:** rescisão formal do contrato, identificada na base pela variável alvo.

---

## 5. Perguntas em Aberto

- Quais colunas compõem a base?
- Existem dados temporais (datas) que permitam ver **quando** os clientes cancelam (ex.: após o 3º mês)?
- Em que unidade estão medidos uso, ligações e atraso (total, por mês, dias corridos)?
- Qual o período de referência da base?