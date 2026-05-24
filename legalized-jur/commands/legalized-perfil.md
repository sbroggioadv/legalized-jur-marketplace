---
description: "Edita o perfil do Legalized Jur — nome, OAB, escritorio, areas de atuacao, tom de escrita, assinaturas. Mostra o perfil atual e permite atualizar campos pontualmente ou reconfigurar do zero."
---

# /legalized-perfil — Edicao do perfil

Voce vai ajudar o usuario a editar seu perfil do Legalized Jur.

## Protocolo

### Passo 1 — Mostrar perfil atual

```bash
cat ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md 2>/dev/null || echo "PERFIL NAO ENCONTRADO"
```

Se nao existir, diga:
> "Voce ainda nao tem perfil configurado. Rode `/legalized` pra criar do zero (3 minutos)."

Se existir, mostre o conteudo formatado e pergunte:

> "Quer:
> - (a) Trocar so o tom (rapido)
> - (b) Editar um campo especifico (nome, OAB, escritorio, areas, assinatura)
> - (c) Reconfigurar tudo do zero (vai rodar `/legalized`)
> - (d) Abrir o arquivo num editor pra editar a mao"

### Passo 2 — Conforme a escolha

**Se (a) trocar tom:**
- Mostre os 3 presets com previews (igual ao `/legalized` passo P4)
- Atualize so o campo `tom.preset` no perfil
- Se escolheu `custom`, abra editor pra ele preencher `tom.tics_linguisticos` e `tom.vocabulario_proprio`

**Se (b) editar campo especifico:**
- Pergunte qual campo
- Pergunte novo valor
- Atualize so esse campo no perfil
- Mostre o perfil atualizado

**Se (c) reconfigurar do zero:**
- Faca backup do atual: `cp ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.backup.$(date +%Y%m%d-%H%M).md`
- Encaminhe pra `/legalized`

**Se (d) abrir no editor:**
- Avise: "Vou abrir no seu editor padrao. Salve e feche pra eu validar."
- Comando: `${EDITOR:-nano} ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md`
- Apos retorno, valide a sintaxe do arquivo (formato esperado, campos obrigatorios presentes)

### Passo 3 — Validar e confirmar

Apos qualquer edicao:

```bash
cat ${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md
```

Valide:
- Campos obrigatorios presentes: `nome`, `oab`, `cidade`, `estado`, `areas_atuacao`, `tom.preset`, `tom.assinatura_estruturada`, `tom.assinatura_rapida`
- Se `tom.preset == custom`, validar que `tom.tics_linguisticos` ou `tom.vocabulario_proprio` foi preenchido

Se passou, diga:
> "Perfil atualizado. As proximas mensagens da Legalized ja usam o novo tom."

Se faltou algo, aponte e ofereca preenchimento rapido.

## Campos do perfil

| Campo | Obrigatorio | Exemplo |
|-------|-------------|---------|
| `nome` | sim | "Joao Silva" |
| `oab` | sim | "OAB/SP 123.456" |
| `escritorio` | nao | "Silva & Associados" |
| `cidade` | sim | "Sao Paulo" |
| `estado` | sim | "SP" |
| `areas_atuacao` | sim | ["empresarial", "civel", "trabalhista"] |
| `tom.preset` | sim | "moderno-consultivo" |
| `tom.tics_linguisticos` | so se custom | ["encadear com ; em vez de ."] |
| `tom.vocabulario_proprio` | nao | {"seu processo": "o caso"} |
| `tom.assinatura_estruturada` | sim | "Joao Silva" ou "Dr. Joao Silva" |
| `tom.assinatura_rapida` | sim | "nao assino" / "assino com inicial" / "assino com nome" |
