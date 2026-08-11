# Legalized Jur — Marketplace

> ## ⚖️ Este repositório NÃO é software livre
>
> O código fica visível para viabilizar a instalação no Claude/Cowork — não porque seja gratuito.
>
> **LEGALIZED JUR — R$ 48,00, pagamento único** (sem assinatura, sem recorrência)
> 👉 **[Adquirir a licença](https://pay.kirvano.com/cba7e99b-4d39-453d-9655-ad7cd88a6020)**
>
> **Ao forkar ou clonar este repositório você adere à [licença de uso](LICENSE)**, devendo efetuar o
> pagamento no link acima e enviar o comprovante para **luis@sbroggio.com.br**.
>
> Os forks são públicos no GitHub e são registrados pelo titular (data, conta e repositório).
>
> **Já comprou?** Nada a fazer — sua licença cobre o uso e o fork para instalação. Este aviso vale de
> 11/08/2026 em diante, para quem chega ao repositório sem ter adquirido.


> ## ⚖️ Este repositório NÃO é software livre
>
> O código fica visível para viabilizar a instalação no Claude/Cowork — não porque seja gratuito.
>
> **LEGALIZED JUR — R$ 48,00, pagamento único** (sem assinatura, sem recorrência)
> 👉 **[Adquirir a licença](https://pay.kirvano.com/cba7e99b-4d39-453d-9655-ad7cd88a6020)**
>
> **Ao forkar ou clonar este repositório você adere à [licença de uso](LICENSE)**, devendo efetuar o
> pagamento no link acima e enviar o comprovante para **luis@sbroggio.com.br**.
>
> Os forks são públicos no GitHub e são registrados pelo titular (data, conta e repositório).
>
> **Já comprou?** Nada a fazer — sua licença cobre o uso e o fork para instalação. Este aviso vale de
> 11/08/2026 em diante, para quem chega ao repositório sem ter adquirido.


Marketplace oficial do plugin **Legalized Jur** para Claude Code, Claude Desktop e Cowork.

---

## O que e o Legalized Jur

**Copywriter juridico de alta performance** para advogados brasileiros. Voce instala em segundos, configura seu perfil profissional uma unica vez (nome, OAB, escritorio, tom de escrita), e passa a ter:

- Redator de **WhatsApp** e **email** que escreve no seu tom
- **Tradutor de juridiques** pro cliente leigo (decisao, ementa, peticao → portugues comum)
- **Revisor de rascunho** com checklist OAB+LGPD embutido
- 17 tipos de mensagem catalogados (11 WhatsApp + 6 email)
- Calibracao automatica de tom por categoria de destinatario (cliente, lead, parte contraria, perito, cartorio, grupo)
- Camada de compliance baseada em Lei 8.906/94, Codigo de Etica OAB 2015, Provimento 205/2021 e LGPD

---

## Instalacao via Claude Cowork (recomendado)

1. Abra o **Cowork**
2. Settings → Plugins → aba **Pessoal**
3. Clique em **"+"** → **Uploads locais** → **Adicionar marketplace**
4. Cole a URL deste repositorio:

```
https://github.com/sbroggioadv/legalized-jur-marketplace
```

5. Clique em **Sincronizar**
6. Encontre o plugin `legalized-jur` na lista e clique em **Instalar**
7. No Claude, rode `/legalized` pra configurar seu perfil (wizard de ~3 min)

---

## Instalacao via Claude Code (CLI)

```bash
claude plugin marketplace add sbroggioadv/legalized-jur-marketplace
claude plugin install legalized-jur@legalized-jur-marketplace
```

Depois rode `/legalized` pra configurar perfil.

---

## Comandos disponiveis

| Comando | Funcao |
|---------|--------|
| `/legalized` | Onboarding wizard — configura perfil profissional em ~3 min |
| `/legalized-redigir` | Redacao de mensagem nova (WhatsApp ou email) |
| `/legalized-traduzir` | Traducao de texto juridico pro cliente leigo |
| `/legalized-revisar` | Revisao de rascunho com checklist OAB+LGPD |
| `/legalized-perfil` | Edicao do perfil profissional |

---

## Tons de escrita

Tres presets cobrem ~85% dos advogados; quem nao se encaixa usa `custom`:

| Preset | Para quem |
|--------|-----------|
| `formal-tradicional` | Escritorio tradicional, clientela corporativa |
| `moderno-consultivo` | Escritorio boutique, clientela mid-market |
| `amigavel-proximo` | Advogado solo, clientela proxima |
| `custom` | Voce define seus proprios tics linguisticos e vocabulario |

---

## Compliance

Toda mensagem produzida passa por 5 verificacoes automaticas:

1. **Promessa de resultado** — vedada (Cod. Etica OAB art. 2°, par.un, VIII; Prov. 205/2021 art. 4°, II)
2. **Dados sensiveis vs destinatario** — LGPD art. 5°, II; art. 7°
3. **Captacao indevida** — Estatuto Advocacia art. 34, IV; Cod. Etica art. 5°
4. **Publicidade abusiva** — Prov. 205/2021 CFOAB
5. **Alinhamento tom × categoria de destinatario**

Bandeiras `[ATENCAO]`, `[SUGESTAO]` e `[SUPOS]` sinalizam riscos mitigados ou suposicoes feitas.

---

## Licenca

Uso licenciado mediante aquisição — ver [`LICENSE`](./LICENSE). As cópias obtidas até 11/08/2026 permanecem sob MIT; a partir dessa data o código é proprietário. O uso comercial é regido pela licença de aquisição entregue no pacote pós-compra.

---

## Suporte

Versao atual: **0.1.0**

Documentacao completa do plugin em `legalized-jur/README.md` apos instalacao.
