*Documento vivo — atualizado ao longo do refinamento do backlog do Connexa.*
# Backlog Inicial — Projeto Connexa

Documento de acompanhamento da RA-01 (Construção do Product Backlog).
Equipe: Equipe 10 · Disciplina de Engenharia de Software.

O Product Backlog completo, ordenado e classificado está no Azure Boards. Este
documento registra as decisões por trás dele: por que a ordem é essa, o que a
equipe resolveu dos pontos deixados em aberto pelo briefing, e como as sessões
de refinamento aconteceram.

---

## 1. Justificativa da ordem dos cinco primeiros itens

A ordem do backlog segue uma ideia simples: o Connexa só entrega valor quando um
estudante consegue, de ponta a ponta, dizer quando pode estudar, achar um grupo
compatível e entrar nele (ou criar um). Toda a parte de visão institucional
(adesão por curso, evolução no semestre) só faz sentido depois que existem grupos
para medir — por isso ela ficou no fim. Os cinco primeiros itens são exatamente
esse caminho de entrada do estudante.

**1º — Declarar disponibilidade de horários e disciplinas de interesse**
É a base de tudo: sem a disponibilidade declarada, não há como cruzar horários nem
sugerir nada. O gargalo que a monitoria descreve é justamente esse cruzamento
feito na mão — montar um grupo de cinco pessoas com horário compatível leva
"uns três dias de conversa". Colocar essa informação no sistema, declarada pelo
próprio estudante, é o que elimina esse trabalho manual (objetivo declarado:
eficiência da monitoria). Corresponde ao território **Perfil e disponibilidade**,
o primeiro do escopo.

**2º — Visualizar e buscar grupos de estudo ativos por disciplina**
Vem direto da fala do estudante ingressante: ele só soube que existiam grupos
quase no fim do semestre, e diz que "se tivesse visto uma lista de grupos da
minha disciplina, com o horário, teria entrado no primeiro dia". O que trava não
é falta de vontade, é não saber por onde começar. Como o ingressante é o público
com maior risco de evasão e é alvo prioritário do objetivo de adesão, dar
visibilidade da oferta é o segundo passo mais importante.

**3º — Filtrar grupos por compatibilidade de horários**
O estudante trabalhador deixa claro que compatibilidade de horário é condição, não
preferência: ele já entrou num grupo que se reunia num horário impossível e
acabou saindo. A informação precisa estar visível *antes* da adesão, senão o
estudante entra e sai, o que prejudica o próprio grupo. Filtrar por
compatibilidade ataca diretamente a permanência (objetivo declarado) e evita a
frustração que ele relata.

**4º — Solicitar entrada em grupo de estudo compatível**
Achar o grupo não basta; é preciso conseguir entrar. Aqui pesa a barreira de
aproximação social do ingressante — ele não se sentia à vontade de "chegar num
pessoal que já estava conversando e pedir para entrar". O sistema formaliza esse
ingresso e tira o peso social da situação. Fecha o fluxo de entrada iniciado nos
itens 2 e 3.

**5º — Criar novo grupo de estudo com limite de integrantes**
Quando não existe grupo compatível, o estudante precisa poder criar o seu. Isso
sustenta a meta central da coordenação — elevar a proporção de estudantes em
grupo ativo — porque amplia a oferta em vez de depender só dos grupos que já
existem. O "limite de integrantes" reflete uma decisão da equipe sobre um dos
pontos em aberto (tamanho do grupo), detalhada na seção 3.

---

## 2. Ordenação e classificação (resumo)

Registro do estado do backlog ao fim do refinamento. A ordem foi definida por
arrasto na página de backlog do Azure Boards; a estimativa usou Story Points
(escala 1-2-3-5-8-13) por comparação com a história de referência; e a prioridade
foi classificada em MoSCoW por Tags.

| # | História | Pontos | MoSCoW |
|---|----------|:------:|:------:|
| 1 | Declarar disponibilidade de horários e disciplinas de interesse | 3 | Must |
| 2 | Visualizar e buscar grupos de estudo ativos por disciplina | 5 | Must |
| 3 | Filtrar grupos por compatibilidade de horários | 5 | Must |
| 4 | Solicitar entrada em grupo de estudo compatível | 3 | Must |
| 5 | Criar novo grupo de estudo com limite de integrantes | 3 | Must |
| 6 | Agendar um novo encontro do grupo | 3 | Must |
| 7 | Registrar presença dos participantes | 3 | Should |
| 8 | Receber sugestões automáticas de grupos de acordo com minha disciplina | 8 | Could |
| 9 | Sugerir subgrupos com horário compatível | 8 | Should |
| 10 | Ser notificado quando houver estudantes compatíveis para formar um novo grupo | 8 | Could |
| 11 | Permitir saída do participante de um grupo de estudo | 2 | Should |
| 12 | Receber lembretes antes dos encontros | 5 | Could |
| 13 | Consultar histórico de encontros realizados | 3 | Could |
| 14 | Visualizar adesão por curso e período | 5 | Must |
| 15 | Acompanhar evolução da adesão no semestre | 3 | Could |
| 16 | Ser avisado quando um grupo parar de se encontrar | 3 | Could |

