# Objetivo do MVP

Responder uma pergunta:

> **Administrar um clube endividado por temporadas é divertido?**
> 

Se a resposta for sim, expandimos.

---

# O que entra no MVP

## 1. Escolher clube

No início:

```
Corinthians
Flamengo
Palmeiras
Santos
Cruzeiro
Vasco
São Paulo
Grêmio
Atlético-MG
Botafogo
```

Cada clube terá:

```
caixa
dívida
folha
torcida
brand score
elenco
treinador
patrocínios
objetivos
```

---

## 2. Dashboard

Tela principal com:

```
Caixa
Dívida
Folha salarial
Próximo jogo
Pressão da torcida
Moral do elenco
Notícias
Alertas financeiros
Botão Simular Semana
```

---

## 3. Financeiro básico

Entradas:

```
TV
bilheteria
patrocínio
sócio torcedor
venda de jogador
premiação
```

Saídas:

```
salários
juros
parcelas
funcionários
viagem
manutenção
```

---

## 4. Elenco

Jogadores com:

```
idade
posição
salário
contrato
valor estimado
moral
atributos principais
```

Sem overall.

---

## 5. Mercado simples

Ações:

```
comprar jogador
vender jogador
receber proposta
renovar contrato
```

---

## 6. Patrocínio

O MVP precisa ter essa mecânica.

Tipos:

```
Master
Manga
Material esportivo
Naming rights
```

Negociação simples:

```
valor anual
prazo
adiantamento
bônus por título
cláusula de rebaixamento
chance de aceitar
```

---

## 7. Diretoria básica

Cargos:

```
CEO
Diretor Financeiro
Diretor de Futebol
Diretor de Marketing
```

Cada um terá nota e salário.

---

## 8. Simulação semanal

Ao clicar em **Simular Semana**:

```
atualiza caixa
paga contas
gera notícias
simula jogo
atualiza moral
atualiza torcida
gera propostas
salva histórico
```

---

## 9. Campeonato simples

Primeira versão:

```
Brasileirão com 10 clubes
turno e returno
18 rodadas
```

Depois expandimos para 20.

---

## 10. Notícias

Notícias geradas por templates:

```
"Elenco cobra salários atrasados."
"Patrocinador demonstra interesse no clube."
"Torcida protesta após derrota."
"Jovem da base recebe sondagem."
```

IA entra depois.

---

# O que NÃO entra no MVP

```
multiplayer
mobile
editor de database
IA generativa
Libertadores
Copa do Brasil
calendário real completo
base sub-15/sub-17/sub-20 profunda
sistema tático complexo
milhares de jogadores
```

Isso tudo fica para depois.

---

# Versão 0.1 jogável

O objetivo da v0.1:

```
Escolher Corinthians
Ver crise financeira
Vender jogador
Negociar patrocinador
Contratar CEO
Simular temporada
Tentar não quebrar
```

Se isso for divertido, o projeto tem futuro.

---

# Roadmap curto

## Sprint 1 — Fundação

```
monorepo
React
API
Prisma
PostgreSQL
auth simples
estrutura do save
```

## Sprint 2 — Dados iniciais

```
clubes
jogadores
contratos
finanças
dívidas
patrocínios
```

## Sprint 3 — Dashboard

```
home do clube
cards financeiros
notícias
alertas
simular semana
```

## Sprint 4 — Simulation Engine

```
tick semanal
eventos
logs
fechamento financeiro
```

## Sprint 5 — Elenco e mercado

```
lista de jogadores
propostas
venda
compra
renovação
```

## Sprint 6 — Patrocínio

```
propostas
contraproposta
chance de aceitar
contratos ativos
pagamentos
```

## Sprint 7 — Campeonato

```
tabela
rodadas
resultado simulado
premiação
```

## Sprint 8 — Balanceamento

```
testar temporadas
corrigir dinheiro infinito
ajustar valores
melhorar UX
```

---

# Regra de ouro do MVP

**Não tentar fazer o Football Manager.**

Fazer primeiro um jogo onde a decisão seja:

```
Tenho R$ 12 milhões em caixa.
A folha é R$ 24 milhões.
Tenho parcela da dívida vencendo.
Meu melhor jovem recebeu proposta.
Meu patrocinador quer renovar por 3 anos.
O que eu faço?
```

Esse é o jogo.
