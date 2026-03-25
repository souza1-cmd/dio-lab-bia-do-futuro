# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores dar continuidade ao atendimento mais eficiente|
| `perfil_investidor.json` | JSON | Personalizar Explicaçoes sobre as duvidas e necessidade e apredizado do cliente |
| `produtos_financeiros.json` | JSON | Conhecer o produtos disponiveis ao cliente|
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente analisar essa informaçoes em forma didatica |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

sim o componete fundo muti mercado foi alterado para fundo imobiliario pois sinto mais confiate em analise de fundo imobiliriario pois eu entendo.

---

## Estratégia de Integração

### Como os dados são carregados?
existem duas possibilidade injetar os dado diretos(Ctrl + V) ou pelo code Como exemplo abaixo
> ""
import pandas as pd
import json

# CSVs
historico = pd.read_csv('data/historico_atendimento.csv')
transacoes = pd.read_csv('data/transacoes.csv')

# JSONs
with open('data/perfil_investidor.json', 'r', encoding='utf-8') as f:
    perfil = json.load(f)

with open('data/produtos_financeiros.json', 'r', encoding='utf-8') as f:
    produtos = json.load(f)
  ""

[ex: Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt]

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?
```
text
historico do Ususario:
perfil investidor do Ususario:
produtos financeiros do Ususario:
transacoes do Ususario: ...
```
---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
