# Documento 11 — Mapa do Domínio

## Objetivo

Definir as entidades principais do Club Manager, seus relacionamentos e responsabilidades.

## Domínios principais

- World
- Save
- Club
- Player
- Coach
- Employee
- Sponsor
- Company
- Competition
- Match
- Finance
- Event
- News
- Market
- Youth Academy

## Relação geral

```text
World
├── Clubs
├── Players
├── Coaches
├── Employees
├── Companies
├── Competitions
├── Events
└── Economy

Save
└── World

Club
├── Players
├── Coaches
├── Employees
├── Sponsors
├── Finances
├── Youth Academy
└── Infrastructure
```

## Regra principal

O jogo será orientado a eventos.

Nenhum domínio deve alterar outro diretamente quando a mudança tiver impacto no mundo.

Exemplo:

```text
PlayerSold
→ Finance recebe dinheiro
→ Club perde atleta
→ Fans reagem
→ Sponsor recalcula valor
→ News gera manchete
```
