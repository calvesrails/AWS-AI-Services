Vamos começar a criar o nosso treinamento, que no Amazon Personalize é chamado de **Solution**.

As **Solutions** no Amazon Personalize são recursos que armazenam a configuração do treinamento e os modelos gerados a partir dela, chamados de **Solution Versions**. Elas definem qual receita (*recipe*) e quais parâmetros serão utilizados para analisar os dados e gerar recomendações personalizadas.

Em resumo, a *Solution* é a base do treinamento do seu modelo dentro do Amazon Personalize.

## Principais características das Solutions

### Treinamento de modelos

Uma *Solution* é criada a partir da escolha de uma **recipe**, ou seja, um algoritmo pré-configurado do Amazon Personalize. Essa receita será treinada com os dados que adicionamos anteriormente aos nossos datasets.

### Versões da solução

Sempre que treinamos uma solução, o Amazon Personalize gera uma **Solution Version**.
Se o treinamento for executado novamente com novos dados ou novas configurações, uma nova versão será criada. Isso permite comparar resultados e acompanhar a evolução do modelo.

### Recommenders vs. Solutions

As **Solutions** oferecem uma configuração mais manual e mais flexível do treinamento.
Já os **Recommenders** são opções mais rápidas e otimizadas para casos de uso comuns, como recomendações automáticas de produtos ou conteúdos, exigindo menos configuração.

### Uso prático

Depois de treinada, a solução poderá ser utilizada para gerar recomendações em tempo real ou em lote (*batch*), normalmente por meio de campanhas.

---

## 01 - Criando a nossa Solution

Vamos começar criando a nossa **Solution** dentro do **Dataset Group** que configuramos anteriormente.

![image](/Amazon%20Personalize/movie_recomendation_project/images/solutions-01.png)

---

## 02 - Especificando os detalhes da Solution

Agora precisamos informar alguns detalhes da nossa solução, como:

- **Solution name**
- **Solution type**
- **Recipe**

![image](/Amazon%20Personalize/movie_recomendation_project/images/solutions-02.png)

### Solution type

Aqui escolhemos qual tipo de problema o modelo irá resolver.

#### 1. Item recommendation

Cria uma solução voltada para recomendar itens aos usuários.

Exemplos:
- recomendar filmes
- recomendar produtos
- recomendar músicas
- recomendar livros

Esse é o tipo ideal no nosso caso, já que queremos montar um sistema de recomendação de filmes.

#### 2. Action recommendation

Cria uma solução para prever qual ação o usuário provavelmente irá executar.

Exemplos:
- clicar em um botão
- abrir uma funcionalidade
- iniciar uma assinatura
- responder a uma oferta

Essa opção pode aparecer desabilitada caso você não tenha configurado um **Actions dataset**.

#### 3. User segmentation

Cria uma solução para agrupar usuários em segmentos com base em comportamento ou dados de perfil.

Exemplos:
- usuários que gostam de ação
- usuários que preferem comédia
- usuários com alto engajamento
- usuários com perfil de consumo parecido

Essa opção é útil quando o objetivo não é recomendar diretamente um item, mas sim classificar ou segmentar usuários.

### Recipe

A opção **Recipe** define qual algoritmo pré-configurado será utilizado no treinamento.

Ou seja:

- o **Solution type** define **o que você quer fazer**
- a **Recipe** define **como o Amazon Personalize fará isso**

Dependendo do tipo escolhido, o serviço exibirá as receitas compatíveis.
No nosso caso, utilizaremos a receita **`user-personalization-v2`**.

---

## 03 - Training configuration

Essa etapa serve para personalizar o treinamento da solução de acordo com a necessidade do projeto.

É importante lembrar que **essas configurações não podem ser alteradas depois que a solução for criada**, então vale a pena revisar tudo com atenção antes de continuar.

No nosso caso, não faremos muitas alterações. Vamos apenas **desmarcar a opção de Automatic training**.

### Automatic training

Essa opção controla como o Amazon Personalize irá treinar novamente a solução quando houver novos dados.

A ideia é permitir que o modelo continue aprendendo com interações mais recentes dos usuários, sem depender totalmente de treinamento manual.

Como neste projeto queremos entender o processo passo a passo, iremos deixar essa opção desativada.

![image](/Amazon%20Personalize/movie_recomendation_project/images/solutions-03.png)

---

Depois disso, no **overview** da nossa solução, podemos revisar as informações e clicar em **Create solution**.

Após iniciar a criação, aparecerá uma mensagem semelhante a esta:

**Creating solution version (version ID: 162e4cb3). This can take anywhere from 20 minutes to 48 hours to complete.**

Ou seja, agora precisamos aguardar a conclusão do treinamento para continuar na próxima seção.