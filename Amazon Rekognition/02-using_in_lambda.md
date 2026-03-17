## Integração do Amazon Rekognition com AWS Lambda

Agora vamos fazer uma demonstração de como o **Amazon Rekognition** pode ser integrado com uma função **AWS Lambda** para utilizarmos sua API de forma prática.

Essa parte não costuma cair no exame, mas é uma ótima forma de consolidar o aprendizado e entender como os serviços da AWS podem trabalhar juntos em um cenário real.

### O que é o AWS Lambda?

O **AWS Lambda** é um serviço de computação sem servidor (*serverless*) da AWS que permite executar código sob demanda, sem a necessidade de provisionar ou gerenciar servidores.

Com ele, basta enviar o código da sua função, definir as permissões necessárias e executar a lógica quando quiser, seja manualmente, por eventos ou por integração com outros serviços da AWS.

Neste exemplo, usaremos o Lambda para chamar a API do **Amazon Rekognition** e detectar rótulos em uma imagem armazenada no **Amazon S3**.

---

## 01 - Criando a função Lambda

Vamos começar acessando a página do **AWS Lambda** e criando uma nova função.

Nessa etapa, podemos definir apenas o nome da função e a linguagem que será utilizada. No nosso caso, vamos usar **Python**.

![image](/Amazon%20Rekognition/images/rekognition-04.png)

Após criar a função, podemos adicionar o código disponível em `Amazon Rekognition/code.py`. Esse código será responsável por detectar os rótulos de uma imagem armazenada no nosso bucket S3.

Lembre-se de pausar e observar o código com atenção para entender melhor o que ele faz.

![image](/Amazon%20Rekognition/images/rekognition-05.png)

No código, precisamos informar os dados do nosso bucket S3. Para isso, você pode criar um bucket e adicionar uma imagem qualquer. Eu irei seguir com a imagem do churrasco, só que com um churrasco bem maior, huuum.

![image](/Amazon%20Rekognition/images/barbecue.jpg)

Depois disso, adicionei no código as informações do nome do bucket e o caminho da imagem.

![image](/Amazon%20Rekognition/images/rekognition-06.png)

Se ocorrer algum erro, provavelmente ele estará relacionado ao **caminho da imagem** ou à **demora na propagação das permissões**.

Se o problema for o caminho, tente passar somente o nome do arquivo no bucket, por exemplo:

` s3_key = event.get('s3_key', 'barbecue.jpg') `

---

## 02 - Definindo permissões

Antes de executarmos a função, precisamos configurar as permissões para que o **Lambda** consiga acessar o **Amazon Rekognition** e o **bucket S3**.

![image](/Amazon%20Rekognition/images/rekognition-07.png)

Podemos ver que, inicialmente, na seção **Resource summary**, a role da função possui apenas permissões para logs do **CloudWatch**. No entanto, neste caso também queremos permitir acesso ao **S3** e ao **Rekognition**.

Para isso, podemos clicar na role vinculada à função e adicionar novas policies ao nosso caso de uso.
No meu teste, adicionei as seguintes permissões:

- `AmazonRekognitionFullAccess`
- `AmazonS3FullAccess`

Essas permissões foram usadas apenas para fins de demonstração.

![image](/Amazon%20Rekognition/images/rekognition-08.png)

---

## 03 - Deploy e teste

Agora podemos finalmente realizar o **deploy** da nossa função e deixá-la ativa.

![image](/Amazon%20Rekognition/images/rekognition-09.png)

Com o deploy realizado, vamos testar a função.

Podemos acessar a aba **Test**, definir um nome para o evento de teste e deixar o restante com a configuração padrão. Depois disso, basta clicar no botão **Test**.

![image](/Amazon%20Rekognition/images/rekognition-10.png)

Após a execução, serão exibidos os detalhes do resultado do teste. Formatando a resposta, teremos algo parecido com isso:

![image](/Amazon%20Rekognition/images/rekognition-11.png)

Podemos ver claramente os rótulos identificados e o nível de confiança de cada um deles. É realmente impressionante observar como o serviço consegue reconhecer o contexto visual da imagem com tanta precisão.

Essa integração simples entre Lambda + S3 + Rekognition já mostra bem o poder da AWS para construir aplicações inteligentes e orientadas por eventos.

```json
{
  "statusCode": 200,
  "body": {
    "image": "s3://barbecue-demo/barbecue.jpg",
    "labels": [
      {
        "Name": "Bbq",
        "Confidence": 99.82763671875
      },
      {
        "Name": "Grilling",
        "Confidence": 99.82763671875
      },
      {
        "Name": "People",
        "Confidence": 99.37129974365234
      },
      {
        "Name": "Person",
        "Confidence": 99.37129974365234
      },
      {
        "Name": "Adult",
        "Confidence": 97.94725036621094
      },
      {
        "Name": "Male",
        "Confidence": 97.94725036621094
      },
      {
        "Name": "Man",
        "Confidence": 97.94725036621094
      },
      {
        "Name": "Female",
        "Confidence": 97.62250518798828
      },
      {
        "Name": "Woman",
        "Confidence": 97.62250518798828
      },
      {
        "Name": "Brunch",
        "Confidence": 96.03730773925781
      }
    ]
  }
}