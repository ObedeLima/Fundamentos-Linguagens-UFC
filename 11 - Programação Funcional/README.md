
# Desafio 11 - Programação Funcional

## Linguagem Utilizada: Python
Neste desafio, aplicamos conceitos da **programação funcional** utilizando **Python**, com ênfase no uso de **funções de alta ordem**, **funções anônimas (lambda)** e **recursão**.

---

## 1. Conceitos Envolvidos

| Conceito              | Descrição |
|-----------------------|-----------|
| **Função pura**       | Função sem efeitos colaterais e que sempre retorna o mesmo resultado dado um mesmo input. |
| **Função de alta ordem** | Função que recebe outra função como argumento ou retorna uma função. |
| **Recursão**          | Função que se chama a si mesma. |
| **Lambda**            | Funções anônimas e curtas. |

---

## 2. Exemplo: Processamento funcional de uma lista

### Objetivo: Dada uma lista de inteiros, aplicar os seguintes passos de forma funcional:

1. Filtrar apenas os números pares.
2. Dobrar os valores.
3. Somar todos os valores resultantes.

### Código em Python

```python
from functools import reduce

numeros = [1, 2, 3, 4, 5, 6]

# Passo 1: filtrar pares
pares = list(filter(lambda x: x % 2 == 0, numeros))

# Passo 2: mapear para o dobro
dobrados = list(map(lambda x: x * 2, pares))

# Passo 3: reduzir à soma total
soma = reduce(lambda x, y: x + y, dobrados)

print("Números:", numeros)
print("Pares:", pares)
print("Dobrados:", dobrados)
print("Soma:", soma)
```

### Saída:

```
Números: [1, 2, 3, 4, 5, 6]
Pares: [2, 4, 6]
Dobrados: [4, 8, 12]
Soma: 24
```

---

## 3. Exemplo de Recursão: Soma de uma lista

```python
def soma_lista(lista):
    if not lista:
        return 0
    return lista[0] + soma_lista(lista[1:])

print(soma_lista([1, 2, 3, 4, 5]))  # Resultado: 15
```

---

## 4. Conclusão

A **programação funcional** é um paradigma poderoso que promove código mais limpo, modular e previsível. Em Python, embora não seja uma linguagem puramente funcional, muitos recursos como `map`, `filter`, `reduce`, `lambda` e **recursão** permitem programar com esse estilo com eficiência e elegância.

---

## 5. Referências

- [Documentação Python: functools](https://docs.python.org/3/library/functools.html)
- [Funções Lambda, Map, Filter e Reduce](https://realpython.com/python-map-function/)
