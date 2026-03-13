Aqui iremos criar os datasets de treinamento do nosso modelo.

## 01 - User Dataset

Vamos criar um novo dataset para os nossos dados de usuários. Como o **Items interactions dataset** já está pronto, agora selecionaremos a opção **User dataset**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-01.png)

Assim como fizemos no arquivo `01_create_dataset_group.md`, repetiremos o mesmo processo, verificando se o schema padrão corresponde ao nosso arquivo `Users_Data.csv`.  
No entanto, neste caso, será necessário ajustar o schema para incluir as colunas **name** e **age**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-02.png)

### 01 - 02 - Configurando o import job dos dados de usuários

Agora vamos configurar o job de importação dos dados de usuários. Para isso, definiremos:

- o nome do job
- o local do bucket onde está o arquivo `Users_Data.csv`
- a IAM Role que será utilizada

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-03.png)

## 02 - Item Dataset

Agora vamos criar um novo dataset para os dados dos itens. Como os datasets **Items interactions dataset** e **User dataset** já estão prontos, selecionaremos a opção **Item dataset**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-04.png)

Em seguida, vamos verificar se o schema padrão corresponde ao arquivo `Movies_Data_with_Year.csv`.  
Neste caso, também será necessário ajustá-lo para incluir as colunas **title** e **year**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-05.png)

### 02 - 02 - Configurando o import job dos dados dos itens

Agora vamos configurar o job de importação dos dados dos itens. Para isso, definiremos:

- o nome do job
- o local do bucket onde está o arquivo `Movies_Data_with_Year.csv`
- a IAM Role que será utilizada

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-06.png)

Pronto, agora temos todos os datasets configurados dentro do nosso **Dataset Group**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/training-dataset-07.png)