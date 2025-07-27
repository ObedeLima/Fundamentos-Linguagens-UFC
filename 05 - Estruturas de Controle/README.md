
# Desafio 05 - Estruturas de Controle

## Linguagem Utilizada: Python

Neste desafio, utilizamos **Python** para demonstrar o uso de **estruturas de seleção**, **repetição** e **controle de fluxo**. O exemplo criado simula um pequeno sistema de contagem de votos para uma eleição com três candidatos.

---

## 1. Descrição do Problema

Vamos implementar um sistema de votação simples no terminal. O programa apresenta três candidatos (A, B e C), permite que o usuário vote digitando um número e, ao final, exibe o vencedor.

- **Seleção (`if/elif/else`)** será usada para validar e contar os votos.
- **Repetição (`while`)** permitirá votação contínua até o usuário decidir encerrar.
- **Controle de fluxo (`break`)** será utilizado para sair do loop quando o usuário desejar.

---

## 2. Código em Python

```python
print("=== Sistema de Votação ===")
print("Candidatos:")
print("1 - Alice")
print("2 - Bob")
print("3 - Carol")
print("0 - Encerrar votação")

votos = {"Alice": 0, "Bob": 0, "Carol": 0}

while True:
    try:
        voto = int(input("Digite o número do seu candidato: "))
    except ValueError:
        print("Entrada inválida. Digite um número.")
        continue

    if voto == 0:
        print("Votação encerrada.")
        break
    elif voto == 1:
        votos["Alice"] += 1
    elif voto == 2:
        votos["Bob"] += 1
    elif voto == 3:
        votos["Carol"] += 1
    else:
        print("Candidato inválido. Tente novamente.")

# Exibir resultado
print("\n=== Resultado da Votação ===")
for candidato, total in votos.items():
    print(f"{candidato}: {total} voto(s)")

# Determinar vencedor
vencedor = max(votos, key=votos.get)
print(f"\nVencedor: {vencedor} 🎉")
```

---

## 3. Funcionamento

### Exemplo de entrada e saída:

```
Digite o número do seu candidato: 1
Digite o número do seu candidato: 2
Digite o número do seu candidato: 1
Digite o número do seu candidato: 0

=== Resultado da Votação ===
Alice: 2 voto(s)
Bob: 1 voto(s)
Carol: 0 voto(s)

Vencedor: Alice 🎉
```

---

## 4. Conclusão

Este exemplo demonstrou o uso combinado das principais estruturas de controle em Python:

- **Condicionais** para verificar o voto e validar a entrada.
- **Laço `while`** para repetir o processo de votação.
- **`break`** para encerrar o loop com base em condição.
- **Funções embutidas como `max()`** para encontrar o vencedor com base nos votos.

Essas estruturas são fundamentais na lógica de qualquer linguagem de programação e aparecem com frequência no desenvolvimento de sistemas interativos.
