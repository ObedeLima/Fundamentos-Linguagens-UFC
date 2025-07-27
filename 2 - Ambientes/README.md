# 02 – Ambientes de Programação

Este desafio apresenta um diagrama explicativo sobre **compiladores**, **interpretadores** e **máquinas virtuais**, conceitos fundamentais para o funcionamento de linguagens de programação.

## Definições

- **Compilador**: Traduz todo o código-fonte para código de máquina antes da execução.
  - 📌 Exemplo: `C`, `C++` → usam `gcc`, `clang`, etc.
  
- **Interpretador**: Lê e executa o código linha por linha, sem gerar um executável completo.
  - 📌 Exemplo: `Python`, `Ruby`

- **Máquina Virtual (VM)**: Um ambiente intermediário entre o código-fonte e o hardware real, normalmente interpretando bytecode.
  - 📌 Exemplo: `Java` → usa a JVM (Java Virtual Machine)

## Diagrama Ilustrativo

> Veja o diagrama abaixo que representa o fluxo de execução para cada tipo:

![Diagrama de Ambientes de Programação](ambientes-programacao.png)

## Comparativo Rápido

| Característica        | Compilador         | Interpretador       | Máquina Virtual      |
|-----------------------|--------------------|----------------------|-----------------------|
| Tradução              | Antes da execução  | Durante a execução   | Antes (para bytecode)|
| Velocidade de Execução| Alta               | Média a baixa        | Média                |
| Portabilidade         | Baixa              | Alta                 | Alta                 |
| Exemplo de Linguagem  | C, C++             | Python, Ruby         | Java, Kotlin         |
