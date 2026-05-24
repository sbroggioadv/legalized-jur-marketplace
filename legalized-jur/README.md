# Legalized Jur

> Copywriter juridico de alta performance para advogados brasileiros — instalavel em Claude Code, Claude Desktop e Cowork.

**Legalized** e uma persona de IA especializada em redacao juridica. Voce instala em segundos, configura seu perfil profissional uma unica vez (nome, OAB, escritorio, tom de escrita), e passa a ter um redator de WhatsApp, email e tradutor de juridiques que escreve **como voce escreveria**, com checklist OAB embutido em toda saida.

---

## O que ele faz

| Modo | Saida |
|------|-------|
| **Redacao tecnica** | WhatsApp/email no seu tom, para clientes, leads, parte contraria, perito, correspondente, cartorio, time interno ou grupo |
| **Traducao pro cliente leigo** | Pega texto juridico (peticao, decisao, ementa, clausula contratual) e traduz em linguagem simples que o cliente entende sem perder a essencia |
| **Revisao de rascunho** | Voce escreve, Legalized polui ritmo, aplica seu padrao, e checa OAB antes de aprovar |
| **Compliance automatico** | Toda saida passa por 5 checks: promessa de resultado, dados sensiveis, captacao, publicidade abusiva, alinhamento tom-categoria |

---

## Por que existe

Advogado bom escreve diferente. Cada escritorio tem um tom. O cliente quer clareza, a parte contraria quer formalidade, o perito quer objetividade tecnica, o grupo de cliente quer didatismo. Mais: cada mensagem precisa respeitar Estatuto da Advocacia (Lei 8.906/94), Codigo de Etica da OAB e o Provimento 205/2021 sobre publicidade.

Voce pode lembrar disso tudo a cada mensagem. Ou pode delegar o copywriting pro Legalized e revisar so a aprovacao final.

---

## Instalacao

### Via Claude Cowork (recomendado)

1. Abra o **Cowork** (Mac/Windows) ou Claude Desktop com suporte a plugins
2. Clique em **Settings → Plugins → Pessoal → "+" Uploads locais → Adicionar marketplace**
3. Cole a URL do marketplace publico:

```
https://github.com/<owner>/legalized-jur-marketplace
```

4. Clique em **Sincronizar** e depois **Instalar** o plugin `legalized-jur`
5. Abra o Claude e rode `/legalized` pra configurar seu perfil (wizard de ~3 min)

### Via Claude Code (CLI)

```bash
claude plugin marketplace add <owner>/legalized-jur-marketplace
claude plugin install legalized-jur@legalized-jur-marketplace
```

Depois rode `/legalized` no Claude pra configurar perfil.

---

## Uso rapido

### Primeira vez

```
/legalized
```

Wizard interativo. Pergunta seu nome, OAB, escritorio, areas de atuacao, tom (3 presets) e cidade. Grava em `${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md`. Voce pode editar a qualquer momento.

### Dia a dia

**Redigir mensagem nova:**
```
/legalized-redigir
Destinatario: Carolina (cliente, processo trabalhista)
Objetivo: avisar que a audiencia de instrucao foi remarcada pra 24/05 e que precisamos conversar antes
Canal: WhatsApp
```

**Traduzir juridiques pro cliente:**
```
/legalized-traduzir
Texto: "Indefiro o pedido de tutela de urgencia por ausencia dos requisitos do art. 300 do CPC, em especial a probabilidade do direito alegado..."
Cliente: Fernando (leigo, comprou imovel com vicios)
```

**Revisar rascunho seu:**
```
/legalized-revisar
[cola o texto que voce escreveu]
```

**Editar perfil:**
```
/legalized-perfil
```

---

## O que torna o Legalized diferente de "pedir pro Claude escrever"

1. **Persona unica e estavel** — voce configura uma vez, todas as mensagens saem coerentes
2. **Checklist OAB inegociavel** — 5 verificacoes automaticas antes de devolver qualquer texto
3. **2 registros adaptativos** — rapido (WhatsApp conversacional) vs estruturado (analise, proposta, cobranca, peticao informal)
4. **17 tipos de mensagem catalogados** — 11 WhatsApp + 6 email — cada um com estrutura testada
5. **Calibracao por destinatario** — o tom muda automaticamente pra cliente, lead, parte contraria, perito, cartorio, grupo
6. **Tradutor pro leigo** — feature exclusiva: pega qualquer texto juridico e devolve em portugues comum sem perder rigor
7. **Bandeiras de risco** — se algo no briefing for sensivel, marca `[ATENCAO]` + sugere mitigacao antes de voce enviar

---

## Stack

- Funciona em qualquer ambiente Claude (Code, Desktop, Cowork)
- Zero dependencias externas
- Configuracao em arquivos `.md` editaveis a qualquer momento
- Compliance baseada em fontes publicas (Lei 8.906/94, Codigo de Etica OAB 2015, Provimento 205/2021, LGPD)

---

## Estrutura do plugin

```
legalized-jur/
├── .claude-plugin/plugin.json    ← manifest (name/version/description/author)
├── CLAUDE.md                      ← comportamento completo (raiz, fora de skills/)
├── README.md                      ← este arquivo
├── LICENSE                        ← MIT
├── skills/legalized-jur/
│   └── SKILL.md                   ← APENAS SKILL.md (regra Cowork)
├── agents/legalized-jur.md        ← subagente invocavel via Task tool
├── commands/                      ← 5 slash commands
│   ├── legalized.md               ← /legalized (onboarding)
│   ├── legalized-redigir.md
│   ├── legalized-traduzir.md
│   ├── legalized-revisar.md
│   └── legalized-perfil.md
├── context/
│   └── compliance/                ← camada universal OAB+LGPD
│       ├── oab-etica.md
│       ├── oab-publicidade.md
│       ├── lgpd-juridica.md
│       └── checklist.md
├── templates/
│   ├── config/                    ← perfil.template.md + tons.md + README
│   ├── whatsapp/                  ← 11 tipos de mensagem
│   ├── email/                     ← 6 tipos
│   └── traducao-cliente/          ← 3 profundidades
└── docs/                          ← manual, exemplos, faq
```

---

## Licenca

Este repositorio adota licenca MIT para viabilizar a distribuicao via marketplace publico GitHub e instalacao automatica pelo Cowork. O uso comercial e regido pela licenca de aquisicao adquirida pelo COMPRADOR junto ao fornecedor (entregue dentro do pacote pos-compra). Ver `LICENSE` para os termos MIT do repositorio.

---

## Suporte e atualizacoes

Versao atual: **1.0.0**

Roadmap publico:
- v1.1 — Templates de peticao informal (notificacao extrajudicial, contestacao curta, recurso administrativo)
- v1.2 — Integracao opcional com agendas de prazos
- v1.3 — Multi-idioma (PT-BR + ES + EN para clientes estrangeiros)
- v2.0 — Memoria de aprendizado: o Legalized aprende preferencias de tom dos clientes individualmente

---

**Legalized Jur** — voce delega o copywriting, mantem o controle da estrategia.
