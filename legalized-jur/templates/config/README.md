# config/ — Configuracao do Legalized Jur

Pasta com os arquivos que personalizam a persona Legalized pro advogado que a instalou.

## Arquivos

| Arquivo | Funcao |
|---------|--------|
| `perfil.template.md` | Template em branco, modelo de como `perfil.md` deve ficar |
| `perfil.md` | Perfil real do advogado — **gerado pelo wizard `/legalized` ou editado manualmente** |
| `tons.md` | Documentacao dos 3 tons preset + tom custom (formal-tradicional, moderno-consultivo, amigavel-proximo, custom) |

## Como criar o `perfil.md`

### Opcao 1 — Wizard (recomendado, ~3 min)

```
/legalized
```

Faz 6 perguntas guiadas, mostra um WhatsApp de exemplo aplicando seu tom, e grava o arquivo.

### Opcao 2 — Manual

```bash
cp perfil.template.md perfil.md
${EDITOR:-nano} perfil.md
```

Preencha os placeholders `<...>` e salve.

### Opcao 3 — Misto

Rode o wizard pra gerar o esqueleto, depois edite `perfil.md` manualmente pra ajuste fino dos `tics_linguisticos` e `vocabulario_proprio`.

## Como editar depois

```
/legalized-perfil
```

Mostra o atual, deixa voce trocar so o tom, editar um campo, reconfigurar do zero ou abrir no editor.

## Onde o `perfil.md` vive depois da instalacao

```
${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.md
```

A persona Legalized recarrega automaticamente em toda invocacao — voce nao precisa "reiniciar" nada apos editar.

## Backup

Quando voce reconfigura do zero pelo `/legalized-perfil`, o arquivo antigo e salvo como:

```
${CLAUDE_PLUGIN_ROOT}/templates/config/perfil.backup.YYYYMMDD-HHMM.md
```

Voce pode restaurar manualmente se quiser voltar.
