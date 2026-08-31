# Guia de Identificação — Epics, Features e User Stories Candidatas
## Regras do Professor (RA-01 + Apresentação Azure Boards + Briefing Connexa)

> Como extrair os 3 níveis sem abrir o Azure Boards, seguindo exatamente o que será cobrado na correção.

---

### 0. Princípios que não mudam

- **Epic, Feature, Story e Task são quatro horizontes** `Azure_Boards_Backlog_e_Sprint1.md:247-273`: Epic = meses, Feature = semanas, Story = dias, Task = horas. O nível é pelo **tamanho do resultado, não dificuldade técnica** `Azure_Boards_Backlog_e_Sprint1.md:249`.
- **Processo Agile obrigatório** — sem ele o nível Feature não existe `RA-01_Roteiro_Product_Backlog.md:56`, `Connexa_Proposta_do_Projeto.md:732`.
- **Etapa 1 é sem ferramenta** `RA-01_Roteiro_Product_Backlog.md:75`: papel ou doc compartilhado. Não abra Boards antes de listar candidatos.
- **Checkpoint 1** `RA-01_Roteiro_Product_Backlog.md:90`: ao fim, 2-4 Epics, 4-8 Features, 12-18 Stories, e a equipe diz em voz alta de qual trecho do briefing cada Epic nasceu.

---

### 1. Antes de classificar: leia o briefing em duas camadas

**Camada A — Falas dos 5 envolvidos** `Connexa_Proposta_do_Projeto.md:190-289`, `RA-01_Roteiro_Product_Backlog.md:77`:

| Envolvido | Onde está | O que anotar (1 linha por fala) |
|---|---|---|
| Coordenação | `Connexa_Proposta_do_Projeto.md:194` | O que quer alcançar / o que hoje impede (ex: visibilidade por curso/período) |
| Monitoria | `Connexa_Proposta_do_Projeto.md:212` | Idem (ex: cruzamento manual consome bolsa) |
| Ingressante | `Connexa_Proposta_do_Projeto.md:228` | Barreira de descoberta/aproximação |
| Trabalhador | `Connexa_Proposta_do_Projeto.md:243` | Horário como condição, não preferência |
| TI | `Connexa_Proposta_do_Projeto.md:263` | Restrições AUTH/LGPD/WCAG/DISP |

Anote literalmente: `papel | quer | impede`. Isso vira o `papel` e o `para <benefício>` da Story depois.

**Camada B — Objetivos e territórios** `RA-01_Roteiro_Product_Backlog.md:82`:

- Visão `Connexa_Proposta_do_Projeto.md:313`: “aproxima estudantes compatíveis e dá à instituição visibilidade sobre grupos ativos”
- Objetivos `Connexa_Proposta_do_Projeto.md:339-361`: ADESÃO (20%→45%), PERMANÊNCIA (reduzir evasão), EFICIÊNCIA DA MONITORIA (reduzir agendamento), VISIBILIDADE (saber quantos/ativos por curso/período)
- Territórios dentro do escopo `Connexa_Proposta_do_Projeto.md:370-405`: PERF (perfil/disponibilidade), FORM (formação), ENCO (encontros), ACOM (acompanhamento), PAIN (visão institucional), MATE (materiais)
- Fora do escopo `Connexa_Proposta_do_Projeto.md:413-445`: notas, mensageria, vídeo próprio, conteúdo, cobrança — não entram
- Pontos em aberto `Connexa_Proposta_do_Projeto.md:539-576`: ENTRA, TAM, PRES, INAT, REM, VISI — cada um vira decisão registrada, não suposição

---

### 2. Epic candidata

**Definição** `Azure_Boards_Backlog_e_Sprint1.md:251`, `Connexa_Proposta_do_Projeto.md:749`:

