# Epics Extraídas — Connexa

Extração a partir de `Connexa_Proposta_do_Projeto.md:1` (conversão via Pandoc do `.pptx`) e validação com `Azure_Boards_Backlog_e_Sprint1.md:1` (hierarquia) e `Exemplo_Referencia_Backlog_PedeJa.md:1`.

> **Leitura:** Epic = objetivo amplo, meses (`Azure_Boards_Backlog_e_Sprint1.md:251`), 2 a 4 por projeto (`Azure_Boards_Backlog_e_Sprint1.md:975`), título nomeia **resultado percebido, não módulo** (`Azure_Boards_Backlog_e_Sprint1.md:376`). Epic nasce dos **objetivos declarados** pela instituição (`Azure_Boards_Backlog_e_Sprint1.md:360`). Descrição obrigatoriamente cita meta institucional e ator beneficiado (`Connexa_Proposta_do_Projeto.md:749` / `Azure_Boards_Backlog_e_Sprint1.md:1012`).

## Fonte no briefing

- **Visão do produto** `Connexa_Proposta_do_Projeto.md:313`: “aproxima estudantes compatíveis e dá à instituição visibilidade sobre os grupos ativos”
- **Objetivos declarados** `Connexa_Proposta_do_Projeto.md:339-361`:
  - ADESÃO: 20% → 45% em grupo ativo (`Connexa_Proposta_do_Projeto.md:339`)
  - PERMANÊNCIA: reduzir evasão 1º ano, identificar isolado (`Connexa_Proposta_do_Projeto.md:345`)
  - EFICIÊNCIA DA MONITORIA: reduzir tempo de agendamento (`Connexa_Proposta_do_Projeto.md:351`)
  - VISIBILIDADE: saber quantos/ativos, por curso/período (`Connexa_Proposta_do_Projeto.md:357`)
- **Frase da coordenação** `Connexa_Proposta_do_Projeto.md:75`: “quantos estudantes estarão em grupo ativo no fim do semestre”
- **Territórios dentro do escopo** `Connexa_Proposta_do_Projeto.md:370-405`: PERF, FORM, ENCO, ACOM, PAIN, MATE
- **Exemplo ilustrativo (não copiar)** `Azure_Boards_Backlog_e_Sprint1.md:340`: “Estudante encontra um grupo de estudo compatível sem depender de conhecer alguém” — coincide com Epic 1 abaixo, mas é apenas 1 ramo ilustrativo (`Azure_Boards_Backlog_e_Sprint1.md:338` alerta: “não copie este ramo: ele é um exemplo, não um gabarito”).

## Epics propostas (3 — dentro do limite 2-4)

### EPIC 1 — Estudante encontra e ingressa em grupo compatível sem depender de conhecer alguém
**Descrição (campo Description no Azure Boards):**
> Para estudantes (ingresso e noturno/trabalhador) que hoje dependem de afinidade prévia, permitir descobrir grupos da sua disciplina/período e ingressar por compatibilidade de horário/disponibilidade, elevando de ~20% para 45% a proporção em grupo ativo ao final do semestre (objetivos ADESÃO `Connexa_Proposta_do_Projeto.md:339` + PERMANÊNCIA `Connexa_Proposta_do_Projeto.md:345`). Ator beneficiado: estudante ingressante e estudante trabalhador (`Connexa_Proposta_do_Projeto.md:284`). Métrica: % em grupo ativo (`Connexa_Proposta_do_Projeto.md:329`).

**Territórios cobertos:** PERF — Perfil e disponibilidade (`Connexa_Proposta_do_Projeto.md:371`), FORM — Formação de grupos (`Connexa_Proposta_do_Projeto.md:377`)
**Pontos em aberto que viram decisão registrada:** ENTRA como alguém entra no grupo, TAM tamanho do grupo, REM presencial/remoto (`Connexa_Proposta_do_Projeto.md:539-568`)
**Features candidatas (4-8 no total do backlog):**
- F1.1 Perfil de disponibilidade do estudante (horários livres, disciplinas)
- F1.2 Descoberta de grupos abertos por disciplina/período/horário

