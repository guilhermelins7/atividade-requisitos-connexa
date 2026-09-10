# Exemplo de referência — Backlog e Sprint 1 do **PedeJá**

**Disciplina de Engenharia de Software** · Prof. Claudio Nunes
**Finalidade:** material de consulta para as atividades RA-01 e RA-02.

> **Por que um domínio diferente do Connexa.** Este exemplo existe para mostrar *forma*, *nível* e *grau de detalhe* — não conteúdo aproveitável. Copiar trechos daqui para o backlog do Connexa não funciona: o domínio é outro, os envolvidos são outros e a correção percebe. Use-o para responder "como se escreve isso?", nunca "o que devo escrever?".

---

## 1. O domínio

O **Cantinho da Esquina** é um restaurante de bairro com dez mesas e forte movimento de entrega. Hoje, todo pedido de entrega chega por telefone: o atendente anota em um bloco, repassa à cozinha em voz alta e calcula o troco de cabeça. Nos horários de pico, o telefone fica ocupado, pedidos se perdem e o entregador sai sem saber o valor exato a receber.

O dono contratou o desenvolvimento do **PedeJá**, um aplicativo pelo qual o cliente monta e envia o próprio pedido.

**Objetivo declarado:** reduzir em 70% os pedidos anotados por telefone em três meses.

**Restrições:** sem integração com o sistema fiscal existente; sem pagamento dentro do aplicativo nesta fase (o pagamento continua na entrega); o cardápio muda semanalmente e é mantido pelo próprio dono.

---

## 2. Hierarquia completa

```
EPIC 1   Cliente monta e envia o pedido sem depender do telefone
  │
  ├─ FEATURE 1.1   Consulta ao cardápio do dia
  │     ├─ US-01   Ver o cardápio disponível hoje
  │     └─ US-02   Ver a descrição e o preço de um item
  │
  ├─ FEATURE 1.2   Montagem do pedido
  │     ├─ US-03   Adicionar um item ao carrinho
  │     ├─ US-04   Remover um item do carrinho
  │     ├─ US-05   Alterar a quantidade de um item
  │     └─ US-06   Aplicar um cupom de desconto
  │
  └─ FEATURE 1.3   Envio do pedido
        ├─ US-07   Informar endereço de entrega
        └─ US-08   Enviar o pedido para a cozinha

EPIC 2   Cozinha e entrega trabalham sem anotação em papel
  │
  ├─ FEATURE 2.1   Painel da cozinha
  │     ├─ US-09   Ver os pedidos em fila, na ordem de chegada
  │     └─ US-10   Marcar um pedido como pronto
  │
  └─ FEATURE 2.2   Acompanhamento pelo cliente
        └─ US-11   Ver o status do meu pedido

EPIC 3   Dono mantém o cardápio sem depender de terceiros
  │
  └─ FEATURE 3.1   Gestão de cardápio
        ├─ US-12   Cadastrar um item do cardápio
        └─ US-13   Marcar um item como indisponível
```

**Leitura do exemplo:** três Epics, seis Features, treze histórias. Cada Epic nomeia uma mudança percebida por alguém (cliente, cozinha, dono) — nenhum nomeia um módulo do sistema ("Epic: Cadastro", "Epic: Frontend" seriam erros de nível).

---

## 3. Backlog ordenado

A ordem responde à pergunta: *se a equipe só conseguir entregar três coisas, quais são?*