- Objetivo amplo, meses de trabalho, reúne várias Features em torno do mesmo resultado de negócio. 2 a 4 por projeto `Azure_Boards_Backlog_e_Sprint1.md:976`, `RA-01_Roteiro_Product_Backlog.md:184`.
- **De onde vem:** dos **objetivos declarados pela instituição** `Azure_Boards_Backlog_e_Sprint1.md:360`. Não invente.
- **Título:** mudança percebida por alguém (`Azure_Boards_Backlog_e_Sprint1.md:976`: “nomeia um resultado, não um módulo”). Errado: `Epic — Tela de login` `Azure_Boards_Backlog_e_Sprint1.md:378`.
- **Description (obrigatório):** cita a **meta institucional e o ator beneficiado** `Azure_Boards_Backlog_e_Sprint1.md:1012`.

**Teste de nível** `RA-01_Roteiro_Product_Backlog.md:86`, `Azure_Boards_Backlog_e_Sprint1.md:394`:

> Complete: “ao final deste item, ___ consegue ___”
> - Se ___ = própria equipe → é **Task**, descarte por enquanto.
> - Se a frase não fecha → ainda é grande demais → é Epic ou Feature.
> - Se `Cabe em uma sprint? Não, atravessa o semestre` → Epic `Azure_Boards_Backlog_e_Sprint1.md:288`.

**Check Epic:**

- [ ] Cabe em semanas/meses, não em dias?
- [ ] Uma pessoa de fora percebe o resultado? (se só quem programa percebe, é Task)
- [ ] Entrega valor sozinha? (se só junto com outros, é Task ou Feature `Azure_Boards_Backlog_e_Sprint1.md:290`)
- [ ] Consegue apontar objetivo `Connexa_Proposta_do_Projeto.md:339-361` que a originou?

**Exemplos**

- **PedeJá** (domínio diferente, forma correta) `Exemplo_Referencia_Backlog_PedeJa.md:25`: `EPIC 1 Cliente monta e envia o pedido sem depender do telefone` — não “Módulo de Pedidos”.
- **Connexa ilustrativo (não copie)** `Azure_Boards_Backlog_e_Sprint1.md:340`: `Estudante encontra um grupo compatível sem depender de conhecer alguém` — coincide com Epic 1 real, mas `Azure_Boards_Backlog_e_Sprint1.md:338` alerta: hierarquia da equipe nasce do briefing, não deste slide.

**Epics reais sugeridas (3, validadas no projeto):** ver `epics-extraidas.md:21-50` — Epic 1 (ADESÃO), Epic 2 (PERMANÊNCIA+EFICIÊNCIA), Epic 3 (VISIBILIDADE).

---

### 3. Feature candidata

**Definição** `Azure_Boards_Backlog_e_Sprint1.md:258`, `Connexa_Proposta_do_Projeto.md:750`:

- Conjunto coerente de histórias, semanas de trabalho. Faz sentido **anunciar para quem usa** (“lançamos a consulta ao cardápio do dia”). Agrupa histórias relacionadas.
- **De onde vem:** dos **territórios dentro do escopo** `Azure_Boards_Backlog_e_Sprint1.md:361`.
- **Description:** declara o **impacto esperado** da funcionalidade `Azure_Boards_Backlog_e_Sprint1.md:1013`.
- **Quantidade:** 4 a 8 no total do backlog `RA-01_Roteiro_Product_Backlog.md:185`.

**Teste de nível:**

- `Cabe em uma sprint? Não, leva semanas` → Feature `Azure_Boards_Backlog_e_Sprint1.md:287`
- Ainda responde “alguém consegue…” mas com escopo de semanas, não dias.

**Erros típicos:**

- Feature que é camada técnica (“API de grupos”, “Banco de perfis”) → é Task, viola fatia vertical `Azure_Boards_Backlog_e_Sprint1.md:541-572`.
- Feature que é tela isolada → provavelmente é Story.

**Mapeamento Connexa (exemplo):**

