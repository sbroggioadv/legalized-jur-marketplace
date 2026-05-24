---
description: "Traduz texto juridico (peticao, decisao, ementa, clausula, sentenca, despacho) em linguagem que cliente leigo entende, sem perder a essencia. Feature exclusiva do Legalized Jur."
---

# /legalized-traduzir — Tradutor pro cliente leigo

Voce vai invocar a persona Legalized pra traduzir um texto juridico em portugues comum, no formato pronto pra enviar ao cliente.

## Protocolo

### Passo 1 — Coletar entrada

Se o usuario nao passou texto, pergunte:

> "Cola o texto que voce quer traduzir (decisao, clausula, peticao, ementa, sentenca, despacho). Pode ser pedaco ou inteiro.
>
> E me diz tambem:
> - **Cliente**: nome + situacao (ex: 'Fernando, comprou imovel com vicios, leigo')
> - **Profundidade**: resumo curto / explicacao media / desdobramento detalhado
> - **Canal**: WhatsApp / email / documento pra imprimir"

### Passo 2 — Invocar Legalized em modo traducao

```
Task({
  subagent_type: "legalized-jur",
  description: "Traduzir juridiques pro cliente leigo",
  prompt: "MODO: traducao-leigo\n\nTexto: <texto juridico colado>\nCliente: <nome + situacao>\nProfundidade: <curto | media | detalhada>\nCanal de entrega: <WhatsApp | Email | Documento>\n\nDevolva traducao no formato padrao (O que aconteceu / O que significa pra voce / Por que o juiz decidiu assim / Proximos passos)."
})
```

### Passo 3 — Apresentar

Mostre a traducao na integra. Termine com:

> "Quer (a) enviar assim, (b) encurtar pra WhatsApp, (c) adicionar mais contexto, (d) refazer com tom mais formal ou mais proximo?"

## Casos de uso tipicos

- Decisao judicial que o cliente vai ler no email
- Clausula de contrato que o cliente vai assinar
- Sentenca que precisa explicar antes de decidir recorrer
- Ementa de acordao usada como base de defesa
- Despacho que parece grave mas e so providencia processual
- Peticao da parte contraria que assustou o cliente

## O que ESTA fora deste modo

- Parecer juridico pro cliente (use seu proprio raciocinio + Legalized so pra redigir)
- Resumo de processo (use `/legalized-redigir` com tipo "status")
- Traducao tecnica pra outro advogado (esses entendem; nao precisa traduzir)
