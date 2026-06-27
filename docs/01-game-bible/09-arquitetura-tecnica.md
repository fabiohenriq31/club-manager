# Filosofia

Uma regra.

## O Front-end nunca decide nada.

Ele apenas mostra.

Toda regra do jogo fica no backend.

Sempre.

---

# Arquitetura

Eu faria algo assim.

```
                    React
                      │
                      │
                REST / WebSocket
                      │
          -------------------------
          │                       │
       API Server          Simulation Engine
          │                       │
          -----------┬------------
                      │
               PostgreSQL
```

---

# Front-end

Responsável apenas por.

Mostrar dados.

Enviar ações.

Animações.

UX.

Nada mais.

---

# Backend

Responsável por.

Autenticação.

Validação.

API.

Permissões.

Salvar.

Carregar.

---

# Simulation Engine

Esse é outro projeto.

Ele não sabe nem que React existe.

Ele recebe.

```
Simular Semana
```

E devolve.

```
Novo estado do mundo.
```

Só isso.

---

# Banco

Outro erro comum.

Guardar tudo em JSON.

Eu não faria isso.

---

Teremos.

```
Users

Saves

Worlds

Clubs

Players

Contracts

Sponsors

Matches

Events

Finances

Employees

Competitions

Youth

History

News
```

Tudo separado.

---

# Save

Cada save é independente.

Exemplo.

```
Save 1

Corinthians

2031
```

---

Outro.

```
Save 2

XV de Piracicaba

2044
```

---

Tudo separado.

---

# Mundo

Essa foi uma ideia que tive agora.

O Save possui um Mundo.

O Mundo possui.

```
Clubes

Jogadores

Empresas

Economia

Federação

Calendário
```

Assim.

No futuro.

Você pode ter mods.

---

# IDs

Tudo terá UUID.

Nunca nome.

---

# APIs

Outra decisão.

Teremos duas.

---

API Pública.

React usa.

---

API Interna.

Simulation Engine usa.

---

Isso facilita.

---

# Cache

Nem tudo precisa consultar banco.

Exemplo.

Tabela de países.

Tabela de posições.

Tabela de competições.

Ficam em memória.

---

# Histórico

Nada será apagado.

Nunca.

Jogador aposentou.

Continua no histórico.

---

Treinador morreu.

Continua.

---

Empresa saiu do futebol.

Continua.

---

Tudo gera história.

---

# Sistema de Eventos

Já falamos.

Mas agora.

Ele ganha estrutura.

```
Event

ID

Tipo

Data

Origem

Destino

Payload

Processado?
```

---

Exemplo.

```
{
 "type":"PLAYER_SOLD",
 "club":"Corinthians",
 "player":"Yuri Alberto",
 "value":120000000
}
```

---

# IA

Outra decisão enorme.

A IA nunca altera banco.

Ela responde.

```
O que devo fazer?
```

---

Resposta.

```
Comprar atacante.
```

---

Quem executa.

Simulation Engine.

---

Isso evita bugs.

---

# Logs

Tudo gera log.

Também separado.

```
Log

Data

Sistema

Mensagem

Tempo
```

---

# Configuração

Nada hardcoded.

Tudo configurável.

Exemplo.

Brasileirão.

20 clubes.

---

Quer criar.

```
Brasileirão

24 clubes.
```

Basta alterar configuração.

---

# Mods

Aqui está uma ideia gigante.

O jogo inteiro será Data Driven.

Nada fica preso no código.

---

Exemplo.

Competições.

Arquivo.

```
{
 "name":"Brasileirão",
 "teams":20
}
```

---

Outra.

```
{
 "name":"Libertadores"
}
```

---

Quer criar.

Copa Mercosul.

Só adiciona.

---

# Regras

Também.

Data Driven.

---

Exemplo.

```
{
 "salary_limit":false
}
```

---

Liga inglesa.

```
{
 "work_permit":true
}
```

---

Tudo configurável.

---

# Estatísticas

Outro módulo.

Tudo é registrado.

Exemplo.

```
Maior venda

Maior público

Maior dívida

Maior contratação

Mais gols

Mais assistências

Mais títulos
```

---

# Replay

Outra ideia.

Como tudo gera eventos.

Você pode.

Reproduzir temporada.

---

# Debug

Modo desenvolvedor.

Exemplo.

```
Ver IA.

Ver decisões.

Ver cálculos.

Ver probabilidades.

Ver histórico.
```

Isso ajuda absurdamente.

---

# Performance

Nunca recalcular tudo.

Só o necessário.

---

Exemplo.

Brand Score.

Mudou?

Não.

Não recalcula.

---

Economia.

Sem alteração.

Não recalcula.

---

# Escalabilidade

Quero pensar em 100 anos.

Hoje.

Brasileirão.

---

Depois.

Mundo inteiro.

---

Depois.

Modo online.

---

Depois.

Steam.

---

Tudo possível.

---

# Estrutura do projeto

Aqui está a primeira coisa que eu mudaria em relação aos seus projetos anteriores.

Eu faria um **monorepo**.

```
club-manager/

├── apps/
│   ├── web/              # React
│   ├── api/              # Backend HTTP
│   └── simulation/       # Motor do jogo
│
├── packages/
│   ├── database/
│   ├── engine/
│   ├── shared/
│   ├── types/
│   ├── configs/
│   ├── formulas/
│   └── ui/
│
├── docs/
│
└── scripts/
```

Percebe?

O **Simulation Engine não fica dentro da API**.

Ele é um projeto separado.

Na minha opinião isso é MUITO importante.

---

# A decisão que considero mais importante de toda a arquitetura

Agora vem uma decisão que pode economizar centenas de horas de desenvolvimento.

## Não modelaremos o jogo baseado em telas.

Modelaremos baseado em **Domínios**.

Exemplo.

Não existe.

```
Tela Financeira
```

Existe.

```
Domínio Financeiro
```

Esse domínio possui.

- regras
- serviços
- entidades
- eventos
- cálculos

Depois.

A tela financeira apenas consulta esse domínio.

Isso vale para.

- Mercado
- Jogadores
- Patrocínio
- Diretoria
- Competições
- Torcida
- Imprensa