| # | ID | História (título) | Pontos | MoSCoW | Por que nesta posição |
|---:|---|---|---:|---|---|
| 1 | US-01 | Ver o cardápio disponível hoje | 3 | Must | Sem cardápio visível, nada mais existe para o cliente |
| 2 | US-03 | Adicionar um item ao carrinho | 3 | Must | Primeiro passo real da montagem do pedido |
| 3 | US-08 | Enviar o pedido para a cozinha | 5 | Must | É o item que fecha o resultado prometido no objetivo |
| 4 | US-07 | Informar endereço de entrega | 3 | Must | Sem endereço, o pedido enviado é inútil para a entrega |
| 5 | US-09 | Ver os pedidos em fila, na ordem de chegada | 5 | Must | Sem isso, o pedido enviado volta a virar papel |
| 6 | US-04 | Remover um item do carrinho | 2 | Should | Erro de montagem é frequente, mas há contorno: refazer |
| 7 | US-05 | Alterar a quantidade de um item | 2 | Should | Mesma lógica do anterior |
| 8 | US-10 | Marcar um pedido como pronto | 3 | Should | Organiza a cozinha; a fila já funciona sem isso |
| 9 | US-12 | Cadastrar um item do cardápio | 5 | Should | Enquanto não existe, o cardápio é carregado pela equipe |
| 10 | US-13 | Marcar um item como indisponível | 2 | Should | Contorno temporário: remover o item do cardápio |
| 11 | US-02 | Ver a descrição e o preço de um item | 2 | Could | Melhora a decisão de compra; o preço já aparece na lista |
| 12 | US-11 | Ver o status do meu pedido | 8 | Could | Desejável; hoje o cliente liga para perguntar |
| 13 | US-06 | Aplicar um cupom de desconto | 5 | Wont | Não há campanha de cupom prevista para este trimestre |

**Observação sobre a escala:** a história de referência escolhida pela equipe foi **US-01 = 3 pontos**. Todas as demais foram estimadas por comparação com ela.

**Observação sobre MoSCoW:** cinco `Must` somando 19 pontos, contra 31 pontos no restante — os itens obrigatórios não dominam o backlog. Um backlog com treze `Must` não teria sido priorizado.

---

## 4. Duas histórias detalhadas

### US-03 — Adicionar um item ao carrinho

**Descrição**

> Como cliente do PedeJá, quero adicionar um item do cardápio ao meu carrinho, para montar meu pedido antes de decidir enviá-lo.

**Critérios de aceite**

```gherkin
Cenário: item disponível adicionado ao carrinho vazio
  Dado que o carrinho está vazio
    E que o item "Prato Feito" custa R$ 24,00 e está disponível
  Quando o cliente adiciona "Prato Feito" ao carrinho
  Então o carrinho passa a exibir 1 item
    E o total do carrinho passa a ser R$ 24,00

Cenário: mesmo item adicionado duas vezes
  Dado que o carrinho já contém 1 unidade de "Prato Feito"
  Quando o cliente adiciona "Prato Feito" novamente
  Então o carrinho exibe 2 unidades de "Prato Feito" em uma única linha
    E o total do carrinho passa a ser R$ 48,00

Cenário: item indisponível
  Dado que o item "Feijoada" está marcado como indisponível hoje
  Quando o cliente tenta adicionar "Feijoada" ao carrinho
  Então o item não é adicionado
    E a mensagem "item indisponível hoje" é exibida

Cenário: limite de itens por pedido
  Dado que o carrinho contém 20 itens, o máximo permitido por pedido
  Quando o cliente tenta adicionar mais um item
  Então o item não é adicionado
    E a mensagem informa o limite de 20 itens por pedido
```

**Por que estes cenários.** O primeiro cobre o caminho feliz. O segundo revela uma regra de negócio que o briefing não mencionava — agrupar ou não itens repetidos — e que precisou ser decidida. O terceiro e o quarto são exceções: indisponibilidade e limite. Note que nenhum cenário menciona tabela, endpoint ou componente de tela.

**Tarefas (criadas no planejamento da sprint)**

| Task | Horas |
|---|---:|
| Modelar carrinho e itens de carrinho | 4h |
| Implementar inclusão de item com agrupamento de repetidos | 5h |
| Implementar as validações de disponibilidade e limite | 4h |
| Construir a tela de cardápio com o botão de adicionar | 6h |
| Escrever os testes dos quatro cenários de aceite | 3h |
| Revisar em par e ajustar | 2h |
| **Total** | **24h** |

---

### US-08 — Enviar o pedido para a cozinha

**Descrição**

> Como cliente do PedeJá, quero enviar meu pedido montado para a cozinha, para receber a comida sem precisar telefonar.

**Critérios de aceite**

