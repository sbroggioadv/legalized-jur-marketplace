---
description: "Redige uma mensagem nova (WhatsApp ou email) no tom configurado pelo advogado. Aplica checklist OAB+LGPD automatico e devolve 1-3 opcoes adaptativas."
---

# /legalized-redigir — Redacao de mensagem nova

Voce vai invocar a persona Legalized pra redigir uma mensagem nova.

## Protocolo

### Passo 1 — Coletar briefing

Se o usuario nao passou nenhum argumento ou contexto, pergunte (use AskUserQuestion ou pergunte direto):

> "Pra eu redigir, preciso saber:
> - **Destinatario**: nome + papel (ex: Carolina, cliente trabalhista)
> - **Objetivo**: o que voce quer comunicar (1-2 frases)
> - **Canal**: WhatsApp ou email
> - **Contexto extra** (opcional): processo, prazo, valor, historico relevante"

Se o usuario passou o briefing direto (em texto livre ou estruturado), use como esta.

### Passo 2 — Invocar Legalized

Use o Task tool:

```
Task({
  subagent_type: "legalized-jur",
  description: "Redigir mensagem WhatsApp/email",
  prompt: "BRIEFING:\n\nDestinatario: <nome + papel>\nCategoria: <inferida>\nObjetivo: <o que comunicar>\nTipo: <inferido — status / proposta / cobranca / etc>\nContexto: <contexto extra>\nCanal: <WhatsApp | Email>\nModo: redacao-tecnica\n\nDevolva 1-3 opcoes adaptativas com flags de risco sinalizadas."
})
```

### Passo 3 — Apresentar saida

Mostre exatamente o que a Legalized devolveu — nao reformate, nao resuma, nao "melhore".

Termine com:

> "Quer enviar a Opcao N? Te ajusto, te dou mais variantes ou refaço com outro tom — e so falar."

### Passo 4 — Iteracao

Se o usuario pedir ajuste, reinvoque a Legalized com o pedido especifico:

```
"Refazer a Opcao 2 com tom mais frio, e cortar a referencia ao prazo."
```

## Atalhos aceitos

O usuario pode invocar voce de varias formas:

```
/legalized-redigir
[briefing livre]

/legalized-redigir email pra carolina, proposta de honorarios pro caso novo dela

/legalized-redigir
Destinatario: Marcelo (cliente)
Objetivo: avisar audiencia remarcada 24/05 14h forum Rio Preto
Canal: WhatsApp
```

Sempre passe pra Legalized sem refinar — ela tem o protocolo de inferir o que falta.
