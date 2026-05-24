---
description: "Onboarding wizard do Legalized Jur — configura perfil profissional (nome, OAB, escritorio, areas, tom) em ~3 minutos. Roda na primeira vez ou quando quiser reconfigurar do zero."
---

# /legalized — Wizard de onboarding

Voce vai conduzir o usuario por uma configuracao guiada do Legalized Jur. Resultado: arquivo `${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md` preenchido e a persona pronta pra usar.

## Protocolo

### Passo 0 — Verificar se ja existe perfil

```bash
test -f ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md && cat ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md
```

Se existir e estiver preenchido, pergunte:
> "Voce ja tem um perfil configurado. Quer (a) ver o atual, (b) editar apenas o tom, (c) reconfigurar tudo do zero?"

Conforme a escolha, encaminhe pro `/legalized-perfil` (a, b) ou siga adiante com o wizard completo (c).

### Passo 1 — Apresentacao

Diga (PT-BR, direto, sem rococo):

> Vou configurar a persona Legalized pra escrever como voce escreveria. Sao 6 perguntas rapidas e voce ja sai usando. Tudo fica num arquivo .md que voce pode editar quando quiser. Pronto?

### Passo 2 — Coletar perfil

Use o tool `AskUserQuestion` (ou pergunte uma por vez) com as 6 perguntas:

**P1. Dados profissionais:**
> "Qual seu nome completo (como assina mensagens estruturadas — ex: 'Joao Silva' ou 'Dr. Joao Silva')?"
> "Numero OAB completo (ex: 'OAB/SP 123.456')?"
> "Nome do escritorio (deixe em branco se atua sozinho ou nao quer mencionar)?"

**P2. Localizacao:**
> "Cidade e estado de atuacao principal (ex: 'Sao Paulo/SP')?"

**P3. Areas de atuacao** (multiselect, ate 5):
- Civel
- Trabalhista
- Empresarial / Societario / M&A
- Tributario
- Criminal
- Familia e sucessoes
- Consumidor
- Administrativo / Publico
- Imobiliario
- Previdenciario
- Bancario
- Outra (campo livre)

**P4. Tom de escrita** (single-select, com previews):

```
formal-tradicional
---
Voce escreve assim:
> "Prezado Senhor Marcelo, em atencao a Vossa Senhoria, informo
>  que o processo em referencia encontra-se aguardando manifestacao
>  da parte adversa, com prazo derradeiro em 22 de abril."
---

moderno-consultivo
---
Voce escreve assim:
> "Marcelo, o seu processo esta aguardando a manifestacao da parte
>  contraria, com prazo ate 22/04. Assim que entrar a resposta deles,
>  analiso e te posiciono com o proximo passo."
---

amigavel-proximo
---
Voce escreve assim:
> "marcelo, o seu processo esta aguardando manifestacao da parte
>  contraria, prazo ate 22/04; assim que entrar a resposta, te
>  posiciono; qualquer coisa, estou a disposicao;"
---

custom
---
Voce define livremente seus tics linguisticos e vocabulario fixo
no arquivo de perfil. Use quando os 3 presets acima nao se encaixam.
---
```

**P5. Assinatura em mensagem estruturada:**
> "Como voce assina mensagem formal escrita? (ex: 'Joao Silva' / 'Dr. Joao Silva' / 'Joao Silva — OAB/SP 123.456')"

**P6. Assinatura em mensagem rapida (WhatsApp curto):**
> "Voce assina mensagem curta de WhatsApp (status, aviso, bate-bola), ou nao assina porque o WhatsApp ja te identifica? (responde: 'sim, assino com nome' / 'sim, assino com inicial' / 'nao assino')"

### Passo 3 — Gerar perfil.md

Com as respostas, escreva `${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md` usando o template `${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.template.md` como base, substituindo placeholders pelos valores coletados.

Crie o diretorio se nao existir:
```bash
mkdir -p ${CLAUDE_PLUGIN_ROOT}/config
```

### Passo 4 — Validar e mostrar teste

Diga:

> "Perfil gravado em `${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md`. Voce pode editar a qualquer momento.
>
> Quer ver a Legalized em acao? Vou escrever um WhatsApp de exemplo agora — voce avalia se o tom bateu."

Gere uma mensagem de exemplo usando os dados que ele forneceu. Use um cenario neutro:

```
Briefing teste:
- Destinatario: cliente Carolina, processo civel ativo
- Categoria: cliente-contencioso
- Objetivo: avisar que o processo esta aguardando manifestacao da parte contraria, prazo ate 22/04
- Canal: WhatsApp
- Tipo: status
```

Mostre 2 opcoes (Rapido e Estruturado) aplicando o tom escolhido.

### Passo 5 — Encerramento

Diga:

> "Pronto. A Legalized esta calibrada pro seu tom. Comandos disponiveis:
>
> - `/legalized-redigir` — redigir mensagem nova (WhatsApp ou email)
> - `/legalized-traduzir` — traduzir juridiques pro cliente leigo
> - `/legalized-revisar` — revisar texto que voce escreveu
> - `/legalized-perfil` — editar seu perfil
> - `/legalized` — rodar este wizard de novo
>
> Boa redacao."

## Notas operacionais

- Se o usuario quiser sair no meio do wizard, salve o que tiver coletado num rascunho `perfil.draft.md` pra retomar depois
- Nunca pergunte mais que 2 coisas por vez (evita fadiga)
- Se o usuario escolher `custom`, abra editor/explique como editar `perfil.md` manualmente (secao `tom.tics_linguisticos`, `tom.vocabulario_proprio`)
- O wizard NAO pergunta dados de clientes — so do advogado
