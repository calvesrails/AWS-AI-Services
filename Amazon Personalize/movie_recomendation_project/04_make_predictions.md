## Criando uma Campaign para gerar previsões

Agora vamos criar uma **Campaign** para finalmente disponibilizarmos as nossas previsões.

No Amazon Personalize, uma **Campaign** é o recurso que você cria para implantar uma versão específica da sua solução, ou seja, o modelo treinado, e torná-la disponível para fornecer recomendações em tempo real.

Se a **Solution** é o projeto e a **Solution Version** é o modelo já treinado, a **Campaign** funciona como o “servidor” ou endpoint de API que ficará ativo para receber as requisições do seu site ou aplicativo.

### Principais características de uma Campaign

- **Provisionamento de recursos:** ao criar uma campanha, você define a taxa mínima de transferência desejada, geralmente em transações por segundo (**TPS**). O Amazon Personalize pode escalar automaticamente conforme a demanda aumenta.
- **Acesso via API:** a campanha gera um **ARN (Amazon Resource Name)** único. Esse ARN é utilizado em chamadas de API, como `GetRecommendations`, para obter recomendações personalizadas para seus usuários.
- **Custo:** diferente da Solution, que cobra pelo treinamento, a Campaign possui custo baseado no tempo em que o endpoint fica ativo e na quantidade de recomendações geradas.
- **Atualização:** você pode atualizar uma campanha existente para utilizar uma nova **Solution Version**, sem precisar alterar o código da sua aplicação.

![image](/Amazon%20Personalize/movie_recomendation_project/images/prediction-01.png)

### 01 - Create new campaign

#### Campaign details

Essa seção reúne as informações principais da campanha que será criada.

Ela serve para definir:

- o nome da campanha
- qual solução será utilizada
- como a campanha irá se comportar quando surgirem novas versões do modelo

Aqui, selecionaremos a **Solution** que criamos anteriormente e marcaremos a opção **Automatically use the latest solution version**.

Depois disso, podemos clicar em **Create campaign**.
A criação da campanha pode demorar alguns minutos. Assim que ela estiver pronta, poderemos seguir para a próxima etapa.

![image](/Amazon%20Personalize/movie_recomendation_project/images/prediction-02.png)

### 02 - Testando os resultados da Campaign

Antes de utilizar a Campaign em nosso aplicativo, podemos testá-la diretamente para entender como ela funciona e verificar quais recomendações estão sendo geradas para um usuário específico.

![image](/Amazon%20Personalize/movie_recomendation_project/images/prediction-03.png)

Podemos ver que algumas recomendações foram geradas e ordenadas por **score**. Essas seriam, portanto, recomendações relevantes para o usuário de exemplo com **ID 31**.

![image](/Amazon%20Personalize/movie_recomendation_project/images/prediction-04.png)

Também podemos enviar algum **context** para verificar se a Campaign está gerando resultados diferentes de acordo com as informações adicionais fornecidas.

![image](/Amazon%20Personalize/movie_recomendation_project/images/prediction-05.png)