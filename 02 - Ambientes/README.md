
# Desafio 02 - Ambientes de Programação

## Tema: Compiladores, Interpretadores e Máquinas Virtuais

Neste desafio, vamos explorar os principais componentes dos ambientes de programação: **compiladores**, **interpretadores** e **máquinas virtuais**. Cada um possui papel fundamental na execução de programas, dependendo da linguagem utilizada.

---

## 1. Conceitos-Chave

### Compilador

- Converte o código fonte para código de máquina **antes da execução**.
- Produz um executável independente.
- Exemplo: `gcc` para C, `javac` para Java.

### Interpretador

- Executa o código **linha por linha** diretamente.
- Não gera um arquivo executável.
- Exemplo: Python, Ruby, PHP.

### Máquina Virtual

- Emula um ambiente de execução padronizado.
- Interpreta bytecode, não o código-fonte diretamente.
- Exemplo: JVM (Java Virtual Machine), .NET CLR.

---

## 2. Diagrama Explicativo

<img width="905" height="615" alt="image" src="https://github.com/user-attachments/assets/788c7854-fd81-44bf-abd2-1642eb908d63" />

```

---

## 3. Comparação entre os Modelos

| Critério               | Compilador       | Interpretador       | Máquina Virtual         |
|------------------------|------------------|----------------------|--------------------------|
| Tempo de execução      | Mais rápido      | Mais lento           | Intermediário            |
| Análise de erros       | Antes da execução| Durante execução     | Misto (compilação e execução) |
| Portabilidade          | Baixa            | Alta                 | Alta                     |
| Geração de código      | Binário nativo   | Não gera             | Bytecode                 |
| Exemplos               | C, C++           | Python, Bash         | Java, C#, Kotlin         |

---

## 4. Conclusão

Ambientes de programação são estruturados de acordo com o modelo de execução da linguagem. Entender as diferenças entre **compiladores**, **interpretadores** e **máquinas virtuais** ajuda a tomar decisões sobre desempenho, portabilidade e ambiente de desenvolvimento.

---

## 5. Referências

- [Compilers vs Interpreters - GeeksforGeeks](https://www.geeksforgeeks.org/compiler-vs-interpreter/)
- [JVM Internals](https://docs.oracle.com/javase/specs/)
- [Python Execution Model](https://docs.python.org/3/reference/executionmodel.html)
