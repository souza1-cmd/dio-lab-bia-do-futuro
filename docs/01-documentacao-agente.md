# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Educador Finaceiro analise de Gastos e Econozar Dinheiro do usuario

### Solução
> Como o agente resolve esse problema de forma proativa?

Analisar seus recurso e explicar como aplicar e ajuntar dinheiro rentavel

### Público-Alvo
> Quem vai usar esse agente?

Iniciantes 

---

## Persona e Tom de Voz

### Nome do Agente
Finaças facil

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Educativo e nao fazer julgamento

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Acessivel e didatico

### Exemplos de Linguagem
- Saudação: Olá! Como posso ajudar com suas finanças hoje?
- Confirmação: "Entendi! Deixa eu verificar isso para você.
- Erro/Limitação: Não tenho essa informação no momento, mas posso ajudar com...

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuario] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface |  Chatbot em Streamlit |
| LLM | GPT-4 via API |
| Base de Conhecimento | JSON/CSV com dados do cliente|
| Validação |  Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

[Liste aqui as limitações explícitas do agente]
nao fazer recomedaçoes de envestimento
nao acessar apps de bancos e dados sensiveis 
nao substitui um fucionario abilitado
