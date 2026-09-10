# RA-02 — Roteiro de Atividade
## Planejamento da Sprint 1 do Connexa no Azure Boards

**Disciplina de Engenharia de Software** · Prof. Claudio Nunes
**Modalidade:** em equipe (4 a 5 integrantes) · **Duração:** 1 aula de laboratório + reunião de planejamento da equipe
**Ferramenta:** Azure Boards (processo *Agile*) · **Submissão:** Microsoft Teams

---

### Convenções deste documento

| Marcador | Significado |
|---|---|
| `<organizacao-da-disciplina>` | Organização no GitHub definida pelo docente na primeira aula |
| `<turma>` | Identificador da turma, informado pelo docente |
| `NN` | Número da equipe, com dois dígitos |
| `engsoft-<turma>-equipe-NN` | Sugestão de nome para a organização da equipe no Azure DevOps |

> O nome da organização no Azure DevOps é uma convenção sugerida. O nome do projeto é obrigatório e deve ser exatamente `Connexa`.

---

## 1. Cenário

O Product Backlog do Connexa está construído, ordenado e classificado (RA-01). A coordenação de curso quer ver resultado ainda neste semestre e a equipe tem, a partir de agora, ciclos de **duas semanas**.

Esta atividade é a **reunião de planejamento da Sprint 1**: a equipe define uma meta, seleciona do topo do backlog o que consegue concluir dentro da sua capacidade real e decompõe cada história selecionada em tarefas estimadas em horas.

O erro mais caro desta etapa não é escolher a história errada — é comprometer-se com mais trabalho do que a equipe consegue realizar e terminar a sprint com várias histórias pela metade, das quais nenhuma é verificável.

---

## 2. Objetivos de aprendizagem

| Nível (Bloom) | Objetivo |
|---|---|
| Entender | Explicar o que caracteriza uma sprint: duração fixa, meta única, escopo acordado e resultado verificável |
| Aplicar | Configurar iterações, datas e capacidade da equipe no Azure Boards |
| Aplicar | Decompor histórias em tarefas de 2 a 8 horas e registrar `Remaining Work` |
| Analisar | Comparar o plano com a capacidade real e identificar o excesso antes do início da sprint |
| Avaliar | Julgar quais itens sustentam a meta da sprint e quais devem retornar ao backlog |
| Criar | Produzir um plano de sprint executável, com meta, escopo, riscos e Definition of Done |

---

## 3. Pré-requisitos

- [ ] Atividade RA-01 entregue e corrigida
- [ ] Backlog ordenado, com `Story Points` e Tags MoSCoW em todas as histórias
- [ ] Todos os integrantes disponíveis na reunião de planejamento
- [ ] Datas da Sprint 1 alinhadas com o calendário da disciplina

---

## 4. Etapas

### Etapa 0 — Configurar a sprint na ferramenta (15 min)

1. **Project Settings › Boards › Project configuration › Iterations**: abra `Sprint 1` e informe **data de início** e **data de fim** (duas semanas).
2. **Project Settings › Boards › Team configuration › Iterations**: confirme que `Sprint 1` está na lista de iterações da equipe. Sem isso, ela não aparece no menu **Boards › Sprints**.
3. **Boards › Sprints › Capacity**: cadastre cada integrante, informe **horas por dia** e marque os **dias de ausência** já conhecidos (prova, trabalho, viagem).

> **Checkpoint 0** — `Sprint 1` aparece no seletor de sprints com as datas corretas e a aba *Capacity* mostra todos os integrantes.

---

### Etapa 1 — Calcular a capacidade real (20 min, sem ferramenta)

Cada integrante declara, **em voz alta e diante da equipe**, quantas horas por semana consegue dedicar ao projeto. Números otimistas declarados em silêncio são a origem do estouro.

```
Horas declaradas por integrante, por semana ......  6h
Integrantes .....................................   5
Semanas da sprint ...............................   2
                                              ------
Capacidade bruta ................................  60h

( - ) reserva para imprevistos, provas e retrabalho ....  20%
( - ) reuniões da equipe ...............................   4h
                                              ------
Capacidade de planejamento ......................  44h
```

**Regra da primeira sprint:** sem histórico de velocidade, planeje entre **70% e 80%** da capacidade de planejamento e considere sobra um bom resultado. Terminar antes permite puxar o próximo item do backlog; não terminar não permite nada.

> **Checkpoint 1** — a equipe tem um número único de horas de capacidade, com a conta registrada por escrito.

---

### Etapa 2 — Escrever a meta da sprint (15 min, sem ferramenta)

**Escreva a meta antes de escolher qualquer item.** A meta não é a lista dos itens; é o motivo pelo qual eles serão escolhidos.

Molde:

```
Ao final desta sprint, <papel> consegue <resultado observável>.
```

| Metas que não servem | Por quê |
|---|---|
| "Fazer as histórias 12, 15 e 18" | É a lista, não a meta |
| "Adiantar o projeto" | Não permite decidir nada durante a sprint |
| "Terminar o banco de dados" | Não entrega resultado a nenhum usuário |

Exemplo em outro domínio (PedeJá, aplicativo de pedidos de um restaurante): *"Ao final desta sprint, um cliente consegue montar e enviar um pedido simples sem telefonar."*

> **Checkpoint 2** — a meta cabe em uma frase, nomeia um papel e descreve um resultado que alguém de fora da equipe consegue observar.

---

### Etapa 3 — Selecionar os itens (25 min)

1. Em **Boards › Backlogs**, abra **View options › Planning**: uma coluna lateral com as sprints aparece à direita.
2. Percorra o backlog **do topo para baixo** e, para cada história, pergunte: *ela sustenta a meta?*
   - Sim → arraste-a para o cartão da `Sprint 1` (isso grava o `Iteration Path`).
   - Não → mantenha no backlog, mesmo que pareça fácil.
