# projeto-chat-bot-elay


### 📂 Estrutura de Diretórios no IntelliJ

```
📦 chatbot
 ┣ 📂 src
 ┃ ┣ 📂 main
 ┃ ┃ ┣ 📂 java
 ┃ ┃ ┃ ┣ 📂 com.chatbot
 ┃ ┃ ┃ ┃ ┣ 📂 controller        # Lida com as requisições do frontend
 ┃ ┃ ┃ ┃ ┃ ┣ ChatbotController.java
 ┃ ┃ ┃ ┃ ┣ 📂 model             # Classes que representam a estrutura de dados
 ┃ ┃ ┃ ┃ ┃ ┣ Mensagem.java
 ┃ ┃ ┃ ┃ ┣ 📂 repository        # Comunicação com o banco de dados MySQL
 ┃ ┃ ┃ ┃ ┃ ┣ ChatbotRepository.java
 ┃ ┃ ┃ ┃ ┣ 📂 service           # Lógica de negócio e integração com OpenAI
 ┃ ┃ ┃ ┃ ┃ ┣ ChatbotService.java
 ┃ ┃ ┃ ┣ Application.java       # Classe principal (Spring Boot)
 ┃ ┃ ┣ 📂 resources
 ┃ ┃ ┃ ┣ 📂 templates           # Arquivos HTML para o frontend
 ┃ ┃ ┃ ┃ ┣ index.html
 ┃ ┃ ┃ ┣ 📂 static
 ┃ ┃ ┃ ┃ ┣ style.css            # Estilos da página
 ┃ ┃ ┃ ┣ application.properties # Configuração do banco de dados
 ┣ 📂 sql
 ┃ ┣ chatbot.sql                # Script para criação das tabelas no MySQL
 ┣ 📄 pom.xml                    # Dependências do projeto (Maven)
```

---

### 🚀 Tecnologias utilizadas:
- **Java** → Para o backend.
- **MySQL** → Para armazenar as perguntas e respostas.
- **HTML + CSS + JavaScript (AJAX/fetch API)** → Para a interface gráfica.
- **JPA/Hibernate** → Para interagir com o banco de dados.
- **OpenAI API (Opcional)** → Para respostas quando não houver no banco.

---

### 📌 Fluxo de Funcionamento:

1. O **frontend (HTML + JavaScript)** envia uma pergunta para o backend via **AJAX/fetch**.
2. O **ChatbotController** recebe a pergunta e chama o **ChatbotService**.
3. O **ChatbotService** verifica se a entrada já existe no **banco MySQL** via **ChatbotRepository**.
4. **Se a pergunta existir** → Retorna a resposta salva no banco.
5. **Se não existir** → Consulta a OpenAI, recebe a resposta e salva no banco.
6. Retorna a resposta para o frontend, exibindo para o usuário.

