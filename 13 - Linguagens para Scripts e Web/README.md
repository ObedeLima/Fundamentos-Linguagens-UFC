
# Desafio 13 - Linguagens para Scripts e Web

## Linguagem Utilizada: Python

Neste desafio, criamos um **script Python** para automatizar uma tarefa simples: **verificar o status de um site** (online/offline) e registrar os resultados em um arquivo.

Esse tipo de automação é comum em tarefas de monitoramento, scraping ou manutenção de sistemas web.

---

## 1. Descrição da Tarefa

O script:

- Recebe uma lista de URLs.
- Verifica se cada site está online (`status code 200`) ou fora do ar.
- Registra os resultados com data/hora em um arquivo `log.txt`.

---

## 2. Código do Script

```python
import requests
from datetime import datetime

# Lista de sites para checar
sites = [
    "https://www.google.com",
    "https://www.github.com",
    "https://www.umsitequenaoexiste123.com"
]

def verificar_site(url):
    try:
        resposta = requests.get(url, timeout=5)
        if resposta.status_code == 200:
            return "ONLINE"
        else:
            return f"ERRO {resposta.status_code}"
    except requests.exceptions.RequestException:
        return "OFFLINE"

with open("log.txt", "a") as log:
    for site in sites:
        status = verificar_site(site)
        timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        log.write(f"[{timestamp}] {site} - {status}\n")
        print(f"{site} - {status}")
```

---

## 3. Saída Exemplo

```
https://www.google.com - ONLINE
https://www.github.com - ONLINE
https://www.umsitequenaoexiste123.com - OFFLINE
```

Arquivo `log.txt` atualizado com os registros.

---

## 4. Possíveis Extensões

- Enviar alertas por e-mail quando sites estiverem offline.
- Executar o script periodicamente com `cron` (Linux) ou `Agendador de Tarefas` (Windows).
- Criar uma interface web para visualizar os status em tempo real.

---

## 5. Conclusão

Scripts em Python são extremamente úteis para automatizar tarefas do dia a dia, especialmente no contexto web. Com bibliotecas como `requests`, é possível realizar requisições HTTP de forma simples, tornando Python uma excelente linguagem para scripts e automações.

---

## 6. Referências

- [Documentação Requests](https://docs.python-requests.org/en/latest/)
- [Automatize tarefas com Python - Livro recomendado](https://automatetheboringstuff.com/)
