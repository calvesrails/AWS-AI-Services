Como primeiro passo, precisamos criar um **Dataset Group** para utilizarmos os arquivos disponíveis na pasta `Amazon Personalize/utils`.

Um **Dataset Group** é um contêiner de recursos do Amazon Personalize. Ele reúne os datasets, recomendações de domínio e recursos personalizados que serão utilizados ao longo do projeto.

### 01 - Criando o Dataset Group

Na página inicial do Amazon Personalize, podemos encontrar a opção para criação do nosso grupo.

![image](/Amazon%20Personalize/movie_recomendation_project/images/dataset-01.png)

### 02 - Definindo nome e domínio

Para criar o grupo, devemos informar o nome desejado e selecionar o domínio.  
No meu caso de uso, irei selecionar a opção **Custom resources**, pois quero montar uma recomendação personalizada.

![image](/Amazon%20Personalize/movie_recomendation_project/images/dataset-02.png)

### 03 - Criando um dataset

Depois disso, podemos clicar em **Create dataset**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/dataset-03.png)

No **overview** do nosso grupo, será possível adicionar os datasets necessários. Teremos as seguintes opções:

- **Items interactions dataset**
- **Users dataset**
- **Items dataset**

Esses três datasets serão utilizados para gerar as nossas recomendações.

### 04 - Criando o Items interactions dataset

Aqui iremos adicionar os dados das interações dos usuários com os itens.

Devemos definir o nome do dataset e criar um novo schema na opção **Create a new schema**.

Um **schema** é a estrutura que define como os dados devem ser organizados, incluindo nomes de colunas, tipos de dados e regras de validação. Ele é importante para garantir que o Amazon Personalize consiga interpretar corretamente as informações importadas.

Por isso, precisamos verificar se o schema corresponde ao formato do nosso arquivo. No nosso caso, será necessário ajustar o schema para incluir a coluna **RATING**, que existe no dataset e será usada como parte das interações.

![image](/Amazon%20Personalize/movie_recomendation_project/images/dataset-04.png)

### 05 - Configurando o import job

Em seguida, também configuraremos o **import job** do dataset, preenchendo os seguintes campos:

- **Dataset import job name**
- **Data location**
- **IAM role**

Em **Data location**, devemos informar o caminho do arquivo `Dataset.csv` dentro do bucket S3 que configuramos anteriormente.

Neste ponto, é muito importante já ter familiaridade com configuração de **bucket**, **IAM role**, **IAM user** e **IAM group**, pois erros de permissão são comuns nessa etapa. Caso você ainda não tenha prática com isso, vale a pena aprender esses conceitos antes de continuar.

![image](/Amazon%20Personalize/movie_recomendation_project/images/dataset-05.png)

Por fim, clique em **Start import** e o nosso primeiro dataset estará em processo de importação.