| Epic | Território → Feature |
|---|---|
| Epic 1 (encontrar grupo) | PERF → *Perfil de disponibilidade*; FORM → *Descoberta de grupos abertos* |
| Epic 2 (sustentar grupo) | ENCO → *Agendamento de encontros*; ACOM → *Registro de presença*; MATE → *Materiais do grupo* |
| Epic 3 (visibilidade) | PAIN → *Painel da coordenação*; PAIN → *Painel da monitoria* |

Todas nascem de `Connexa_Proposta_do_Projeto.md:370-405`.

---

### 4. User Story candidata

**Definição** `Azure_Boards_Backlog_e_Sprint1.md:263`, `Connexa_Proposta_do_Projeto.md:751`:

- Valor entregável **em uma sprint**, dias de trabalho. Algo que **um usuário identificável consegue fazer ao final**. É o nível que vai para a sprint.
- **De onde vem:** das **falas dos envolvidos** `Azure_Boards_Backlog_e_Sprint1.md:362`.

**Forma canônica obrigatória** `RA-01_Roteiro_Product_Backlog.md:100`, `Azure_Boards_Backlog_e_Sprint1.md:441`:

```
Como <papel específico>, quero <capacidade, não solução de tela>, para <benefício verificável>.
```

- Papel: nunca “o usuário”. No Connexa há ≥4 papéis `Azure_Boards_Backlog_e_Sprint1.md:449`: ingressante, estudante trabalhador, monitor, coordenação.
- Ação: capacidade (“ver grupos compatíveis”), não solução de tela (“dropdown com filtro”) `Azure_Boards_Backlog_e_Sprint1.md:453`.
- Benefício: permite priorizar; sem ele o item talvez não devesse existir `Azure_Boards_Backlog_e_Sprint1.md:459`.
- Onde registra: campo **Description** do work item; título é versão curta sem “Como…” `Azure_Boards_Backlog_e_Sprint1.md:463`, `RA-01_Roteiro_Product_Backlog.md:98`.

**Teste INVEST** `Azure_Boards_Backlog_e_Sprint1.md:492-537` — só para topo do backlog:

- I Independent, N Negotiable, V Valuable, E Estimable, S Small (cabe com folga na sprint), T Testable. Falhar em E ou S → quebrar, não reescrever.

**Fatia vertical, não camada** `Azure_Boards_Backlog_e_Sprint1.md:540-572`:

- Errado: Interface / Regras / Banco separados → nada utilizável.
- Certo: cada Story atravessa as 3 camadas (ex: Adicionar item → modelar + endpoint + tela + testes `Exemplo_Referencia_Backlog_PedeJa.md:130`).

**Quebrar Story grande (5 padrões, preservam fatia)** `Azure_Boards_Backlog_e_Sprint1.md:645`:

- PASSO (buscar → entrar → sair), PERFIL (ingressante vs trabalhador), REGRA (ingresso direto vs aprovação), DADO (presencial vs remoto), EXCEÇÃO (caminho feliz vs recusas). Nunca separar frontend/backend `Azure_Boards_Backlog_e_Sprint1.md:679`.

**Exemplos**

- PedeJá `Exemplo_Referencia_Backlog_PedeJa.md:93`: “Como cliente do PedeJá, quero adicionar um item do cardápio ao meu carrinho, para montar meu pedido antes de decidir enviá-lo.”
- Connexa `Azure_Boards_Backlog_e_Sprint1.md:483`: “Como estudante do noturno, quero ver apenas os grupos que se encontram no meu horário livre, para não entrar em um grupo ao qual não conseguirei comparecer.”
- Antes/depois `Azure_Boards_Backlog_e_Sprint1.md:471-483`: “Filtro de horário” (errado, nomeia componente) → forma canônica acima.

**Quantidade e qualidade:** 12-18 Stories, todas filhas de alguma Feature `RA-01_Roteiro_Product_Backlog.md:186`, 100% com critérios Gherkin incluindo exceção, Story Points e Tag MoSCoW `RA-01_Roteiro_Product_Backlog.md:187`.

---

### 5. Critérios de aceite em Gherkin

