
# Desafio 07 - Implementação de Subprogramas

## Tópico: Pilha de Chamadas com Recursão (Sequência de Fibonacci)

Este desafio tem como objetivo demonstrar o funcionamento da **pilha de chamadas** durante a execução de uma função **recursiva**. O exemplo escolhido é o cálculo do **n-ésimo número da sequência de Fibonacci**.

---

## 1. Função Recursiva em Python

```python
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

resultado = fibonacci(4)
print("Fibonacci(4):", resultado)
```

### Saída:

```
Fibonacci(4): 3
```

A sequência de Fibonacci é: `0, 1, 1, 2, 3, 5, 8, 13, ...`

---

## 2. Simulação da Pilha de Chamadas

Vamos visualizar a pilha para `fibonacci(4)`:

```
fibonacci(4)
├── fibonacci(3)
│   ├── fibonacci(2)
│   │   ├── fibonacci(1) → 1
│   │   └── fibonacci(0) → 0
│   └── fibonacci(1) → 1
└── fibonacci(2)
    ├── fibonacci(1) → 1
    └── fibonacci(0) → 0
```

As chamadas ativas se acumulam na pilha até que os casos-base (`n == 0` ou `n == 1`) sejam atingidos.

---

## 3. Diagrama da Pilha (exemplo parcial)

```
Topo da Pilha
┌─────────────────────┐
│ fibonacci(0)        │ → retorna 0
├─────────────────────┤
│ fibonacci(2)        │ → retorna 1
├─────────────────────┤
│ fibonacci(3)        │ → retorna 2
├─────────────────────┤
│ fibonacci(2)        │ → retorna 1
├─────────────────────┤
│ fibonacci(4)        │ → retorna 3
└─────────────────────┘
Base da Pilha
```

---

## 4. Considerações sobre Recursão

- Cada chamada da função `fibonacci` gera **duas novas chamadas**, resultando em **crescimento exponencial** da pilha.
- A recursão é clara e elegante, mas **ineficiente** sem otimização (ex: **memoização**).
- O uso da **pilha de chamadas** ajuda a entender como valores intermediários são empilhados e depois "desempilhados" na ordem inversa.

---

## 5. Conclusão

A pilha de chamadas é um mecanismo fundamental para execução de subprogramas recursivos. No exemplo da sequência de Fibonacci, observamos como:

- O crescimento da pilha reflete a profundidade e ramificação da recursão.
- O desempenho da recursão pode ser ruim se não for otimizada.
- Compreender a pilha é essencial para depuração e análise de desempenho em algoritmos recursivos.
