# LGPD aplicada a pratica juridica

Sintese da Lei 13.709/18 (Lei Geral de Protecao de Dados) com foco no que afeta diretamente o copywriting do advogado: que dados podem aparecer em que canal, para quem.

> **Fonte:** Lei 13.709/18, texto publico. Resolucoes da ANPD aplicaveis.

---

## Dados pessoais vs dados sensiveis

### Dado pessoal (Art. 5°, I)
> "informacao relacionada a pessoa natural identificada ou identificavel."

Inclui: nome, CPF, RG, endereco, telefone, email, profissao, salario, foto, voz.

### Dado pessoal sensivel (Art. 5°, II)
> "dado pessoal sobre origem racial ou etnica, conviccao religiosa, opiniao politica, filiacao a sindicato ou a organizacao de carater religioso, filosofico ou politico, dado referente a saude ou a vida sexual, dado genetico ou biometrico, quando vinculado a uma pessoa natural."

Inclui: condicao medica do cliente, orientacao sexual, religiao, opiniao politica, sindicalizacao.

**Aplicacao Legalized:** dados sensiveis tem protecao redobrada. Mesmo em comunicacao direta com o titular, a Legalized alerta se o briefing pede pra registrar dado sensivel em texto que pode ser interceptado.

---

## Base legal para tratamento (Art. 7°)

O advogado trata dados de cliente com base em:

- **Inciso V:** "execucao de contrato ou de procedimentos preliminares relacionados a contrato do qual seja parte o titular"
- **Inciso VI:** "exercicio regular de direitos em processo judicial, administrativo ou arbitral"
- **Inciso IX:** "quando necessario para atender aos interesses legitimos do controlador..."

**Aplicacao Legalized:** o advogado tem base legal pra tratar dado do cliente sem consentimento expresso na maioria dos casos — porque ha contrato (V) ou processo (VI). Mas isso nao autoriza compartilhamento livre.

---

## Principios (Art. 6°)

| Principio | Aplicacao Legalized |
|-----------|---------------------|
| **Finalidade** | Dado so circula pelo proposito declarado. Numero de processo num grupo geral nao tem finalidade legitima |
| **Adequacao** | Dado compativel com a finalidade — endereco residencial nao precisa estar em mensagem sobre andamento processual |
| **Necessidade** | Minimizacao — usar o minimo necessario. CPF abreviado em vez de completo se da pra identificar pelo nome |
| **Transparencia** | O cliente sabe que dados dele circulam. Em grupo misto, sinalize antes de mencionar |
| **Seguranca** | Canal adequado — dado bancario nunca em grupo, sempre em canal direto |
| **Prevencao** | Antes de enviar, perguntar: "se isso vazar pra quem nao deveria ler, ha dano?" |

---

## Direitos do titular (Art. 18)

O cliente tem direito a:
- Confirmacao de existencia de tratamento
- Acesso aos dados
- Correcao de dados incompletos
- Anonimizacao, bloqueio ou eliminacao
- Portabilidade
- Eliminacao apos termino do tratamento
- Informacao sobre compartilhamento
- Revogacao do consentimento

**Aplicacao Legalized:** o advogado e controlador dos dados que recebe. Texto que a Legalized produz nao gera novo controle — mas se a Legalized for invocada pra escrever resposta a pedido de eliminacao do cliente, ela trata com seriedade do direito.

---

## Tabela de decisao — que dado vai pra onde

