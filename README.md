# Chatbot de Atendimento ao Cliente para E-commerce

Este projeto é um chatbot de atendimento ao cliente desenvolvido para um e-commerce, utilizando a API da OpenAI para fornecer respostas inteligentes e contextuais às perguntas dos usuários. O chatbot é capaz de responder a questões relacionadas a produtos, promoções, políticas de frete e outras informações relevantes ao e-commerce.

## Descrição Geral

O chatbot foi desenvolvido como parte do curso [Desenvolva um Chatbot de IA com GPT e Java](https://cursos.alura.com.br/course/gpt-java-desenvolva-chatbot-ia) da Alura. O objetivo é melhorar o atendimento ao cliente, fornecendo respostas imediatas e precisas, além de automatizar processos frequentes, como o cálculo de frete.

## Funcionalidades

- **Interação Natural com o Usuário**: Utiliza o modelo GPT da OpenAI para entender e responder às perguntas dos clientes de forma natural e contextualizada.
- **Cálculo de Frete**: Integração com um serviço de cálculo de frete, permitindo ao chatbot fornecer informações precisas sobre custos de envio.
- **Gerenciamento de Conversa**: Mantém o histórico de mensagens para proporcionar uma experiência de conversa contínua.
- **Limpeza de Histórico**: Possibilidade de limpar a conversa atual para iniciar um novo atendimento.

## Tecnologias Utilizadas

- **Java**: Linguagem de programação principal do projeto.
- **Spring Framework**: Utilizado para construção do aplicativo, gerenciamento de dependências e configuração dos componentes.
- **OpenAI API**: Serviço externo para processamento de linguagem natural.
- **jtokkit**: Biblioteca para contagem de tokens nas mensagens, auxiliando no controle de custos e conformidade com limites da API.
- **Jackson**: Biblioteca para serialização e desserialização de objetos JSON.
- **Biblioteca OpenAI Java (com.theokanning.openai)**: Cliente Java para interagir com a API da OpenAI de forma simplificada.

## Pré-requisitos

- **Java 17** ou superior
- **Maven**
- **Conta na OpenAI** com acesso à API e chave de API válida

## Configuração do Projeto

1. **Clonar o repositório:**

   ```bash
   git clone https://github.com/lucaslap/chatbot-java.git
   ```

2. **Navegar até o diretório do projeto:**

   ```bash
   cd chatbot-java
   ```

3. **Configurar as variáveis de ambiente:**

   No arquivo `application.properties` em `src/main/resources` com o seguinte conteúdo:

   ```properties
   app.openai.api.key=SUA_CHAVE_API_OPENAI
   app.openai.assistant.id=SEU_ASSISTANT_ID
   ```

   Substitua `SUA_CHAVE_API_OPENAI` pela sua chave de API da OpenAI e `SEU_ASSISTANT_ID` pelo ID do assistente(thread) configurado na OpenAI.

## Executando o Projeto

1. **Compilar o projeto:**

   ```bash
   mvn clean install
   ```

2. **Executar a aplicação:**

   ```bash
   mvn spring-boot:run
   ```

3. **Acessar a aplicação:**

   Abra o navegador e acesse `http://localhost:8080/chat` para interagir com o chatbot.

## Estrutura do Projeto

- **Controller:**
  - `ChatController`: Controlador responsável por gerenciar as requisições HTTP relacionadas ao chatbot.

- **Service:**
  - `ChatbotService`: Serviço que coordena as interações entre o usuário e a API da OpenAI.

- **Infra/OpenAI:**
  - `OpenAIClient`: Classe que lida diretamente com a API da OpenAI.
  - `ContadorDeTokens`: Classe para contar o número de tokens em uma mensagem.
  - `DadosRequisicaoChatCompletion`: Record que encapsula os dados necessários para a requisição.

- **Domain:**
  - `CalculadorDeFrete`: Serviço responsável pelo cálculo de frete quando solicitado pelo chatbot.

- **Web/DTO:**
  - `PerguntaDto`: Objeto de transferência de dados que encapsula a pergunta enviada pelo usuário.

---
