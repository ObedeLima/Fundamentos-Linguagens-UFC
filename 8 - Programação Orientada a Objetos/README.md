
# Desafio 08 - Programação Orientada a Objetos

## Linguagem Utilizada: Python

Neste desafio, criamos uma hierarquia simples de classes utilizando os princípios da **Programação Orientada a Objetos (POO)**. O domínio escolhido é o de **transportes**, com uma superclasse `Transporte` e subclasses como `Carro` e `Bicicleta`.

---

## 1. Conceitos Utilizados

- **Classe**: Define um tipo de objeto.
- **Objeto**: Instância de uma classe.
- **Herança**: Subclasses herdam atributos e métodos da superclasse.
- **Encapsulamento**: Controle de acesso aos atributos e métodos.
- **Polimorfismo**: Capacidade de redefinir comportamentos em subclasses.

---

## 2. Código em Python

```python
class Transporte:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo

    def mover(self):
        print(f"{self.marca} {self.modelo} está se movendo.")

class Carro(Transporte):
    def __init__(self, marca, modelo, portas):
        super().__init__(marca, modelo)
        self.portas = portas

    def mover(self):
        print(f"Carro {self.marca} {self.modelo} com {self.portas} portas está dirigindo.")

class Bicicleta(Transporte):
    def __init__(self, marca, modelo, marchas):
        super().__init__(marca, modelo)
        self.marchas = marchas

    def mover(self):
        print(f"Bicicleta {self.marca} {self.modelo} com {self.marchas} marchas está pedalando.")
```

---

## 3. Exemplo de Uso

```python
carro = Carro("Toyota", "Corolla", 4)
bike = Bicicleta("Caloi", "Elite", 21)

carro.mover()
bike.mover()
```

### Saída:

```
Carro Toyota Corolla com 4 portas está dirigindo.
Bicicleta Caloi Elite com 21 marchas está pedalando.
```

---

## 4. Diagrama da Hierarquia

```
          Transporte
           /     \
        Carro   Bicicleta
```

- `Transporte`: Superclasse com método genérico `mover`.
- `Carro`: Subclasse com comportamento específico de movimentação.
- `Bicicleta`: Subclasse com sua própria implementação de `mover`.

---

## 5. Conclusão

A modelagem orientada a objetos permite representar entidades do mundo real com clareza, favorecendo a reutilização de código e a extensibilidade do sistema. Utilizando herança e polimorfismo, conseguimos criar uma estrutura flexível que facilita manutenção e expansão do projeto.

Este exemplo pode ser facilmente estendido para outros meios de transporte, como ônibus, caminhões ou motos.
