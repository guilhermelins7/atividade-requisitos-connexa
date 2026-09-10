# RA-01 — Roteiro de Atividade
## Construção do Product Backlog do Connexa no Azure Boards

**Disciplina de Engenharia de Software** · Prof. Claudio Nunes
**Modalidade:** em equipe (4 a 5 integrantes) · **Duração:** 1 aula de laboratório + trabalho extraclasse
**Ferramenta:** Azure Boards (processo *Agile*) · **Submissão:** Microsoft Teams

---

### Convenções deste documento

| Marcador | Significado |
|---|---|
| `<organizacao-da-disciplina>` | Organização no GitHub definida pelo docente na primeira aula |
| `<turma>` | Identificador da turma, informado pelo docente |
| `NN` | Número da equipe, com dois dígitos (`01`, `02`, … `12`) |
| `engsoft-<turma>-equipe-NN` | Sugestão de nome para a organização da equipe no Azure DevOps |

> O nome da organização no Azure DevOps é uma convenção sugerida. O nome do projeto é obrigatório e deve ser exatamente `Connexa`.

---

## 1. Cenário

A coordenação de curso encomendou o **Connexa**, uma plataforma para formação e acompanhamento de grupos de estudo. O documento de proposta do projeto descreve a situação atual, os cinco envolvidos, os objetivos institucionais, o escopo e — deliberadamente — um conjunto de **pontos em aberto** que a instituição ainda não decidiu.

Sua equipe assume, a partir de agora, a responsabilidade de transformar aquele briefing em um **Product Backlog**: uma lista única, ordenada e viva de tudo que se pretende construir, no formato que a equipe usará durante todo o semestre.

Nenhuma equipe construirá tudo. O recorte é decisão da própria equipe — e a ordem do backlog é onde essa decisão fica visível.

---

## 2. Objetivos de aprendizagem

Ao final desta atividade, a equipe deverá ser capaz de:

| Nível (Bloom) | Objetivo |
|---|---|
| Entender | Explicar a diferença entre Epic, Feature, User Story e Task e justificar o nível de um item |
| Aplicar | Escrever histórias de usuário na forma canônica, com critérios de aceite em Gherkin |
| Aplicar | Operar o Azure Boards para criar, vincular, ordenar e classificar work items |
| Analisar | Identificar erros de nível, histórias horizontais e critérios de aceite não verificáveis |
| Avaliar | Defender a ordem do backlog a partir dos objetivos declarados no briefing |
| Criar | Produzir um backlog coerente que recorta o problema e registra as decisões tomadas |

---

## 3. Pré-requisitos

Antes de iniciar, confirme que a equipe já concluiu os passos da proposta do projeto:

- [ ] Equipe formada, com número `NN` atribuído pelo docente
- [ ] Organização criada no Azure DevOps, preferencialmente com o nome `engsoft-<turma>-equipe-NN`, na região *Brazil South*
- [ ] Projeto criado obrigatoriamente com o nome `Connexa` e com o **processo Agile** (não *Basic*, não *Scrum*)
- [ ] Todos os integrantes convidados com nível de acesso *Basic*
- [ ] Docente adicionado ao projeto
- [ ] Documento de proposta do projeto lido integralmente, em equipe

> Se o processo do projeto não for *Agile*, o nível **Feature** não existirá e a atividade não poderá ser concluída. Nesse caso, recrie o projeto antes de prosseguir.

---

## 4. Etapas

### Etapa 0 — Preparar o ambiente (15 min)

1. Abra **Project Settings › Boards › Team configuration › Backlogs** e marque **Epics**, **Features** e **Stories**.
2. Na aba **Working days**, marque os dias em que a equipe efetivamente trabalha.
3. Volte a **Boards › Backlogs** e confirme que o seletor de nível, no alto da página, oferece os três níveis.

> **Checkpoint 0** — a equipe consegue alternar entre *Epics*, *Features* e *Stories* na página de backlog.

---

### Etapa 1 — Extrair candidatos do briefing (40 min, sem ferramenta)

Trabalhe em papel ou em um documento compartilhado. **Não abra o Azure Boards nesta etapa.**

1. Releia as falas dos cinco envolvidos na proposta do projeto. Para cada fala, anote:
   - quem é o papel;
   - o que essa pessoa quer alcançar;
   - o que hoje a impede.
