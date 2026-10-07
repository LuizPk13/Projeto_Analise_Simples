# Projeto Análise Simples

## 1. Identificação e Contexto de Origem
| Campo | Descrição |
|---|---|
| **Projeto** | Análise de Cancelamento de Clientes (Churn) |
| **Autor** | (Seu Nome) |
| **Data** | 07/10/2026 |
| **Fonte dos dados** | Base da Hashtag / Disponibilizado via Kaggle |
| **Período coberto** | Não informado na origem |
| **Tipo de dados** | Anonimizados |
| **Dicionário de dados** | Não disponível (será inferido analisando as colunas) |

---

## 2. Visão de Negócio
* **Pergunta Principal:** Por que os clientes estão cancelando o contrato?
* **Público-alvo:** Time de Marketing / Retenção.
* **Decisão apoiada:** Criação de campanhas e ações direcionadas para reduzir a taxa de cancelamento (churn).
* **Critério de sucesso (Entregável):** Identificar os 3 principais fatores que mais impactam o cancelamento e apresentar recomendações práticas.

---

## 3. Expectativa sobre os Dados (Pré-análise)
| Característica | Expectativa |
|---|---|
| **Granularidade (O que é 1 linha):** | 1 linha = 1 cliente único |
| **Variável Alvo:** | Coluna indicativa de cancelamento (ex: `churn` ou `cancelado`, com valores Sim/Não ou 1/0) |
| **Definições-chave:** | "Cancelar" = Rescisão formal do contrato identificada na base de dados. |

---

## 4. Desdobrando a Pergunta Principal (Subpergunta Testáveis)
Cada subpergunta abaixo pode ser validada cruzando os dados com a variável de cancelamento:

| Pergunta principal | Subpergunta testável |
|---|---|
| "Por que os clientes cancelam?" | • Clientes com mensalidades/planos mais caros cancelam mais do que os de planos básicos?<br>• Clientes com menor frequência de uso ou engajamento cancelam mais?<br>• O número de ligações para o suporte (atendimento ruim/não resolvido) aumenta o cancelamento?<br>• Clientes com atraso recorrente no pagamento cancelam mais? |

---

## 5. Hipóteses Iniciais (O que achamos antes de olhar)
* **Hipótese 1:** Clientes que entram em contato com o suporte técnico mais de 3 vezes por mês têm uma taxa de cancelamento significativamente maior. *(Status: ⏳ Pendente)*
* **Hipótese 2:** O tipo de contrato (ex: mensal vs. anual) é o fator mais determinante para o churn; contratos mensais cancelam muito mais. *(Status: ⏳ Pendente)*
* **Hipótese 3:** Atrasos superiores a 20 dias na fatura antecedem o cancelamento definitivo. *(Status: ⏳ Pendente)*

---

## 6. Perguntas em Aberto
* Quais colunas exatas compõem essa base da Hashtag?
* O dataset possui dados temporais que permitam ver *quando* os clientes costumam cancelar (ex: após o 3º mês)?