```gherkin
Cenário: pedido válido enviado
  Dado que o carrinho contém 2 itens e o endereço de entrega está informado
  Quando o cliente confirma o envio do pedido
  Então o pedido recebe um número sequencial
    E o pedido passa a aparecer na fila da cozinha
    E o carrinho é esvaziado

Cenário: pedido sem endereço
  Dado que o carrinho contém 2 itens e nenhum endereço foi informado
  Quando o cliente tenta confirmar o envio
  Então o pedido não é enviado
    E a mensagem indica que o endereço é obrigatório

Cenário: carrinho vazio
  Dado que o carrinho não contém nenhum item
  Quando o cliente tenta confirmar o envio
  Então o botão de envio permanece indisponível

Cenário: restaurante fechado
  Dado que o horário atual está fora do período de atendimento
  Quando o cliente tenta confirmar o envio
  Então o pedido não é enviado
    E a mensagem informa o próximo horário de atendimento
```

---

## 5. Plano da Sprint 1

**Meta**

> Ao final desta sprint, um cliente consegue montar um pedido a partir do cardápio do dia e enviá-lo para a cozinha, sem telefonar.

**Capacidade**

```
Horas por integrante, por semana ................  6h
Integrantes .....................................   5
Semanas .........................................   2
                                              ------
Capacidade bruta ................................  60h
( - ) reserva de 20% para imprevistos ...........  12h
( - ) reuniões da equipe ........................   4h
                                              ------
Capacidade de planejamento ......................  44h
Alvo da primeira sprint (75%) ...................  33h
```

**Escopo selecionado**

| História | Pontos | Horas das tarefas |
|---|---:|---:|
| US-01 — Ver o cardápio disponível hoje | 3 | 10h |
| US-03 — Adicionar um item ao carrinho | 3 | 24h |
| **Total** | **6** | **34h** |

**Como o escopo foi ajustado.** A equipe havia selecionado também US-08 (Enviar o pedido), o que levaria o total a 52h — acima da capacidade. Como a meta prioriza *montar e enviar*, houve discussão real: manter US-08 e cortar US-03 tornaria a meta inalcançável, porque não há o que enviar sem carrinho. A equipe optou por **devolver US-08 ao backlog** e ajustar a meta para o que efetivamente cabe:

> Ao final desta sprint, um cliente consegue ver o cardápio do dia e montar seu pedido no carrinho.

Devolver a história e reescrever a meta **antes** do início da sprint é o comportamento esperado. Manter as três histórias e terminar as três pela metade não entregaria nada verificável.

**Riscos**

| Risco | Resposta prevista |
|---|---|
| Dois integrantes têm prova na segunda semana | Concentrar as tarefas deles na primeira semana |
| A equipe nunca usou a biblioteca de interface escolhida | Reservar 4h de estudo na primeira tarefa; se não render, trocar por solução já conhecida |
| O dono do restaurante ainda não definiu o limite de itens por pedido | Adotar 20 como valor provisório e registrar a decisão |

**Definition of Done desta sprint**

- [ ] Todos os critérios de aceite da história verificados manualmente
- [ ] Testes automatizados dos cenários principais passando
- [ ] Código revisado por outro integrante
- [ ] Nenhuma tarefa da história em estado `Active`
- [ ] História movida para `Closed` pelo guardião da qualidade

---

## 6. O que este exemplo pretende ensinar

| Ponto | Onde aparece |
|---|---|
| Epic nomeia mudança percebida, não módulo | Seção 2 |
| Feature agrupa histórias, não camadas técnicas | Seção 2 |
| História é fatia vertical, com papel e benefício | Seção 4 |
| Cenário de exceção revela regra de negócio ausente | US-03, cenário do item repetido |
| Ordem justificada, item a item | Seção 3, última coluna |
| `Must` limitado, não universal | Seção 3, observação sobre MoSCoW |
| Estimativa por comparação com uma referência declarada | Seção 3, observação sobre a escala |
| Tarefas de 2h a 8h, cobrindo teste e revisão | Seção 4, tabela de tarefas |
| Ajustar escopo — e a meta — antes de começar | Seção 5 |

---

*Material de apoio — Disciplina de Engenharia de Software — Projeto Connexa.*
