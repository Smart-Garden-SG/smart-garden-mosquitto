
# 🌿 Smart-Garden Mosquitto 📡

Este projeto faz a integração entre sensores e um banco de dados utilizando MQTT e MySQL. Ele escuta mensagens MQTT e armazena os dados recebidos no banco de dados para posterior análise. 📝🗄️

---

## 📦 Funcionalidades

- **📡 Recebimento de Dados via MQTT**: Escuta mensagens dos sensores conectados.
- **🗄️ Armazenamento no MySQL**: Salva os dados dos sensores em um banco de dados.
- **🕒 Registro de Data e Hora**: Cada dado armazenado inclui a data e hora de recepção.

---

## 🛠️ Tecnologias Utilizadas

- **Paho MQTT**: Cliente MQTT para comunicação.
- **MySQL**: Banco de dados relacional.
- **Python**: Linguagem de programação.

---

## 🚀 Como Rodar o Projeto

1. **Instale as dependências**:

   ```bash
   pip install paho-mqtt mysql-connector-python
   ```

2. **Configure o MySQL**:

   Certifique-se de ter um banco de dados MySQL configurado e ajuste os parâmetros de conexão no `sub.py`:

   ```python
   db_connection = mysql.connector.connect(
       host="localhost",
       user="seu_usuario",
       password="sua_senha",
       database="smart_garden_db"
   )
   ```

3. **Configure o Broker MQTT**:

   ```python
   mqtt_client.connect("localhost", 1883, 60)  # Ajuste o endereço do broker MQTT
   ```

4. **Execute o script**:

   ```bash
   python sub.py
   ```

---

## 📝 Explicação do Código

- **on_message**: Função chamada quando uma mensagem é recebida.
  - Processa o payload em JSON.
  - Extrai o `DEVICE_ID` do tópico.
  - Insere os dados no banco de dados.

---

## 📂 Estrutura do Projeto

```
smart-garden-mosquitto/
│-- sub.py
```

---

🌱 **Happy Gardening!** 🌿
