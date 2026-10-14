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
| 1 | `CustomerID` | `float64` | `349936.0` | Identificador do cliente |
| 2 | `idade` | `float64` | `23.0` | Idade do cliente |
| 3 | `sexo` | `str` | `Male` | Gênero do cliente |
| 4 | `tempo_como_cliente` | `float64` | `13.0` | Tempo como cliente em (dias, semanas, meses, anos?) |
| 5 | `frequencia_uso` | `float64` | `22.0` | Quantidade de usos por (dias, semanas, meses, anos?) |
| 6 | `ligacoes_callcenter` | `float64` | `2.0` | Quantidade de ligações ao suporte |
| 7 | `dias_atraso` | `float64` | `1.0` | Quantidade de (dias) em atraso  |
| 8 | `assinatura` | `str` | `Standard` | Tipo de assinatura |
| 9 | `duracao_contrato` | `str` | `Annual` | Duração do contrato |
| 10 | `total_gasto` | `float64` | `909.58` | Valor total gasto na assinatura desde o início? |
| 11 | `meses_ultima_interacao` | `float64` | `23.0` | Tempo desde última interação com o cliente em (meses) |
| 12 | `cancelou` | `float64` | `0.0` | Status de cancelamento 1 = cancelou, 0 = não cancelou |

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
| E1 | `Valores nulos` | `sexo`, `tempo_como_cliente` | `info()`: `sexo` com 49.997 não nulos (3 nulos); `tempo_como_cliente` com 49.998 não nulos (2 nulos) |
| E2 | `Colunas aparentemente inteiras lidas como decimal` | `CustomerID`, `idade`, `tempo_como_cliente`, `frequencia_uso`, `ligacoes_callcenter`, `dias_atraso`, `total_gasto`, `meses_ultima_interacao`, `cancelou`| Valores terminados por `.0` |
| E3 | `Valores lidos como STR` | `sexo`,  `assinatura` e `duracao_contrato`| Valores como: Male, Standard e Annual |

---

## 6. Novas Perguntas em Aberto

- Qual o periodo de `frequencia_uso` e `ligacoes_callcenter` (por mês? total desde o início?)
- Qual a unidade de `tempo_como_cliente` (dias, meses, anos?)
- `dias_atraso` é o atraso atual ou acumulado?
- `total_gasto` está em qual moeda e cobre qual período?
- Que tipo de "interação" `meses_ultima_interacao` mede?