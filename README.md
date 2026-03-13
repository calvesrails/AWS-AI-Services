# AWS-AI-Services

Repositório de estudos sobre serviços de Inteligência Artificial da AWS, com foco na exploração de recursos como Amazon Bedrock, Amazon Personalize, Amazon Comprehend e outros, abordando casos de uso, integrações e aplicações práticas.

---

Repository for studying AWS Artificial Intelligence services, exploring resources such as Amazon Bedrock, Amazon Personalize, Amazon Comprehend, and others, with a focus on use cases, integrations, and practical applications.

---

## Setup do Ambiente

### 1. Instalar o SDK do Python

Utilizaremos o SDK do Python para interagir com os serviços da AWS: `pip install boto3`

### 2. Instalar a AWS CLI

Também será necessário instalar a AWS CLI para interagir com os serviços da AWS via linha de comando: `pip install awscli`

### 3. Configurar a AWS CLI

No terminal, execute: `aws configure`

Em seguida, serão solicitadas algumas informações de configuração.

#### AWS Access Key ID

Será solicitado um **Access Key ID**, que corresponde ao identificador gerado para o seu usuário IAM com as permissões corretas de acesso.

![IAM User](/images/user-01.png)
![Access Key Step 1](/images/user-03.png)
![Access Key Step 2](/images/user-04.png)

Após copiar o **Access Key ID**, cole-o no terminal.

![Terminal Configuration](/images/user-05.png)

#### AWS Secret Access Key

Depois, será solicitada a **Secret Access Key**. Copie essa chave e cole-a no terminal também.

### 4. Região padrão

Utilizarei a região padrão `us-east-1`.

Essa região será usada para acessar os modelos e serviços necessários.

### 5. Formato de saída padrão

Como formato de saída padrão, utilizarei `json`.