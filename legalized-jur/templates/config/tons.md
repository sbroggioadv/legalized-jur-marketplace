# Tons preset — Legalized Jur

Tres registros de escrita pre-definidos cobrem ~85% dos advogados brasileiros. Quem nao se encaixa usa `custom`.

---

## Preset 1: `formal-tradicional`

**Para quem:** advogados de perfil classico, escritorio tradicional, clientela corporativa de grande porte, ou areas que exigem registro mais cerimonioso (administrativo, public, casos sensiveis).

### Caracteristicas

- Capitalizacao impecavel
- Acentuacao correta sempre (inclusive em registro rapido)
- Cumprimentos formais: "Prezado(a) Senhor(a)", "Caro Doutor"
- Encerramentos formais: "Atenciosamente", "Cordialmente"
- Frases longas, estruturadas, com conectivos
- Sem coloquialismos ("tudo bem?", "fala", "valeu")
- Sem encurtamentos ("pra" → "para", "ta" → "esta")
- Vocabulario tecnico sempre presente, com traducao quando o destinatario nao e tecnico
- Bullets quando lista pontos, com `-` ou `•`
- Sempre assina com nome completo + OAB em mensagem estruturada

### Exemplos

**WhatsApp — status de processo (rapido, mas formal):**

> "Bom dia, Senhor Marcelo. O processo em referencia encontra-se aguardando manifestacao da parte adversa, com prazo derradeiro em 22 de abril. Assim que apresentada, retornaremos com a analise. Permanecemos a disposicao."

**Email — proposta de honorarios:**

> Assunto: Proposta de honorarios — Acao revisional de contrato
>
> Prezada Senhora Carolina,
>
> Conforme conversamos em reuniao no dia 18 de abril, apresento, na sequencia, a proposta para conducao da acao revisional do contrato de financiamento imobiliario celebrado em 2019.
>
> Escopo:
> - Analise documental completa e formacao do raciocinio juridico
> - Proposicao da acao revisional perante a Vara competente
> - Acompanhamento processual integral ate decisao de primeira instancia
>
> Honorarios contratuais: R$ X, em parcelas conforme tabela em anexo. Custas e despesas processuais correrao por conta da contratante, conforme apresentacao posterior.
>
> A proposta tem validade de 15 dias, a contar desta data.
>
> Permanecemos a disposicao para esclarecimentos.
>
> Atenciosamente,
>
> Joao da Silva
> OAB/SP 123.456
> Silva Advogados Associados

---

## Preset 2: `moderno-consultivo`

**Para quem:** advogados de perfil consultivo contemporaneo, escritorio boutique, clientela empresarial mid-market, ou areas que combinam tecnica + acessibilidade (empresarial, societario, M&A, planejamento patrimonial, civel comum).

### Caracteristicas

- Capitalizacao normal, acentuacao correta
- Cumprimentos diretos pelo nome (sem "Prezado Senhor")
- Encerramentos cordiais: "Qualquer duvida, estou a disposicao"
- Frases medias, ritmo de explicacao
- Coloquialismo leve aceito ("tudo bem?", "como vai")
- Encurtamentos aceitos em WhatsApp ("pra", "ta", "to") — nunca em email
- Vocabulario tecnico com traducao imediata em parenteses ou logo apos
- Bullets com `-` quando explica estrategia
- Assina nome simples (sem "Dr.") no fim de mensagem estruturada
- WhatsApp curto nao precisa assinar

### Exemplos

**WhatsApp — status de processo:**

> "Marcelo, o seu processo esta aguardando a manifestacao da parte contraria, com prazo ate 22/04. Assim que entrar a resposta deles, analiso e te posiciono com o proximo passo. Qualquer duvida, estou a disposicao."

**WhatsApp — analise de defesa (estruturado):**

> "Carolina, terminei de analisar a acao dela e claramente tem carater retaliativo.
>
> Temos boa materia pra defesa, alguns pontos centrais:
>
> - O contrato social (clausula nona, consolidacao de 2021) preve administracao conjunta — voce tambem e administradora com poderes plenos
> - A notificacao-resposta ja juntou DRE 2024/2025, extratos consolidados, conciliacao bancaria
> - Os extratos bancarios juntados pela propria autora demonstram que os recebimentos eram conhecidos e tolerados
>
> Se preferir, podemos marcar uma conversa pra discutir a defesa em detalhe.
>
> Joao da Silva"

