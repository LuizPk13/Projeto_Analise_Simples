# 01 - Entendimento do Contexto

## 1. Identificação
| Campo | Descrição |
|---|---|
| **Projeto** | Projeto de Análise de Cancelamento de Clientes |
| **Autor** | Luiz Fernando de Jesus Silva Homem |
| **Data de Início** | 07/10/2026 |
| **Fonte dos dados** | Base da Hashtag / Disponibilizado via Kaggle |
| **Período coberto** | Não informado na origem |
| **Natureza dos Dados** | Anonimizados |
| **Documentação/Dicionário de dados** | Não disponível (será inferido analisando as colunas) |

---

## 2. Pergunta de Negócio
* **Pergunta Principal:**
    > Por que os clientes estão cancelando o contrato?
* **Público-alvo:** Time de Marketing / Retenção.
* **Decisão apoiada:** Criação de campanhas e ações direcionadas para reduzir a taxa de cancelamento (`?`).
* **Critério de Conclusão (Entregável):** Identificar os 3 principais fatores que mais impactam o cancelamento e apresentar recomendações práticas.

---

## 3. Subperguntas Testáveis
*Quebrando a pergunta principal em partes menores que possam ser respondidas com um único número ou gráfico.*

|| Subpergunta Testável |
|---|---|
| <h3>Por que os clientes cancelam?<h3> | ° Clientes com mensalidades/planos mais caros cancelam mais do que os de planos básicos?<br>° Clientes com menor frequência de uso ou engajamento cancelam mais?<br>° O número de ligações para o suporte (atendimento ruim/não resolvido) aumenta o cancelamento?<br>? Clientes com atraso recorrente no pagamento cancelam mais?|

---

## 4. Expectativas sobre os Dados (Pré-análise)
- **Granularidade Esperada (O que uma linha deve representar?):**
    > 1 linha - 1 cliente único
- **Variável Alvo (Qual coluna representa o que quero explicar/prever?):**
    > Coluna indicativa de cancelamento (ex: `churn` ou `cancelado`, com valores Sim/Não ou 1/0)
- **Definições de Termos do Negócio:**
    > Cancelar = Rescisão formal do contrato identificada na base de dados.

---

## 5. Hipóteses Iniciais
| Hipótese | Status |
|---|---|
| Clientes que entram em contato com o suporte técnico mais de 3 vezes por mês têm uma taxa de cancelamento significativamente maior. | ⏳ Pendente |
| O tipo de contrato (ex: mensal vs. anual) é o fator mais determinante para o churn; contratos mensais cancelam muito mais. | ⏳ Pendente |
| Atrasos superiores a 20 dias na fatura antecedem o cancelamento definitivo. | ⏳ Pendente |

---

## 6. Perguntas em Aberto
* Quais colunas exatas compõem essa base da Hashtag?
* O dataset possui dados temporais que permitam ver *quando* os clientes costumam cancelar (ex: após o 3º mês)?