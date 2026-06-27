# 1. Elevator Pitch

> **Club Manager é um simulador profundo de gestão de clubes de futebol onde o jogador assume a presidência de um clube e precisa equilibrar sucesso esportivo, sustentabilidade financeira, desenvolvimento institucional e relacionamento com torcida, patrocinadores e conselho.**
> 

---

# 2. Os 5 pilares do jogo

Todo sistema do jogo deve fortalecer pelo menos um destes pilares.

## 🏆 Pilar 1 — Futebol

Tudo relacionado ao desempenho dentro de campo.

Inclui:

- Elenco
- Treinos
- Treinador
- Scout
- Base
- Lesões
- Tática
- Partidas

---

## 💰 Pilar 2 — Gestão Financeira

Todo dinheiro do clube.

Inclui:

- Caixa
- Fluxo de caixa
- Dívidas
- Empréstimos
- Patrocínio
- Bilheteria
- Sócio-torcedor
- Direitos de TV
- Venda de jogadores
- Investimentos

---

## 👔 Pilar 3 — Gestão Institucional

Quem administra o clube.

Inclui:

- Presidente (jogador)
- CEO
- Diretor Financeiro
- Diretor de Futebol
- Jurídico
- Marketing
- RH
- Conselho
- SAF

---

## 📈 Pilar 4 — Marca

O clube é uma empresa.

Quanto vale essa marca?

Influenciado por:

- Títulos
- Torcida
- Redes sociais
- Audiência
- Ídolos
- Estádio
- História
- Marketing

---

## 🌎 Pilar 5 — Ecossistema

O mundo reage às suas decisões.

Inclui:

- Imprensa
- Torcida
- Empresários
- Outros clubes
- Patrocinadores
- Federações
- Árbitros (mais para frente)
- Mercado internacional

---

# 3. Filosofia do Projeto

Aqui está a regra mais importante do jogo.

## O jogador nunca joga futebol.

Ele administra pessoas.

Administra dinheiro.

Administra recursos.

O futebol é consequência.

Essa decisão muda tudo.

---

# 4. Filosofia da Simulação

Outro princípio importante.

## Nada acontece por sorte.

Tudo possui uma causa.

Exemplo.

Você ganha o Brasileirão.

Isso NÃO gera simplesmente:

+100 milhões.

Na verdade gera:

```
Campeão

↓

Mais exposição

↓

Mais audiência

↓

Mais patrocinadores interessados

↓

Mais venda de camisa

↓

Mais seguidores

↓

Mais receita

↓

Jogadores valorizados

↓

Empresários pedem aumento

↓

Folha cresce

↓

Expectativa da torcida aumenta
```

O jogo inteiro será baseado em cadeias de consequência.

---

# 5. O conceito de Mundo Vivo

Essa talvez seja a mecânica mais importante.

O mundo continua andando sem você.

Enquanto você administra o Corinthians:

- Palmeiras negocia jogadores.
- Flamengo troca treinador.
- Santos revela um craque.
- Bahia fecha novo patrocinador.
- Vasco pega empréstimo.
- Cruzeiro amplia CT.

Você não controla o universo.

Você vive nele.

---

# 6. Entidades do Mundo

O mundo será composto por entidades.

Cada entidade possui IA própria.

## Clubes

Possuem objetivos.

Tomam decisões.

Contratam.

Vendem.

Trocam treinador.

Investem.

---

## Jogadores

Possuem desejos.

Querem dinheiro.

Querem títulos.

Querem seleção.

Querem Europa.

Querem estabilidade.

---

## Treinadores

Possuem estilo.

Personalidade.

Ego.

Objetivos.

---

## Empresários

Negociam contratos.

Pedem aumentos.

Levam atletas.

Criam crises.

---

## Patrocinadores

Buscam retorno.

Analisam imagem.

Negociam.

Desistem.

Mudam estratégia.

---

## Torcida

Possui memória.

Não esquece tudo em duas semanas.

Um título gera boa vontade.

Cinco anos ruins geram pressão.

---

## Conselho

Possui interesses próprios.

Nem sempre concorda com você.

---

# 7. A Regra das Consequências

Essa regra será aplicada em todos os sistemas.

Toda decisão importante precisa gerar impacto em pelo menos **três áreas**.

Exemplo.

Vender um craque.

Impacta:

✅ Futebol

✅ Financeiro

✅ Torcida

✅ Marca

✅ Patrocínio

Não apenas um número no caixa.

---

# 8. Horizonte Temporal

O jogo nunca acaba.

Você pode jogar:

5 anos.

20 anos.

40 anos.

50 anos.

O clube envelhece.

Ídolos aposentam.

Novas gerações aparecem.

As finanças mudam.

---

# 9. Objetivo do Jogador

Não existe uma vitória definitiva.

Você constrói uma história.

Alguns jogadores vão querer:

- ser campeão do mundo

Outros:

- quitar todas as dívidas

Outros:

- revelar o maior jogador do planeta

Outros:

- transformar um clube pequeno em gigante

Cada campanha conta uma história diferente.

---

# 10. Nossa primeira grande decisão de design

Aqui quero propor algo que considero um dos maiores diferenciais do projeto.

## O jogo NÃO terá Overall.

Sim, diferente do Brasfoot, EA FC e vários managers.

Em vez de:

```
Yuri Alberto

Overall: 82
```

Teremos atributos separados:

```
Finalização: 85
Movimentação: 79
Velocidade: 73
Jogo Aéreo: 81
Frieza: 88
Posicionamento: 84
Pressão: 72
```

O "nível" do jogador será calculado dinamicamente conforme:

- posição em que atua;
- estilo do treinador;
- esquema tático;
- momento físico;
- moral;
- entrosamento;
- idade.

Assim, um atacante pode render muito em um clube e apenas razoavelmente em outro, sem que seus atributos mudem magicamente.