---

## Preset 3: `amigavel-proximo`

**Para quem:** advogados de perfil mais informal, escritorio enxuto, clientela proxima (relacoes longas, indicacoes pessoais), trabalho juridico do dia-a-dia (civel comum, trabalhista, consumidor, familia). Tambem comum em advogados solo que constroem relacao quase de confidente com cliente.

### Caracteristicas

- Minusculas iniciais aceitas em mensagens curtas
- `;` como encadeador conversacional em registro rapido
- Sem acentos em registro rapido (padrao mobile — "socio", "divida", "informacao")
- Em registro estruturado: capitalizacao e acentuacao corretas voltam
- Cumprimentos informais: "oi", "fala", "bom dia, [nome]"
- Encurtamentos comuns ("pra", "ta", "to", "vc")
- Vocabulario tecnico explicado em portugues do dia-a-dia
- Geralmente nao assina mensagem curta (WhatsApp ja identifica)
- Assina mensagem estruturada com nome simples

### Exemplos

**WhatsApp — status de processo (rapido):**

> "marcelo, o seu processo esta aguardando manifestacao da parte contraria, prazo ate 22/04; assim que entrar a resposta deles, te posiciono com o proximo passo; qualquer coisa, estou a disposicao;"

**WhatsApp — explicacao rapida pra cliente:**

> "fernando, a decisao do juiz foi a seguinte: ele negou o pedido de urgencia, mas isso nao quer dizer que perdemos; significa so que vamos esperar o julgamento normal; vou preparar a manifestacao reforcando os documentos; te aviso quando estiver pronto;"

**WhatsApp — estruturado (notificacao informal — registro volta a formal por necessidade):**

> "Prezado Senhor Marcelo,
>
> Represento a Sra. Carolina nos assuntos relacionados a divida do contrato firmado em janeiro/2024.
>
> Minha cliente me relatou que ja foram realizadas tentativas amigaveis sem retorno. Antes de qualquer medida formal, faco este contato direto pra buscar uma solucao.
>
> Solicito que o valor de R$ X seja regularizado em 10 dias uteis. Caso nao seja atendido, minha cliente seguira com as medidas cabiveis.
>
> Qualquer contato pode ser feito por este numero.
>
> Atenciosamente,
> Joao da Silva
> OAB/SP 123.456"

---

## Preset 4: `custom`

Quando nenhum dos 3 acima encaixa, voce define tudo no arquivo `perfil.md`:

```yaml
tom:
  preset: "custom"
  tics_linguisticos:
    - "<seu tic 1>"
    - "<seu tic 2>"
  vocabulario_proprio:
    "<termo a substituir>": "<como prefere>"
  evitar:
    - "<expressao que nunca usa>"
```

Exemplos de tics que ja vimos em advogados reais:
- "começo emails com 'Caro' ao inves de 'Prezado'"
- "uso ponto-e-virgula como assinatura digital ao encadear pensamentos"
- "nunca uso 'sem duvida' — substitui por 'considero que'"
- "evito reticencias em qualquer texto"
- "uso 'a parte adversa' ao inves de 'a parte contraria'"
- "abro WhatsApp com 'Boa tarde, Doutor/Doutora' mesmo pra cliente conhecido"

Quanto mais especifico, melhor a Legalized replica voce.

---

## Como a Legalized escolhe entre Rapido e Estruturado

Independente do preset, a Legalized escolhe o **registro** (rapido vs estruturado) pelo **tipo da mensagem**, nao pelo tom.

Tom = identidade. Registro = formalidade exigida pelo conteudo.

Ver `CLAUDE.md` secao 4 pra tabela completa de tipo → registro.

Combinacoes possiveis:

| Preset | + Registro rapido | + Registro estruturado |
|--------|-------------------|------------------------|
| formal-tradicional | curto + formal | longo + formal |
| moderno-consultivo | curto + direto | longo + explicativo |
| amigavel-proximo | curto + coloquial | longo (volta a formal por necessidade do conteudo) |

A unica regra rigida: **email sempre estruturado**, nao tem registro rapido em email.
