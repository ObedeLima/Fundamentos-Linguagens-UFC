
# Desafio 04 - Tipos de Dados

## Comparação entre Python, Java e C++

Este desafio apresenta uma comparação dos sistemas de tipos das linguagens **Python**, **Java** e **C++**, com foco nos aspectos de **tipagem estática/dinâmica** e **forte/fraca**. A análise é acompanhada de exemplos simples e comentados.

---

## 1. Tabela Comparativa

| Linguagem   | Tipagem         | Forte/Fraca | Observações |
|-------------|------------------|-------------|-------------|
| Python      | Dinâmica         | Forte       | Verificação em tempo de execução; impede conversões implícitas perigosas |
| Java        | Estática         | Forte       | Tipagem rigorosa com verificação em tempo de compilação |
| C++         | Estática         | Fraca       | Tipos verificados em tempo de compilação, mas permite coerções implícitas perigosas |

---

## 2. Exemplos de Código Comentados

### Python

```python
# Tipagem dinâmica e forte

x = 10         # x é um inteiro
x = "dez"      # agora x é uma string — permitido, pois é dinâmico

# Soma inválida: gera erro
print("10" + 5)  # TypeError: cannot concatenate str and int
```
 **Conclusão**: Python permite mudança de tipo (dinâmico), mas não realiza conversões automáticas perigosas (forte).

---

### Java

```java
public class Main {
    public static void main(String[] args) {
        int x = 10;
        String y = "dez";

        // Soma inválida: erro de compilação
        // int resultado = x + y;  // ERRO

        // Conversão explícita necessária
        String s = "10";
        int z = Integer.parseInt(s) + 5;
        System.out.println(z);  // 15
    }
}
```

**Conclusão**: Java exige declaração de tipo (estática) e não permite conversões implícitas entre tipos incompatíveis (forte).

---

### C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    float y = 2.5;

    // Conversão implícita (coerção): aceita, mas pode causar perda de precisão
    int resultado = x + y;
    cout << resultado << endl;  // imprime 12

    // Erro de compilação: tipos incompatíveis
    // x = "texto";  // inválido
    return 0;
}
```

**Conclusão**: C++ exige tipos em tempo de compilação (estática), mas permite coerções perigosas sem aviso (fraca).

---

## 3. Conclusão Geral

- A **tipagem estática** (Java, C++) obriga a declaração e verificação de tipos em tempo de compilação.
- A **tipagem dinâmica** (Python) oferece flexibilidade, mas exige mais atenção do programador em tempo de execução.
- A **tipagem forte** (Python, Java) evita coerções implícitas arriscadas.
- A **tipagem fraca** (C++) pode permitir comportamentos inesperados por conversões silenciosas.

### Resumo Visual

| Linguagem   | Estática/Dinâmica | Forte/Fraca | Exemplo de Conversão Implícita |
|-------------|-------------------|-------------|-------------------------------|
| Python      | Dinâmica          | Forte       | `"10" + 5` → Erro             |
| Java        | Estática          | Forte       | `"10" + 5` → Erro             |
| C++         | Estática          | Fraca       | `float + int` → permitido     |

---

## 4. Referências

- Documentação oficial Python (https://docs.python.org)
- Documentação Java (https://docs.oracle.com/en/java/)
- Documentação C++ (https://cplusplus.com/doc/)
