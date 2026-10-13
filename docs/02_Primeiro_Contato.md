# Etapa 2 — Primeiro Contato com o Arquivo (Extract) | Cancelamento de Clientes

> Regra: aqui só se **olha**. Nada de limpar, corrigir ou calcular.

## 1. Ficha Técnica do Arquivo

| Parâmetro | Valor |
|---|---|
| **Caminho / nome do arquivo** | `../data/raw/cancelamentos.csv` |
| **Formato** | `CSV` |
| **Tamanho em disco** | `3,34 MB` |
| **Separador (CSV)** | `,` |
| **Separador decimal** | `.` |
| **Encoding** | `UTF-8`; acentos OK? `N/A (base sem acentos)` |
| **Primeira linha é cabeçalho?** | `Sim` |
| **Abas (se Excel)** | `Não é Excel` |
| **Linhas × colunas** | `50.000 × 12` |
| **Tamanho na memória (deep)** | `11,35 MB` |
| **Início, meio e fim têm a mesma cara?** | `Sim: head, tail e sample(5) com o mesmo formato e as mesmas colunas` |

---

## 2. Inventário das Colunas

| # | Coluna | Tipo lido pelo pandas | Exemplo de valor | Significado provável (supõe-se) |
|---|---|---|---|---|
| 1 | `[coluna]` | `[int64 / float64 / object]` | `[...]` | `[...]` |
| 2 | | | | |
| 3 | | | | |

---

## 3. Conferência das Expectativas da Etapa 1

| Item | Esperado (Etapa 1) | Encontrado | Status |
|---|---|---|---|
| Granularidade | 1 linha = 1 cliente | `[...]` | ⏳ |
| Identificador | Coluna de ID única | `[nome da coluna; nunique == nº de linhas?]` | ⏳ |
| Variável alvo | Coluna de cancelamento (0/1 ou Sim/Não) | `[nome da coluna e valores]` | ⏳ |
| Dados temporais | Datas que mostrem quando cancelou | `[...]` | ⏳ |

Legenda: ✅ confirmado · ❌ refutado · ⚠️ parcial / a investigar

---

## 4. Hipóteses × Colunas Disponíveis

| # | Hipótese (resumo) | Coluna(s) de suporte | Viável testar? |
|---|---|---|---|
| H1 | Mais ligações ao suporte → mais cancelamento | `[...]` | ⏳ |
| H2 | Contrato mensal cancela mais que anual | `[...]` | ⏳ |
| H3 | Atraso > 20 dias → mais cancelamento | `[...]` | ⏳ |
| H4 | Planos mais caros cancelam mais | `[...]` | ⏳ |
| H5 | Menor uso → mais cancelamento | `[...]` | ⏳ |

Legenda: ✅ viável · ⚠️ parcial (coluna existe, mas com ressalva) · ❌ sem coluna para testar

---

## 5. Primeiras Estranhezas (só registrar, não corrigir)

| # | Observação | Coluna(s) | Evidência |
|---|---|---|---|
| E1 | `[ex.: número lido como texto]` | `[...]` | `[ex.: dtype object; valor "R$ 10,00"]` |
| E2 | `Tamanho do arquivo em memória (deep) `| | `11,35 MB` | 

---

## 6. Novas Perguntas em Aberto

- `[ex.: o que significa a coluna X, já que não há dicionário?]`