2. Releia os objetivos declarados pela instituição e os territórios dentro do escopo.
3. Liste candidatos a **Epic**: de dois a quatro resultados amplos, expressos como mudança percebida por alguém — não como módulo do sistema.
4. Para cada Epic, liste candidatos a **Feature**: blocos de funcionalidade que fariam sentido anunciar a quem usa.
5. Para cada Feature, liste candidatos a **User Story**.

**Teste obrigatório de nível.** Para cada item, complete a frase: *"ao final deste item, ___ consegue ___"*.
- Se a lacuna do sujeito for a própria equipe, o item é **Task** — deixe-o de lado por enquanto.
- Se a frase não fecha, o item ainda é grande demais — é Feature ou Epic.

> **Checkpoint 1** — a equipe tem, no papel, de 2 a 4 Epics, de 4 a 8 Features e de 12 a 18 histórias candidatas, e consegue dizer em voz alta de qual trecho do briefing cada Epic nasceu.

---

### Etapa 2 — Escrever as histórias (50 min)

Para cada história candidata, escreva:

**Título** — curto e acionável, sem o "Como…, quero…". Exemplo: *Declarar horários de disponibilidade*.

**Descrição** — a forma canônica completa:

```
Como <papel específico>,
quero <capacidade, não solução de tela>,
para <benefício verificável>.
```

**Critérios de aceite** — em Gherkin, de três a seis cenários, obrigatoriamente incluindo ao menos um caminho de exceção:

```gherkin
Cenário: <nome do cenário>
  Dado que <estado inicial, com valores concretos>
    E que <condição adicional>
  Quando <ação de quem usa>
  Então <resultado observável>
    E <efeito adicional observável>
```

**Regras de escrita cobradas na correção:**

- o papel é específico (`estudante ingressante`, `monitor`), nunca "o usuário";
- nenhum critério menciona tabela, classe, endpoint ou tecnologia;
- valores são concretos (`R$ 40,00`, `três integrantes`), nunca "um valor qualquer";
- cada história passa no teste **INVEST** — em especial **S** (cabe em uma sprint) e **T** (é testável).

> **Checkpoint 2** — troque as histórias com outra equipe e peça que ela aponte, em cinco minutos, qualquer critério de aceite sobre o qual duas pessoas possam discordar. Corrija os apontados.

---

### Etapa 3 — Registrar no Azure Boards (40 min)

Sempre **de cima para baixo**:

1. Em **Boards › Backlogs**, selecione o nível **Epics** e crie os Epics com *New Work Item*. Preencha `Title` e `Description`.
2. Expanda cada Epic e use o sinal **+** à esquerda para criar as **Features** filhas — o vínculo nasce pronto.
3. Expanda cada Feature e use o **+** para criar as **User Stories**.
4. Abra cada história e preencha `Description` e `Acceptance Criteria`. Salve com *Save & Close*.
5. Se alguma história ficou órfã, use **View options › Mapping** e arraste-a sobre a Feature correta.

> Item criado pelo botão geral, sem passar pelo pai, nasce **sem vínculo** e desaparece da árvore quando o nível exibido muda.

**Divisão do trabalho:** todos os integrantes precisam criar ou editar itens. O histórico de cada work item é consultado na correção.

> **Checkpoint 3** — ao selecionar o nível *Features*, toda história aparece sob alguma Feature; não há itens no grupo *Unparented*.

---

### Etapa 4 — Estimar, ordenar e classificar (40 min)

1. **Escolher a história de referência.** Selecione uma história pequena e bem compreendida por todos e atribua a ela **3 Story Points**. Registre qual foi.
2. **Estimar por comparação** (Planning Poker): leitura em voz alta → voto simultâneo em silêncio → revelação → discussão dos extremos → uma reestimativa → registro. Escala: `1, 2, 3, 5, 8, 13`.
   - História estimada em **13 ou mais** deve ser quebrada antes de seguir (por passo do fluxo, por perfil, por regra de negócio, por variação de dado ou por caminho feliz × exceções).
