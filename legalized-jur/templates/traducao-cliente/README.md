# Templates Traducao pra Cliente Leigo

Estruturas padrao do modo `traducao-leigo` da Legalized — pega texto juridico (peticao, decisao, ementa, sentenca, despacho, clausula contratual) e devolve em portugues comum.

> O comportamento completo do modo esta em `${CLAUDE_PLUGIN_ROOT}/CLAUDE.md` secao 8.
> Esta pasta serve como referencia visual de formatos.

## Estruturas por profundidade

| Profundidade | Arquivo | Quando usar |
|--------------|---------|-------------|
| Curta (WhatsApp) | `t1-curta.md` | Cliente pediu rapido, mensagem instantanea |
| Media (email) | `t2-media.md` | Cliente vai ler com calma, decidir algo |
| Detalhada (documento) | `t3-detalhada.md` | Caso complexo, varias partes, vai imprimir/arquivar |

## Glossario base de traducoes

A Legalized mantem internamente um glossario de termos juridicos comuns -> portugues do dia-a-dia. Lista parcial:

| Juridiques | Portugues comum |
|------------|-----------------|
| tutela de urgencia | decisao rapida do juiz pra proteger algo que pode se perder |
| tutela antecipada | antecipa o resultado antes do fim do processo |
| improcedencia | o juiz negou o pedido |
| procedencia | o juiz aceitou o pedido |
| parcialmente procedente | o juiz aceitou em parte, negou em parte |
| litispendencia | ja existe outro processo igual rodando |
| coisa julgada | a decisao virou definitiva, nao da mais pra mudar |
| transito em julgado | quando a decisao vira definitiva |
| preclusao | o prazo passou e agora nao da mais pra fazer essa coisa |
| revelia | a parte foi notificada e nao respondeu — o processo seguiu mesmo assim |
| contraditorio | direito de cada lado se defender ouvindo o que o outro alegou |
| agravo de instrumento | recurso pra uma decisao no meio do processo (nao pra sentenca) |
| apelacao | recurso pra sentenca final |
| embargos de declaracao | pedido pra esclarecer algo confuso ou contraditorio na decisao |
| sentenca | decisao final do juiz no processo |
| acordao | decisao do tribunal (varios juizes) |
| ementa | resumo da decisao do tribunal |
| despacho | decisao curta do juiz no meio do processo (geralmente so organizando) |
| in casu | neste caso |
| data venia | com o devido respeito |
| ex officio | por iniciativa propria (do juiz) |
| ad cautelam | por cautela / por precaucao |
| pro labore | salario do socio que trabalha na empresa |
| holding | empresa que tem participacao em outras empresas (organiza patrimonio) |
| previdencia privada | aposentadoria contratada com banco/seguradora (alem do INSS) |
| dano moral | indenizacao por sofrimento ou ofensa |
| dano material | indenizacao por prejuizo financeiro concreto |
| dano emergente | o que voce perdeu efetivamente |
| lucro cessante | o que voce deixou de ganhar |
| pena de oficio | penalidade aplicada pelo juiz sem que ninguem precise pedir |
| obrigacao solidaria | varios devedores podem ser cobrados pelo valor total cada um |
| obrigacao subsidiaria | so cobra do segundo se o primeiro nao puder pagar |
| sucumbencia | quem perdeu paga os honorarios do advogado do outro lado |

Quando voce expande este glossario com termos de outras areas, a Legalized incorpora automaticamente na proxima traducao.

## Regras de ouro da traducao Legalized

1. **Nunca elimine a essencia tecnica.** Traduzir e simplificar, nao deturpar. O cliente precisa entender o que aconteceu de verdade.
2. **Identifique o efeito pratico.** "O que muda na minha vida?" e a pergunta que toda traducao deve responder.
3. **Substitua latim integralmente.** Nada em latim chega pro cliente leigo.
4. **Quebre paragrafo longo.** Maximo 3-4 linhas por paragrafo em traducao.
5. **Encerre com proximos passos.** O que voce vai fazer + o que ele precisa fazer + quando.
6. **Marque suposicoes.** Se a Legalized inferiu algo do texto original que nao esta literalmente la, marque com `[interpretacao]`.
