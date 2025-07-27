
# Desafio 06 - Subprogramas

## Linguagens Utilizadas: Python e C

Este desafio demonstra o conceito de **subprogramas** e a diferença entre **passagem por valor** e **passagem por referência**, usando dois exemplos simples:

- **Python**: Suporta passagem por referência para objetos mutáveis.
- **C**: Suporta explicitamente ambos os modos de passagem, com ponteiros usados para referência.

---

## 1. Conceitos

| Conceito              | Descrição |
|-----------------------|-----------|
| **Passagem por valor**      | Uma cópia da variável é passada para a função. Alterações dentro da função **não** afetam a variável original. |
| **Passagem por referência** | Um ponteiro ou referência é passado. Alterações dentro da função **afetam** a variável original. |

---

## 2. Exemplo em Python

### Passagem por valor (imutável)

```python
def dobrar_valor(x):
    x = x * 2
    print("Dentro da função:", x)

a = 10
dobrar_valor(a)
print("Fora da função:", a)
```

**Saída:**

```
Dentro da função: 20
Fora da função: 10
```

O valor original de `a` **não** foi alterado.

### Passagem por referência (mutável)

```python
def adicionar_elemento(lista):
    lista.append(99)

numeros = [1, 2, 3]
adicionar_elemento(numeros)
print(numeros)
```

**Saída:**

```
[1, 2, 3, 99]
```

A lista foi alterada, pois listas são objetos mutáveis.

---

## 3. Exemplo em C

### Passagem por valor

```c
#include <stdio.h>

void dobrar(int x) {
    x = x * 2;
    printf("Dentro da função: %d\n", x);
}

int main() {
    int a = 10;
    dobrar(a);
    printf("Fora da função: %d\n", a);
    return 0;
}
```

**Saída:**

```
Dentro da função: 20
Fora da função: 10
```

 `a` não foi alterado porque `x` é uma cópia.

---

### Passagem por referência

```c
#include <stdio.h>

void dobrar(int *x) {
    *x = *x * 2;
}

int main() {
    int a = 10;
    dobrar(&a);
    printf("Valor final: %d\n", a);
    return 0;
}
```

**Saída:**

```
Valor final: 20
```

 `a` foi alterado porque o endereço foi passado.

---

## 4. Conclusão

- Em **Python**, objetos mutáveis (listas, dicionários) funcionam como "referência", enquanto tipos primitivos (int, str) funcionam como valor.
- Em **C**, é necessário usar ponteiros para passagem por referência.
- Entender os modos de passagem é essencial para evitar efeitos colaterais inesperados em funções.
