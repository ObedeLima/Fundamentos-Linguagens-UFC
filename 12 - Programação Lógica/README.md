
# Desafio 12 - Programação Lógica

## Linguagem: Pseudocódigo inspirado em Prolog

O objetivo é representar logicamente as **cores de um mapa**, garantindo que regiões vizinhas não tenham a mesma cor.

---

## 1. Problema Escolhido: Colorir Mapa com 3 Cores

Queremos colorir as regiões de um mapa com três cores: **vermelho**, **verde** e **azul**, de modo que **regiões vizinhas não tenham a mesma cor**.

---

## 2. Fatos: Regiões vizinhas

```prolog
vizinho(a, b).
vizinho(a, c).
vizinho(b, c).
vizinho(b, d).
vizinho(c, d).
vizinho(d, e).
```

Como a relação de vizinhança é simétrica, também devemos considerar:

```prolog
vizinho(X, Y) :- vizinho(Y, X).
```

---

## 3. Cores possíveis

```prolog
cor(vermelho).
cor(verde).
cor(azul).
```

---

## 4. Regras de coloração válida

```prolog
% Atribui cores às regiões, garantindo que vizinhos tenham cores diferentes
mapa(CorA, CorB, CorC, CorD, CorE) :-
    cor(CorA), cor(CorB), cor(CorC), cor(CorD), cor(CorE),
    CorA \= CorB,
    CorA \= CorC,
    CorB \= CorC,
    CorB \= CorD,
    CorC \= CorD,
    CorD \= CorE.
```

---

## 5. Consulta (exemplo de uso)

```prolog
?- mapa(A, B, C, D, E).
A = vermelho,
B = verde,
C = azul,
D = vermelho,
E = azul.
```

---

## 6. Conclusão

A **programação lógica** pode ser aplicada em problemas clássicos de **satisfação de restrições**, como o problema das **n cores em mapas**. A abordagem é declarativa e permite expressar regras de forma clara e natural, deixando o motor lógico encontrar soluções válidas.

Esse paradigma é especialmente útil em:

- Sistemas especialistas
- Inteligência artificial
- Planejamento e lógica de jogos
- Resolução de quebra-cabeças

---

## 7. Referências

- [Aprendizado com Prolog](https://www.learnprolognow.org/)
- [Coloração de mapas - problema clássico de IA](https://en.wikipedia.org/wiki/Map_coloring)
