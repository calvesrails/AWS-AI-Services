## Criando uma Experience no Amazon Kendra

Com o nosso **index** criado e o **data source** sincronizado, agora precisamos criar uma **experience** para que esse índice possa realmente ser utilizado pelos usuários.

No Amazon Kendra, uma **Experience** é a interface de busca que conecta o usuário ao índice criado. Em outras palavras, ela é a camada que permite que pessoas pesquisem, façam perguntas e interajam com os documentos indexados de forma prática. É por meio da experience que transformamos o índice em uma experiência real de consulta.

![image](/Amazon%20Kendra/images/experience-01.png)

### 01 - Create experience

Nesta etapa, podemos definir o nome da nossa **experience**, adicionar o **data source** que criamos na aula passada e também criar uma **IAM Role** para essa experience.

![image](/Amazon%20Kendra/images/experience-02.png)

![image](/Amazon%20Kendra/images/experience-03.png)

O Amazon Kendra exige que você confirme sua identidade para se designar como proprietário da experience. Para isso, basta selecionar o seu nome no diretório do **AWS IAM Identity Center**.

É possível adicionar mais de um proprietário, mas é importante selecionar a si mesmo. Caso contrário, você poderá não ter acesso à experience. Se o seu nome não aparecer na lista, será necessário adicioná-lo como usuário no **AWS IAM Identity Center**.

Se essa parte ainda for avançada para você, recomendo estudar primeiro os conceitos de **IAM** e **IAM Identity Center** antes de continuar, pois esse conhecimento é importante para trabalhar com permissões e segurança na AWS.

Depois disso, podemos apenas selecionar nossa identidade e continuar.

![image](/Amazon%20Kendra/images/experience-04.png)

Em seguida, revisamos as configurações e clicamos em **Create experience**.

---

### 02 - Experience builder

Agora que a nossa experience foi criada, podemos abri-la no **Experience builder**.

![image](/Amazon%20Kendra/images/experience-05.png)

Faça login com o seu usuário do **IAM Identity Center** e então teremos acesso à interface para realizar perguntas e testar a busca.

![image](/Amazon%20Kendra/images/experience-06.png)

Agora, queremos obter algumas informações sobre **integração de funcionários**, que é justamente o tema do nosso arquivo indexado.

![image](/Amazon%20Kendra/images/experience-07.png)

No meu teste, perguntei sobre as formas de entrar em contato, e o Kendra retornou exatamente o trecho do documento em que essas informações são citadas. Isso mostra muito bem o poder da busca inteligente do serviço.

Fique à vontade para explorar, testar novas perguntas e observar como o Amazon Kendra consegue localizar trechos relevantes dentro do conteúdo indexado. Na lateral direita, também temos um menu com opções de ajustes e design da experience.