3. Pare quando a soma dos `Story Points` selecionados se aproximar do que a equipe julga caber. Sem histórico, a soma é uma estimativa provisória — a verificação real vem na Etapa 4.
4. Selecione entre **3 e 6 histórias**.

> **Checkpoint 3** — todas as histórias selecionadas sustentam a meta, e nenhuma foi escolhida apenas por ser fácil.

---

### Etapa 4 — Decompor em tarefas e confrontar com a capacidade (45 min)

1. Vá para **Boards › Sprints › Backlog**.
2. Para cada história, use o **+** da própria história para criar as **Tasks** — elas nascem vinculadas e já na sprint correta.
3. Cubra todos os tipos de trabalho: modelagem, implementação, interface, testes, revisão e documentação. Uma história cujas tarefas não incluem verificação não está decomposta.
4. Preencha `Remaining Work` de cada tarefa, em horas.
   - Faixa saudável: **2h a 8h**.
   - Tarefa acima de 8h quase sempre esconde duas tarefas — ou uma dúvida que ninguém resolveu.
5. Abra **Work details** e compare a soma das horas com a capacidade.
   - Se ultrapassar, **devolva ao backlog a história de menor prioridade** e recalcule.
   - Não reduza números para caber: isso falseia o plano em vez de ajustá-lo.
6. Confira o **Taskboard**: todas as histórias com tarefas, nenhuma tarefa no grupo *Unparented*.

> **Checkpoint 4** — nenhuma barra de capacidade ultrapassa o limite e todas as histórias da sprint têm tarefas estimadas.

---

### Etapa 5 — Registrar riscos e o Definition of Done (20 min)

**Riscos.** Liste de três a cinco riscos concretos desta sprint e, para cada um, o que a equipe fará se ocorrer. Exemplos de risco real em projeto de disciplina: prova de outra disciplina na segunda semana; integrante com viagem marcada; incerteza técnica sobre uma biblioteca ainda não usada; dependência de uma decisão de escopo ainda não tomada.

**Definition of Done.** Acorde, por escrito, o que significa "pronto" nesta sprint. Sugestão de ponto de partida — a equipe pode acrescentar, não retirar:

- [ ] Todos os critérios de aceite da história verificados
- [ ] Código revisado por outro integrante
- [ ] Nenhuma tarefa da história em estado `Active`
- [ ] História movida para `Resolved` por quem executou e para `Closed` pelo guardião da qualidade

> **Checkpoint 5** — a equipe consegue responder, sem consultar ninguém de fora, se uma história está pronta ou não.

---

## 5. Entregáveis

### 5.1 No Azure Boards

- `Sprint 1` com datas definidas e selecionada para a equipe
- Capacidade informada para **todos** os integrantes, com dias de ausência marcados
- 3 a 6 histórias com `Iteration Path` na `Sprint 1`
- Todas as histórias da sprint decompostas em Tasks vinculadas
- Tasks com `Remaining Work` entre 2h e 8h
- Soma das horas dentro da capacidade calculada

### 5.2 No repositório da equipe

Arquivo `docs/sprint-1-planejamento.md` no repositório `<organizacao-da-disciplina>/connexa-equipe-NN`:

1. **Meta da sprint**, em uma frase, no molde apresentado
2. **Conta da capacidade**, com as horas declaradas por cada integrante
3. **Justificativa da seleção**: por que cada história escolhida sustenta a meta; e, se alguma história do topo do backlog foi deixada de fora, por quê
4. **Riscos** identificados e a resposta prevista para cada um
5. **Definition of Done** acordado
6. **Registro da reunião**: data, duração e participantes

### 5.3 Submissão no Microsoft Teams

Um único post da equipe, contendo:

- link da `Sprint 1` no Azure Boards;
- captura de tela do **Taskboard** com as tarefas criadas;
- link do arquivo `docs/sprint-1-planejamento.md`;
- nome completo de todos os integrantes.

---


---

## 6. Erros frequentes

| Erro | Consequência | Correção |
|---|---|---|
| Selecionar itens antes de escrever a meta | Sprint com itens desconexos entre si | Escrever a meta primeiro, sempre |
| Planejar sobre a capacidade bruta | Estouro descoberto na segunda semana | Aplicar a reserva de 20% e a regra dos 70–80% |
| Tarefas gigantes ("Implementar o módulo — 30h") | O acompanhamento não se move por dias | Quebrar em tarefas de 2h a 8h |
| Sprint só de "infraestrutura" | Nada verificável ao final | Selecionar ao menos uma fatia vertical completa |
| Reduzir horas para o plano caber | Plano falso; estouro garantido | Devolver a história de menor prioridade ao backlog |
| Escopo novo entrando no meio da sprint | Meta perdida, nada concluído | Item novo vai para o backlog e é reordenado |
| Nenhuma tarefa de teste ou revisão | História chega ao fim sem verificação | Incluir verificação na decomposição de toda história |

---

## 7. Material de apoio

- Apresentação **Azure Boards na prática — do Product Backlog ao planejamento da primeira Sprint** (Parte 6)
- Roteiro **RA-01 — Construção do Product Backlog**
- **Exemplo de referência: backlog do PedeJá** (`Exemplo_Referencia_Backlog_PedeJa.md`), que inclui um plano de sprint completo em outro domínio
- Documentação oficial: *Azure Boards › Sprints, capacity e Taskboard*

---

*Roteiro de atividade — Disciplina de Engenharia de Software — Projeto Connexa.*
