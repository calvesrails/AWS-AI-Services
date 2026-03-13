Nesta seção, iremos falar sobre o **Amazon Personalize**, um serviço de aprendizado de máquina da AWS que utiliza os seus dados para gerar recomendações personalizadas para os usuários da sua aplicação.

O Amazon Personalize trabalha, principalmente, com **dados de interações entre usuários e itens**. Em outras palavras, ele analisa como os usuários se comportam em relação aos itens disponíveis em sua aplicação ou página, como filmes, produtos, músicas, livros ou qualquer outro conteúdo. A partir dessas interações, o serviço consegue identificar padrões de interesse e gerar recomendações mais relevantes para cada usuário.

Esses dados de interação podem ser enviados de duas formas principais:

### Interações em massa

As interações em massa são dados históricos enviados em lote. Normalmente, isso acontece por meio de arquivos contendo registros antigos de ações dos usuários, como avaliações, cliques, visualizações, compras ou curtidas. Esse tipo de envio é muito útil para iniciar o treinamento do modelo com uma base de dados já existente.

### Eventos em tempo real

Os eventos em tempo real são interações enviadas à medida que acontecem dentro da aplicação. Por exemplo: quando um usuário clica em um produto, assiste a um filme ou adiciona um item ao carrinho, essa ação pode ser registrada imediatamente no Amazon Personalize. Isso permite que as recomendações sejam atualizadas de forma mais dinâmica e próxima do comportamento atual do usuário.

## Casos de uso comuns do Amazon Personalize

Alguns casos de uso comuns do Amazon Personalize são:

- Personalizar um aplicativo de streaming de vídeos
- Adicionar recomendações de produtos em um aplicativo de e-commerce
- Sugerir a melhor ação a ser executada em sua aplicação
- Criar e-mails personalizados
- Criar campanhas de marketing para um público-alvo específico
- Personalizar resultados de busca

## Exemplo prático

Neste exemplo, iremos criar um sistema de recomendação de filmes. Para isso, utilizaremos alguns dados de usuários que avaliaram filmes. Os filmes serão os nossos **itens**, e as avaliações feitas pelos usuários serão as nossas **interações**.

### 01 - Visualizando o dataset de interações

Primeiramente, podemos analisar o dataset que será utilizado para treinar o modelo.

Nele, temos os IDs dos usuários, os IDs dos itens (filmes), as notas atribuídas e os *timestamps* das interações.

![image](/Amazon%20Personalize/images/recomendation-01.png)

### 02 - Visualizando os dados dos usuários

Também temos os dados dos clientes, onde podemos visualizar os IDs, nomes e idades dos usuários.

![image](/Amazon%20Personalize/images/recomendation-02.png)

### 03 - Visualizando os dados dos itens

Além disso, também temos os dados dos nossos itens, que neste caso são os filmes. Nesse arquivo, teremos os IDs dos filmes, os nomes e o ano de lançamento.

![image](/Amazon%20Personalize/images/recomendation-03.png)

### 04 - Enviando os arquivos para o S3

Agora, precisaremos criar um bucket no Amazon S3 e adicionar os três arquivos a ele:

- `Amazon Personalize/utils/Users_Data.csv`
- `Amazon Personalize/utils/Movies_Data_with_Year.csv`
- `Amazon Personalize/utils/Dataset.csv`

![image](/Amazon%20Personalize/images/recomendation-04.png)

### 05 - Concedendo permissões ao Amazon Personalize

Em seguida, precisamos conceder permissões para que o Amazon Personalize consiga acessar o bucket criado. Para isso, será necessário criar uma nova policy de acesso.

![image](/Amazon%20Personalize/images/recomendation-05.png)

Podemos utilizar o arquivo `Amazon Personalize/utils/S3Policy.txt` para adicionar essa permissão.

![image](/Amazon%20Personalize/images/recomendation-06.png)

Lembre-se de ajustar o `bucket-name` para o nome definido no seu bucket. Exemplo:

```json
"Resource": [
    "arn:aws:s3:::movie-recomendation-dataset",
    "arn:aws:s3:::movie-recomendation-dataset/*"
]