### EPIC 2 — Grupo mantém encontros e sinaliza risco de dissolução
**Descrição:**
> Para integrantes e monitores, garantir agendamento, registro de realização e sinalização de ociosidade/encerramento, permitindo intervir antes da dissolução silenciosa após poucas semanas (`Connexa_Proposta_do_Projeto.md:69-72` problema percebido; `Connexa_Proposta_do_Projeto.md:215` monitoria). Ator beneficiado: grupo de estudo e monitoria. Contribui para PERMANÊNCIA e EFICIÊNCIA DA MONITORIA (`Connexa_Proposta_do_Projeto.md:345`, `351`).

**Territórios:** ENCO — Encontros (`Connexa_Proposta_do_Projeto.md:383`), ACOM — Acompanhamento (`Connexa_Proposta_do_Projeto.md:389`), MATE — Materiais do grupo (`Connexa_Proposta_do_Projeto.md:401`)
**Pontos em aberto:** PRES como presença é registrada, INAT quando grupo está inativo (`Connexa_Proposta_do_Projeto.md:551-563`)
**Features candidatas:**
- F2.1 Agendamento de encontros (local/meio presencial/remoto)
- F2.2 Registro e consulta de presença/realização
- F2.3 Compartilhamento de materiais do grupo

### EPIC 3 — Coordenação e monitoria enxergam o quadro e intervêm a tempo
**Descrição:**
> Para coordenação e monitoria, prover panorama por curso e período de quantos grupos existem, quais estão ativos/ociosos e adesão por perfil, sustentando decisão de alocação de monitor e prestação de contas à direção com dado, não percepção (`Connexa_Proposta_do_Projeto.md:198`, `205`, `357-361`). Ator beneficiado: coordenação (`Connexa_Proposta_do_Projeto.md:284`). Contribui para VISIBILIDADE (`Connexa_Proposta_do_Projeto.md:357`) e EFICIÊNCIA (`Connexa_Proposta_do_Projeto.md:351`: ampliar grupos por monitor).

**Território:** PAIN — Visão institucional (`Connexa_Proposta_do_Projeto.md:395`)
**Pontos em aberto:** VISI o que a coordenação enxerga (agregado vs nominal) (`Connexa_Proposta_do_Projeto.md:570`)
**Features candidatas:**
- F3.1 Painel da coordenação (curso/período, ativos/ociosos, correlação permanência)
- F3.2 Painel da monitoria (grupos sob sua responsabilidade, alertas de inatividade)

## O que NÃO é Epic (erros de nível)

- “Tela de login”, “Cadastro”, “Banco de dados” — são User Story ou Task (`Azure_Boards_Backlog_e_Sprint1.md:376-386`). Teste: complete “ao final, alguém consegue…” (`Azure_Boards_Backlog_e_Sprint1.md:394`); se “alguém” for só a equipe técnica, é Task.
- “Autenticação por e-mail institucional” é restrição transversal AUTH (`Connexa_Proposta_do_Projeto.md:453`), não Epic própria — atravessa todos os Epics como critério de aceite e requisito WCAG/LGPD/DISP (`Connexa_Proposta_do_Projeto.md:460-474`).

## Rastreabilidade para RA-01

| Epic | Objetivo briefing | Território | Work item Azure Boards |
|------|-------------------|------------|------------------------|
| 1 | ADESÃO `Connexa_Proposta_do_Projeto.md:339` | PERF, FORM | Title + Description citando meta 45% e ator estudante |
| 2 | PERMANÊNCIA+EFICIÊNCIA `Connexa_Proposta_do_Projeto.md:345,351` | ENCO, ACOM, MATE | Title + Description citando redução de evasão/dissolução |
| 3 | VISIBILIDADE `Connexa_Proposta_do_Projeto.md:357` | PAIN | Title + Description citando visão por curso/período e decisão |

Próximos passos (RA-01): expandir cada Epic em 1-3 Features (total 4-8) e 12-18 User Stories, todas filhas de Feature, com Description em forma “Como…, quero…, para…” e Acceptance Criteria em Gherkin + Story Points + Tag MoSCoW (`Azure_Boards_Backlog_e_Sprint1.md:1012`).

---
*Gerado em 2026-08-31 a partir de `Connexa_Proposta_do_Projeto.md:313`, `339-405` e `Azure_Boards_Backlog_e_Sprint1.md:251,340,360,1012,1065`.*
