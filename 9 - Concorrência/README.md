
# Desafio 09 - Concorrência

## Linguagem Utilizada: Python

Neste desafio, exploramos o conceito de **concorrência** com **threads** em Python. A concorrência permite que múltiplas tarefas sejam executadas ao mesmo tempo, o que pode melhorar a performance em programas que realizam operações simultâneas, como I/O, redes e simulações.

---

## 1. Conceitos Envolvidos

| Conceito | Descrição |
|----------|-----------|
| **Thread** | Unidade leve de execução. Compartilha memória com outras threads do mesmo processo. |
| **Processo** | Instância de um programa em execução. Possui memória isolada. |
| **Concorrência** | Capacidade de alternar entre tarefas em progresso. |

---

## 2. Exemplo de Concorrência com Threads

Vamos simular dois sensores trabalhando em paralelo com threads.

```python
import threading
import time

def sensor_temperatura():
    for i in range(5):
        print(f"[Temperatura] Leitura {i + 1}: 23.{i} °C")
        time.sleep(1)

def sensor_umidade():
    for i in range(5):
        print(f"[Umidade] Leitura {i + 1}: {50 + i}%")
        time.sleep(1.5)

# Criando as threads
thread1 = threading.Thread(target=sensor_temperatura)
thread2 = threading.Thread(target=sensor_umidade)

# Iniciando as threads
thread1.start()
thread2.start()

# Esperando ambas finalizarem
thread1.join()
thread2.join()

print("Leituras finalizadas.")
```

---

## 3. Saída Esperada (pode variar na ordem)

```
[Temperatura] Leitura 1: 23.0 °C
[Umidade] Leitura 1: 50%
[Temperatura] Leitura 2: 23.1 °C
[Temperatura] Leitura 3: 23.2 °C
[Umidade] Leitura 2: 51%
...
Leituras finalizadas.
```

---

## 4. Comparação: Thread vs Processo

| Aspecto     | Thread                          | Processo                          |
|-------------|----------------------------------|-----------------------------------|
| Memória     | Compartilhada entre threads      | Isolada por processo              |
| Custo       | Mais leve                        | Mais pesado                       |
| Comunicação | Mais simples (mesma memória)     | Mais complexa (IPC)               |

---

## 5. Conclusão

A concorrência com **threads** permite que múltiplas tarefas sejam realizadas "ao mesmo tempo", mesmo em sistemas com um único núcleo, graças à alternância rápida de contexto. Em Python, a biblioteca `threading` fornece uma maneira simples e eficaz de implementar essa paralelização.

Este conceito é essencial em aplicações modernas, como servidores web, interfaces gráficas e sistemas de sensores.
