---
description: "Revisa rascunho que voce escreveu: aplica checklist OAB+LGPD, ajusta ritmo e vocabulario pro seu tom configurado, devolve versao polida + diff curto explicando o que mudou."
---

# /legalized-revisar — Revisao de rascunho

Voce vai invocar a persona Legalized pra revisar um texto que o proprio advogado escreveu — checa OAB, polir, alinhar ao tom configurado.

## Protocolo

### Passo 1 — Coletar entrada

Se o usuario nao passou texto, pergunte:

> "Cola o rascunho que voce quer revisar.
>
> E me diz:
> - **Manter tom original** ou **adaptar pro meu tom configurado**?
> - **Canal**: WhatsApp ou email
> - **Destinatario** (se relevante pro check OAB): cliente / lead / parte contraria / outro"

### Passo 2 — Invocar Legalized em modo revisao

```
Task({
  subagent_type: "legalized-jur",
  description: "Revisar rascunho do advogado",
  prompt: "MODO: revisao-rascunho\n\nTexto: <rascunho colado>\nManter: <tom original | adaptar pro meu tom configurado>\nCanal: <WhatsApp | Email>\nDestinatario: <categoria pra check OAB>\n\nDevolva: [bandeiras OAB se houver] + VERSAO POLIDA + lista do que mudou e por que."
})
```

### Passo 3 — Apresentar

Mostre exatamente o que a Legalized devolveu. Termine com:

> "Quer enviar assim, ajustar algo, ou pedir uma 2a opcao em outro tom?"

## Quando usar /legalized-revisar (vs /legalized-redigir)

| Use revisar | Use redigir |
|-------------|-------------|
| Voce ja tem um rascunho pronto | Voce so tem o objetivo |
| So quer checar OAB+LGPD | Quer 2-3 opcoes diferentes |
| So quer polir ritmo e vocabulario | Quer ver direcoes alternativas de tom |
| Mensagem urgente que voce ja escreveu | Mensagem que pode esperar 1 min de redacao |

## Tipos de ajuste comuns que a Legalized aplica

- Mascarar CPF / abreviar numero de processo (LGPD)
- Substituir promessa de resultado por "vamos trabalhar com..." (Check OAB 1)
- Trocar vocabulario pra bater com seu `tom.vocabulario_proprio` (ex: "o caso" → "seu processo" se voce configurou assim)
- Quebrar paragrafo longo demais pra leitura no celular
- Remover emoji caso tenha escapado
- Adicionar CTA consultivo se ficou faltando
- Confirmar abertura especifica (substituir "Ola" vazio por nome)
- Ajustar assinatura conforme `tom.assinatura_estruturada` do perfil