Distribuição da prioridade: 7 Must, 3 Should, 6 Could. Os Must concentram-se no
núcleo de formar e usar um grupo (itens 1 a 6) mais a visão de adesão que a
coordenação levará à direção (item 14); os incrementos automáticos e de apoio
ficaram como Could.

---

## 3. Decisões sobre os pontos em aberto

O briefing lista pontos que a instituição deliberadamente não decidiu e deixou a
cargo da equipe. Abaixo, o que a equipe decidiu para esta primeira versão do
backlog e o motivo. Os itens ainda não resolvidos estão registrados como
pendência.

**Tamanho do grupo.** O grupo tem um limite de até seis integrantes, seguindo o
intervalo de quatro a seis que a monitoria já usa na prática. É o que sustenta a
história "Criar novo grupo com limite de integrantes".

**Como alguém entra num grupo.** A entrada é por solicitação, aprovada por um
integrante do grupo — não é ingresso direto. Isso protege o grupo de entradas
incompatíveis e está refletido na história "Solicitar entrada em grupo
compatível".

**O que caracteriza um grupo inativo.** Um grupo é considerado inativo quando
deixa de registrar encontros por um período prolongado, indicando que parou de se
reunir. É esse estado que dispara o alerta da história "Ser avisado quando um
grupo parar de se encontrar".

**Como a presença é registrada.** A presença é autodeclarada pelo participante e
confirmada por outro integrante do grupo, o que dá um mínimo de confiabilidade ao
registro sem depender de um único responsável.

**Encontro remoto ou presencial.** O agendamento de encontro permite indicar se
ele é presencial ou remoto, deixando visível o local ou o meio de acesso. Isso
atende especialmente o perfil noturno e trabalhador, para quem o encontro remoto
pode ser a única opção viável.

**O que a coordenação enxerga.** O panorama institucional é agregado, por curso e
por período — não nominal. É exatamente o que a coordenação pede ao querer
enxergar o quadro geral e sustentar decisões com dado.

**Acesso, identificação e LGPD — pendência assumida.** A TI exige cadastro por
e-mail institucional comprovado, credencial sob a guarda do próprio Connexa,
conformidade com a LGPD e acessibilidade (operação por teclado e leitor de tela).
A equipe optou por não incluir cadastro, login, LGPD e acessibilidade neste
primeiro recorte, concentrando o esforço no núcleo de formar e usar um grupo.
Esses temas ficam registrados como pendência para as próximas iterações, junto
com as perguntas de finalidade de dados, retenção, recuperação de senha e
requisitos mínimos de senha que o briefing levanta.

---

## 4. História de referência da estimativa

A história escolhida como referência foi **"Registrar presença dos participantes",
com 3 pontos**.

Motivo: é uma história pequena, de escopo bem delimitado e entendida da mesma
forma por todos — um ponto de partida estável para estimar as demais por
comparação. A partir dela, as histórias claramente maiores (as de compatibilidade
automática, que exigem o sistema cruzar disciplina, disponibilidade e status)
foram para 8, e as ações diretas de escopo semelhante ao da referência ficaram
em 3.

---

## 5. Registro das sessões de refinamento

| Sessão | Data | Duração | Participantes |
|--------|------|---------|---------------|
| Refinamento do backlog (escrita das histórias e critérios, estimativa, ordenação e classificação) | 09/09 | 1h30 | Guilherme Correia, Guilherme Lins |
| Orquestração do BackLog (escrita das histórias, criação de Epics/Features no Azure| 09/09 | 2h30 | Lucas Barros Simon |
| Criação do Epic 4 (Colaboração e Materiais de Estudos) e criação de Features e User Stories, seguindo os requisitos gerais | 09/09 | 1h30 | João del Manto Netto |
| Criação do Epic 3 (Visibilidade Institucional) e criação de Features e User Stories, seguindo os requisitos gerais | 09/09 | 1h30 | Osi Paes Junior |
| Melhorias do Backlog e criação de Features e User Stories, seguindo os requisitos gerais | 09/09 | 1h30 | Rafael Alvarenga Omelczuk  |
---

*Documento vivo — atualizado ao longo do refinamento do backlog do Connexa.*
