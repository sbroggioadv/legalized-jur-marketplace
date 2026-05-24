# Templates WhatsApp

Esqueletos neutros pra cada tipo de mensagem WhatsApp. A Legalized aplica o **Padrao Configurado** do advogado (tom, vocabulario, assinatura) por cima desses esqueletos.

> A biblioteca completa de 11 tipos esta detalhada em `${CLAUDE_PLUGIN_ROOT}/CLAUDE.md` secao 6.
> Esta pasta serve pra (a) referencia de consulta humana, (b) extensibilidade — voce pode adicionar tipos novos.

## Tipos disponiveis

| Tipo | Arquivo | Registro padrao |
|------|---------|-----------------|
| 1 — Status de processo | `01-status.md` | Rapido (ou Estruturado se novidade importante) |
| 2 — Primeiro contato com lead | `02-primeiro-contato.md` | Estruturado |
| 3 — Proposta de honorarios | `03-proposta.md` | Estruturado |
| 4 — Cobranca de honorarios vencidos | `04-cobranca.md` | Estruturado |
| 5 — Aviso de audiencia | `05-audiencia.md` | Rapido ou Estruturado |
| 6 — Notificacao extrajudicial informal | `06-notificacao.md` | Estruturado |
| 7 — Resposta a parte contraria | `07-parte-contraria.md` | Estruturado |
| 8 — Contato tecnico (perito/correspondente/cartorio) | `08-contato-tecnico.md` | Rapido |
| 9 — Email-template pro cliente enviar | `09-template-cliente.md` | Estruturado |
| 10 — Checklist documentos pra defesa | `10-checklist-defesa.md` | Estruturado |
| 11 — Checklist documentos pra elaboracao | `11-checklist-elaboracao.md` | Estruturado |

## Estrutura de cada template

```markdown
# Tipo N — Nome

**Quando usar:** [cenario]
**Registro:** [Rapido | Estruturado | Variavel]
**Categoria tipica de destinatario:** [...]
**Cuidado OAB:** [check relevante]

## Esqueleto

1. [bloco 1]
2. [bloco 2]
3. [bloco 3]
...

## Variacoes por preset de tom

### formal-tradicional
[exemplo]

### moderno-consultivo
[exemplo]

### amigavel-proximo
[exemplo]
```

## Como adicionar tipo novo

Crie um arquivo `12-meu-tipo.md` seguindo a estrutura acima. A Legalized vai detectar templates novos quando o usuario solicitar um tipo nao catalogado e tentar matching pela descricao.