Obrigatório `RA-01_Roteiro_Product_Backlog.md:108`, `Azure_Boards_Backlog_e_Sprint1.md:578`:

```gherkin
Cenário: <nome>
  Dado que <estado inicial, valores concretos>
    E que <condição adicional>
  Quando <ação de quem usa>
  Então <resultado observável>
    E <efeito adicional observável>
```

Regras cobradas `Azure_Boards_Backlog_e_Sprint1.md:619`:

- 3 a 6 cenários por Story, sempre ≥1 exceção (recusa, limite, dado ausente)
- Valores concretos (`R$ 60,00`, `20 itens`), nunca “um valor qualquer”
- Nenhuma referência a tabela/classe/endpoint
- Vai no campo **Acceptance Criteria**

Padrões recusados `Azure_Boards_Backlog_e_Sprint1.md:634`: vago (“funcionar corretamente”), testa implementação (“registro na tabela”), repete título, só caminho feliz.

Exemplo completo: `Exemplo_Referencia_Backlog_PedeJa.md:97-122` (US-03, 4 cenários) e `Azure_Boards_Backlog_e_Sprint1.md:580-610` (cupom).

---

### 6. Estimar, ordenar e classificar (só após escrever)

- **Referência:** escolha 1 Story pequena e bem entendida → 3 pontos `RA-01_Roteiro_Product_Backlog.md:150`. Escala Fibonacci 1,2,3,5,8,13 `Azure_Boards_Backlog_e_Sprint1.md:812`. ≥13 → quebrar antes `RA-01_Roteiro_Product_Backlog.md:152`.
- **Planning Poker** `Azure_Boards_Backlog_e_Sprint1.md:825-859`: ler em voz alta → voto silencioso → revelar simultâneo → discutir extremos → reestimar 1x.
- **Ordem vs etiqueta** `Azure_Boards_Backlog_e_Sprint1.md:693-729`: ordem = arrasto na página Backlogs (grava Backlog Priority, sem empate) `RA-01_Roteiro_Product_Backlog.md:153`; MoSCoW = Tag `Must, Should, Could, Wont` (sem apóstrofo) `Azure_Boards_Backlog_e_Sprint1.md:761`, até 60% Must `RA-01_Roteiro_Product_Backlog.md:155`.
- **Campos obrigatórios** `Azure_Boards_Backlog_e_Sprint1.md:1010`: Epic `Title·Description`, Feature `Title·Description`, Story `Title·Description·Acceptance Criteria·Story Points·Tag`, Task só na Atividade 2.

---

### 7. Checklist de “pronto para o Boards” (Etapa 1)

- [ ] Consigo dizer, para cada Epic, o trecho do briefing que a originou? `RA-01_Roteiro_Product_Backlog.md:90`
- [ ] 2-4 Epics, 4-8 Features, 12-18 Stories mapeadas no papel?
- [ ] Toda Story passa em “ao final, ___ consegue ___” e não é Task órfã `Azure_Boards_Backlog_e_Sprint1.md:388`?
- [ ] Toda Story em forma canônica com papel específico e benefício verificável?
- [ ] Toda Story tem 3-6 cenários Gherkin com exceção e valores concretos?
- [ ] Toda Story passaria em INVEST (S e T)?
- [ ] Nenhuma divisão é por camada técnica?

Se sim, siga para Etapa 3: criar de cima para baixo (Epics → + Feature → + Story) `RA-01_Roteiro_Product_Backlog.md:132`, corrigir órfãos via Mapping `RA-01_Roteiro_Product_Backlog.md:138`, e verificar com 4 queries vazias `RA-01_Roteiro_Product_Backlog.md:165`.

---

*Fontes: `RA-01_Roteiro_Product_Backlog.md:72-90`, `Azure_Boards_Backlog_e_Sprint1.md:247-386, 638-679, 812-859, 975-1013`, `Connexa_Proposta_do_Projeto.md:188-405, 539-576`, `Exemplo_Referencia_Backlog_PedeJa.md:24-55, 93-122`.*