| Dado | Mensagem ao proprio titular | Mensagem a grupo restrito (familia direta) | Grupo misto / nao-titulares | Email marketing publico |
|------|------------------------------|---------------------------------------------|------------------------------|-------------------------|
| Nome completo | OK | OK | Avaliar | Nunca (sem autorizacao) |
| Nome social (apelido) | OK | OK | OK | OK se publico |
| CPF | OK | Mascara | Mascara ou remove | Nunca |
| RG / CNH | OK | Mascara | Remove | Nunca |
| Endereco residencial | OK | Avaliar | Remove | Nunca |
| Telefone pessoal | OK | OK | Remove | Nunca |
| Email pessoal | OK | OK | OK se pertinente | Nunca |
| Conta bancaria / PIX | OK em canal direto, alerta de seguranca | Avaliar canal | Remove + canal direto | Nunca |
| Numero de processo | OK | OK | Abrevia | Nunca |
| Valor de causa | OK | OK | Generaliza | Nunca |
| Honorarios | OK | OK | Generaliza | Nunca |
| Condicao medica | OK com cuidado | Avaliar com cliente | Remove | Nunca |
| Orientacao sexual / religiao / politica | Avaliar necessidade | Remove | Remove | Nunca |
| Foto de documento | OK em canal seguro | Avaliar | Remove | Nunca |

---

## Caso especial — grupo de cliente PJ

Grupo de WhatsApp com:
- Socios da empresa cliente
- Contador da empresa cliente
- Gerente financeiro da empresa cliente
- Advogado (voce)

**Tratamento:** grupo misto. Socios sao titulares de dados PJ (que sao tratados de forma diferente — Lei 13.709 art. 4°, IV exclui parcialmente). Mas dados PJ que **identifiquem pessoas fisicas internamente** (CPF de socio, salario, valor de retirada) continuam sendo dados pessoais.

Regra pratica:
- Pode falar de "valor de honorarios do escritorio" (e dado PJ, da empresa)
- Nao pode falar de "salario do funcionario Fulano" (dado pessoal de PF)
- Pode falar de "pro-labore" generico
- Nao pode citar conta pessoal de socio

---

## Sigilo profissional (Codigo de Etica art. 8°) + LGPD

O sigilo do advogado vai alem da LGPD — ele cobre **tudo** que o cliente compartilha. A LGPD soma protecao tecnica:

- Sigilo profissional protege **conteudo** das comunicacoes
- LGPD protege **dados** que identificam pessoas

Logo, mesmo dado nao-sensivel sob LGPD pode estar protegido por sigilo profissional.

**Aplicacao Legalized:** em duvida, restringe — alinha-se ao padrao mais protetivo entre LGPD e sigilo OAB.

---

## Caso especial — email com anexo

Email com anexo (peticao, decisao, documento de identidade do cliente) e tratamento de dados.

A Legalized, ao redigir email com anexo:
- Sugere assunto que nao revele dado sensivel ("Documentos solicitados — processo [referencia abreviada]")
- Nao repete no corpo dado que ja esta no anexo
- Avisa que o anexo contem dados pessoais ("Em anexo, documento com seus dados — recomendamos arquivar com seguranca")

---

## Quando o advogado pede algo que viola LGPD

Cenario: briefing pede pra mandar "lista de clientes ativos do escritorio" pra um lead que pediu referencias.

Resposta Legalized:
```
[ATENCAO] Briefing solicita compartilhamento de lista de clientes — vedado pela LGPD (art. 7°, I — sem consentimento expresso de cada um) e pelo Codigo de Etica OAB (art. 8° — sigilo).

[SUGESTAO] Reescrevi como apresentacao institucional do escritorio em areas de atuacao, sem nominar clientes. Se o lead quiser referencias especificas, podemos pedir autorizacao a clientes selecionados antes.

Opcao 1
---
"[Nome do lead], obrigado pelo interesse.

O escritorio atua ha [X anos] nas areas de [lista de areas], com experiencia em
casos de [descricao geral de tipos de causa, sem nomear clientes].

Posso te apresentar referencias especificas se desejar — vou pedir autorizacao
formal aos clientes mencionados antes de qualquer envio.

Quando podemos conversar?

[assinatura]"
---
```

---

> **Aviso:** Este documento e referencia operacional consolidada da LGPD aplicada a pratica juridica. Nao substitui leitura direta do texto legal nem orientacao especifica de Encarregado de Dados (DPO). A responsabilidade pela conformidade em cada comunicacao e do advogado.
