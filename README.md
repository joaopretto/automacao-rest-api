# 🚀 Automação de Testes de API - RestAssured & Cucumber

Este projeto consiste em uma suíte de testes automatizados para validação de **API REST**, utilizando **Java**, **RestAssured** e **Cucumber**. O projeto foi arquitetado focando em escalabilidade, reutilização de código e gestão inteligente de massa de dados.

# 🛠 Tecnologias Utilizadas
**Linguagem: Java (JDK 17 ou superior recomendado)**

**Gerenciador de Dependências: Maven
**Client HTTP: RestAssured
**BDD Framework: Cucumber (Java & JUnit)
**Runner: JUnit 4
**Processamento JSON: Jackson Databind
**Asserções: JUnit Assertions / Hamcrest

# 📂 Estrutura do Projeto
O projeto segue a convenção de pastas do Maven e boas práticas de QA:

```bash
src/test
├── java/br/desafio
│   ├── config       # Configurações globais (BaseURL, Specs do RestAssured)
│   │   ├── ApiConfig.java # Specs de Request (Com e Sem Token)
│   │   ├── AuthClient.java  # Autenticador de login 
│   │   └── BaseClient.java  # Wrapper dos verbos HTTP (GET, POST, etc.)
│   ├── hooks       
│   │   └── SetupHook.java # Definição de um Before definindo a URL base.
│   ├── model       
│   │   └── LoginPayload.java # Classe armazenamento de dados de login
│   ├── runner       
│   │   └── RunCucumberTest.java # Classe executora do JUnit
│   ├── steps        # Implementação dos passos (Glue Code)
│   └── utils        # Utilitários do framework
│       ├── FilterLogging.java # Gerenciador de log após execução
│       ├── TokenManager.java # Gerenciador Singleton de Autenticação
│       └── TestContext.java  # Gestão de estado entre Steps
└── resources
    └── features     # Arquivos .feature (Gherkin)
```

## 🚀 1. Instalação e Executar
  **APPS NECESSARIOS**
  Intellij - Recomendado

  **-Tecnologias necessarias.
    * **Java JDK 21**
    * **Maven Apache (Para execução do comando "mvn")**

  # Clonar o projeto
  ```bash
  git clone https://gitlab.com/JoaoPrettoo/automacao_sicredi_api.git
  ```

  Precisa ter o JDK instalado na maquina segue o link para download caso não tenha: "https://www.oracle.com/br/java/technologies/downloads/#java21"
  
  E também precisa ter o Apache Maven segue o link para download caso não tenha: "https://maven.apache.org/download.cgi"
  
  Ambos precisam estar configurado na sua variável de ambiente
  
  **JAVA_HOME**
  
  **MAVEN_HOME**

  ## Como Executar

  Certifique-se de ter o Java e o Maven instalados e configurados nas variáveis de ambiente.
  
  No terminal, na raiz do projeto rodar:

  ```bash
  mvn clean test
  ```
  
  Para garantir que o relatório seja gerado mesmo se algum teste falhar:
  ```bash
  mvn test -Dmaven.test.failure.ignore=true
  ```
  O relatorio é gerado após a execução na pasta "target/cucumber-reports/report.html"

  ## Observações:

  Os testes é composto com um total de 8 cenários, cada uma das features possui 1 cenário de risco com sucesso, e outro cenário de risco com falha.
  