3. **Ordenar por arrasto** na página de backlog, até que a sequência responda: *se a equipe só conseguir fazer três coisas, quais são?* Não existe empate.
4. **Classificar em MoSCoW** com Tags, usando exatamente estas grafias: `Must`, `Should`, `Could`, `Wont`.
   - Regra prática: os itens `Must` não devem ultrapassar 60% do esforço previsto para a primeira sprint.
   - Aplique em lote: selecione várias histórias com `Ctrl`, botão direito → *Edit*.
5. **Exibir as colunas de conferência** em *Column Options*: `Story Points`, `Tags`, `State`.

> **Checkpoint 4** — a tela do backlog mostra, sem rolagem lateral, título, pontos e tag de cada história.

---

### Etapa 5 — Verificar a própria entrega (15 min)

Em **Boards › Queries**, crie e execute quatro consultas sobre `Work Item Type = User Story`:

| Consulta | Filtro | Resultado exigido |
|---|---|---|
| 1 | `Story Points` está vazio | nenhuma linha |
| 2 | `Acceptance Criteria` está vazio | nenhuma linha |
| 3 | `Description` está vazio | nenhuma linha |
| 4 | `Tags` está vazio | nenhuma linha |

Se qualquer consulta retornar linhas, a entrega está incompleta — corrija antes de submeter.

> **Checkpoint 5** — quatro consultas, quatro resultados vazios.

---

## 5. Entregáveis

### 5.1 No Azure Boards

- 2 a 4 **Epics**, com `Description` citando a meta institucional e o ator beneficiado
- 4 a 8 **Features**, com `Description` declarando o impacto esperado
- 12 a 18 **User Stories**, todas filhas de alguma Feature
- 100% das histórias com `Acceptance Criteria` em Gherkin, incluindo caminho de exceção
- 100% das histórias com `Story Points` e Tag MoSCoW
- Backlog **ordenado**, sem empates

### 5.2 No repositório da equipe

Arquivo `docs/backlog-inicial.md` no repositório `<organizacao-da-disciplina>/connexa-equipe-NN`, contendo:

1. **Justificativa da ordem** dos cinco primeiros itens do backlog, cada uma referenciando um trecho do briefing (fala de envolvido, objetivo declarado ou restrição).
2. **Decisões sobre pontos em aberto**: para cada ponto em aberto do briefing que a equipe precisou resolver, registre a decisão tomada e o motivo. Ponto em aberto não resolvido também deve ser listado, como pendência.
3. **História de referência** usada na estimativa, com o motivo da escolha.
4. **Registro das sessões**: data, duração e participantes de cada sessão de refinamento.

### 5.3 Submissão no Microsoft Teams

Um único post da equipe, contendo:

- link do projeto no Azure Boards (com o docente já adicionado);

---



## 6. Erros frequentes

| Erro | Como se manifesta | Correção |
|---|---|---|
| Criar tudo como User Story | Nada aparece nos níveis Epics e Features | Habilitar os níveis e reparentar pelo painel *Mapping* |
| História horizontal | "Criar o banco de dados", "Montar a API" | Reescrever como fatia vertical; o trabalho técnico vira Task na Atividade 2 |
| Critério que testa implementação | "Então um registro é inserido na tabela" | Nomear o efeito visível para quem usa |
| Só caminho feliz | Todos os cenários com dados válidos | Acrescentar recusa, limite e dado ausente |
| Tudo `Must` | 100% das tags iguais | Reordenar e reclassificar aceitando que algo fica para depois |
| Copiar o exemplo da aula | Backlog idêntico ao de outra equipe | O recorte precisa ser da equipe e defensável a partir do briefing |
| Um integrante faz tudo | Histórico com um único autor | Distribuir a criação; a participação é avaliada |

---

## 7. Material de apoio

- Apresentação **Azure Boards na prática — do Product Backlog ao planejamento da primeira Sprint** (Partes 1 a 5)
- Documento **Connexa — Proposta do Projeto** (briefing do cliente)
- **Exemplo de referência: backlog do PedeJá** (`Exemplo_Referencia_Backlog_PedeJa.md`) — domínio distinto, para consulta de forma e nível
- Documentação oficial: *Azure Boards › Backlogs, portfolios, and Agile project management*

---

*Roteiro de atividade — Disciplina de Engenharia de Software — Projeto Connexa.*
