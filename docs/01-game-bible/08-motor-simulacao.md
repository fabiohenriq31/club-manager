# Filosofia

O mundo nunca para.

O jogador apenas observa uma pequena parte dele.

O jogo inteiro é uma simulação.

Não existem scripts.

Não existem eventos aleatórios sem explicação.

Tudo acontece porque alguma coisa provocou.

---

# O coração do jogo

Quero que exista apenas um responsável por atualizar o mundo.

Chamaremos de

## Simulation Engine

Ele será responsável por responder apenas uma pergunta.

> "O que aconteceu nesta semana?"
> 

---

# Como o tempo funciona

Outra decisão importante.

O jogo será baseado em semanas.

Cada clique em

```
Simular Semana
```

faz o Simulation Engine trabalhar.

---

# O ciclo

Toda semana.

A ordem sempre será a mesma.

```
1 - Atualizar calendário

↓

2 - Processar notícias

↓

3 - Atualizar economia

↓

4 - Atualizar jogadores

↓

5 - Atualizar funcionários

↓

6 - Mercado

↓

7 - Patrocínio

↓

8 - Treinos

↓

9 - Partidas

↓

10 - Moral

↓

11 - Torcida

↓

12 - Imprensa

↓

13 - Eventos

↓

14 - Salvar histórico
```

Nunca muda.

---

# Por que isso?

Porque evita bugs.

Exemplo.

Você vende jogador.

↓

Dinheiro entra.

↓

Financeiro atualiza.

↓

Só depois.

Patrocínio recalcula.

↓

Só depois.

Torcida reage.

↓

Só depois.

Imprensa publica.

Tudo possui ordem.

---

# Eventos

O Simulation Engine não altera objetos diretamente.

Ele gera eventos.

Exemplo.

```
PlayerSold
```

Esse evento é publicado.

Quem escuta?

Financeiro.

Mercado.

Torcida.

Marketing.

Treinador.

Todos.

---

# Exemplo

Você vende um atacante.

Evento.

```
PLAYER_SOLD
```

O Financeiro escuta.

↓

Adiciona dinheiro.

---

Treinador escuta.

↓

Perde qualidade.

↓

Quer reposição.

---

Marketing escuta.

↓

Camisa vende menos.

---

Torcida escuta.

↓

Reclama.

---

Patrocinador escuta.

↓

Recalcula interesse.

---

Imprensa escuta.

↓

Escreve notícia.

---

Nenhum sistema conversa diretamente.

Todos conversam através dos eventos.

Isso deixa o projeto absurdamente organizado.

---

# Tipos de Eventos

Teremos centenas.

Alguns.

## Futebol

```
MatchFinished

GoalScored

PlayerInjured

PlayerSuspended

CoachHired

CoachFired
```

---

## Financeiro

```
SalaryPaid

LoanApproved

DebtExpired

DebtRenegotiated

SponsorPayment

TicketRevenue
```

---

## Mercado

```
TransferAccepted

TransferRejected

PlayerLoaned

ContractRenewed
```

---

## Diretoria

```
CEOHired

DirectorResigned

BoardMeeting

BudgetApproved
```

---

## Marketing

```
NewSponsor

CampaignLaunched

BrandScoreUpdated

SocialMediaBoom
```

---

## Mundo

```
EconomicCrisis

TVDealUpdated

CompetitionRulesChanged

NewInvestor
```

---

# Scheduler

Outra ideia.

O mundo possui agenda.

Hoje.

```
05/07

Pagamento salários
```

Semana seguinte.

```
12/07

Jogo

Reunião Conselho

Pagamento Banco
```

Tudo possui data.

---

# Tick

O jogo inteiro funciona por Tick.

Cada semana.

```
Tick 284

↓

Simulation Engine

↓

Atualiza tudo

↓

Tick 285
```

Isso facilita salvar.

---

# Save

O Save não salva apenas dados.

Ele salva o mundo inteiro.

```
Estado dos clubes

Estado dos jogadores

Estado da economia

Estado da IA

Calendário

Histórico

Eventos pendentes
```

Você pode continuar exatamente de onde parou.

---

# Logs

Outra ideia.

Tudo gera log.

Exemplo.

```
Semana 214

Corinthians pagou salários

↓

Cruzeiro contratou treinador

↓

Santos revelou atacante

↓

Flamengo recebeu novo patrocinador
```

Isso ajuda muito até para debugar o jogo.

---

# Determinismo

Quero propor algo importante.

Se nada mudar.

O resultado sempre será igual.

Nada de números completamente aleatórios.

Sempre existirão probabilidades calculadas.

Exemplo.

Não é.

```
40%

porque sim.
```

É.

```
Chance

Base

↓

Forma

↓

Moral

↓

Treinador

↓

Clima

↓

Entrosamento

↓

Lesão

↓

Resultado
```

Tudo explicável.

---

# Seeds

Mesmo assim.

Usaremos Seed.

Exemplo.

```
Save criado

Seed

94382711
```

Todo evento aleatório utiliza essa Seed.

Isso permite.

Replays.

Modo espectador.

Compartilhar saves.

---

# Dependências

O Simulation Engine nunca acessa telas.

Nunca acessa React.

Nunca acessa componentes.

Ele só conhece regras.

Isso deixa o jogo extremamente rápido.

---

# Paralelismo

Outra ideia.

Alguns cálculos podem ocorrer juntos.

Exemplo.

```
Atualizar todos os clubes

↓

Atualizar todos os patrocinadores

↓

Atualizar economia mundial
```

Isso facilita quando houver centenas de clubes.

---

# Motor Modular

Quero dividir o Engine.

```
Simulation Engine

│

├── Finance Engine

├── Football Engine

├── Market Engine

├── Sponsor Engine

├── Media Engine

├── AI Engine

├── Youth Engine

├── Economy Engine

├── History Engine
```

Cada um resolve apenas seu problema.

---

# Regras

Nenhum módulo altera outro.

Sempre publica evento.

---

# Exemplo completo

Você clica.

```
Simular Semana
```

---

Football Engine.

```
Corinthians venceu.
```

↓

Evento.

```
MATCH_WON
```

---

Finance Engine.

```
Premiação

+800 mil.
```

↓

Evento.

```
MONEY_RECEIVED
```

---

Marketing.

```
Torcida cresce.
```

↓

Evento.

```
BRAND_UPDATED
```

---

Patrocínio.

```
Empresa interessada.
```

↓

Evento.

```
SPONSOR_INTEREST
```

Tudo encadeado.

---

# O conceito que pode tornar o jogo infinito

Agora vem a ideia que considero a mais importante de todo o projeto.

## O mundo será baseado em "necessidades".

Nenhuma IA recebe ordens do tipo:

```
Contrate João Silva.
```

Ela pensa.

```
Preciso de atacante.

↓

Tenho dinheiro?

↓

Não.

↓

Posso vender alguém?

↓

Sim.

↓

Quem?

↓

Reserva.

↓

Vendeu.

↓

Agora compro atacante.
```

Isso vale para tudo.

Patrocínio.

Treinadores.

CT.

Financeiro.

Base.

Mercado.

Tudo.

