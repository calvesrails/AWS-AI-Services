## Setup inicial e definição do Event Type

No nosso primeiro passo, vamos iniciar o setup no **Amazon Fraud Detector** e definir o nosso **Event Type**.

O **Event Type** é o tipo de evento que o Amazon Fraud Detector irá analisar. Nele, configuramos a estrutura do evento, incluindo o **nome**, a **entidade responsável pela ação** (como cliente, conta ou lojista) e as **variáveis** que serão enviadas para avaliação, como e-mail, IP, valor da transação, número da conta e dispositivo. Em resumo, é nessa etapa que definimos o “formato” dos eventos que serão usados pelos modelos e detectores para calcular o risco de fraude.

### 01 - Escolhendo o caso de uso

Vamos começar criando um caso de uso para os nossos dados.

Isso pode ser feito clicando em **Explore data models** na página de **Overview**, para explorarmos os modelos de dados disponíveis para o nosso cenário.

![image](/Amazon%20Fraud%20Detector/images/setup-01.png)

Na seção **Business use case**, temos vários casos de uso. No nosso exemplo, selecionaremos **Online transaction fraud**.

![image](/Amazon%20Fraud%20Detector/images/setup-02.png)

Depois disso, podemos clicar em **Create event type**.

### 02 - Create event type

Nessa etapa, iremos criar o nosso **Event Type**.

Podemos definir o nome do evento e também criar uma entidade para ele.

![image](/Amazon%20Fraud%20Detector/images/setup-03.png)

![image](/Amazon%20Fraud%20Detector/images/setup-04.png)

### Event variables

Aqui definimos as variáveis que fazem parte do nosso evento, como **ID**, **timestamp**, **account_id** e outros atributos relevantes.

Neste exemplo, vamos criar essas variáveis a partir do nosso conjunto de dados, utilizando a opção **Select variables from a training dataset**.

Também precisaremos definir a **IAM Role** e o local (**bucket**) onde está armazenado o arquivo `test_dataset.csv`. Se os conceitos de **IAM Role** e **S3 bucket** ainda forem novos para você, vale a pena estudar esses serviços antes de avançar nesta etapa.

![image](/Amazon%20Fraud%20Detector/images/setup-05.png)

O nosso conjunto de dados contém várias variáveis interessantes, como o **timestamp do evento**, **categoria**, **número da conta** e outras informações úteis para a análise.

![image](/Amazon%20Fraud%20Detector/images/setup-06.png)

Após a importação do nosso conjunto de dados, aparecerá uma seção para definirmos os tipos das variáveis que iremos utilizar. No meu caso, adicionei os seguintes tipos:

![image](/Amazon%20Fraud%20Detector/images/setup-07.png)

![image](/Amazon%20Fraud%20Detector/images/setup-08.png)

### Labels

Agora podemos definir os **labels**, que serão usados para categorizar os eventos como **fraudulentos** ou **legítimos** durante o treinamento do modelo de machine learning.

Como a nossa coluna `EVENT_LABEL` informa se a transação foi **fraudulenta** (`1`) ou **legítima** (`0`), podemos usar esses valores para criar os rótulos, definindo:

- `1` como **fraudulenta**
- `0` como **legítima**

![image](/Amazon%20Fraud%20Detector/images/setup-09.png)

![image](/Amazon%20Fraud%20Detector/images/setup-10.png)

Por fim, podemos clicar em **Create event type** e seguir para a construção do nosso modelo.