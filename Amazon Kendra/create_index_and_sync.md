## Criando um índice no Amazon Kendra

Agora vamos começar a criar um **index** no Amazon Kendra.

O **index** é, basicamente, o recurso onde os dados serão armazenados, organizados e disponibilizados para busca. Em outras palavras, é ele que torna o conteúdo pesquisável dentro do Amazon Kendra. Posteriormente, esse índice pode ser utilizado em outros aplicativos ou até servir como base para uma aplicação de busca, permitindo que os usuários pesquisem documentos e tenham uma experiência mais inteligente e eficiente.

---

### 01 - Criação do index

Na página inicial do **Amazon Kendra**, podemos clicar em **Create index**.
O documento utilizado nesta aula será o arquivo `Employee_Onboarding_Guide.pdf`.

Embora o Amazon Kendra permita trabalhar com vários tipos de **data sources**, como esta é uma demonstração com um arquivo PDF, vamos utilizar um **bucket do Amazon S3** como fonte de dados.

![image](/Amazon%20Kendra/images/index-01.png)

Em seguida, adicionamos um nome ao nosso índice e também definimos uma **IAM Role**, que será necessária para a configuração do recurso.

![image](/Amazon%20Kendra/images/index-02.png)

Para este exemplo, podemos seguir apenas com essas configurações iniciais.

Na etapa de capacidade adicional, recomendo utilizar a **Developer Edition** para fins de estudo e teste.

![image](/Amazon%20Kendra/images/index-03.png)

Na seção de **Access control**, também podemos seguir apenas clicando em **Next**.

![image](/Amazon%20Kendra/images/index-04.png)

Depois disso, revise as informações e clique em **Create**.

Em seguida, veremos a mensagem indicando que o índice está sendo criado, o que pode levar alguns instantes.

![image](/Amazon%20Kendra/images/index-05.png)

---

### 02 - Adicionando um data source

Agora vamos clicar em **Add data sources** para vincular o nosso índice a uma fonte de dados, que no nosso caso será o **Amazon S3**.

![image](/Amazon%20Kendra/images/index-06.png)

Podemos ver que existem muitos tipos de **data sources** disponíveis, mas seguiremos com o **bucket S3**.

![image](/Amazon%20Kendra/images/index-07.png)

Em seguida, adicionamos um nome ao nosso **data source** e prosseguimos.

![image](/Amazon%20Kendra/images/index-08.png)

Depois disso, vamos criar uma nova **IAM Role** para permitir a criação e o acesso a esse data source. Para este teste, também podemos continuar sem configurar **VPC**.

![image](/Amazon%20Kendra/images/index-09.png)

Nas configurações de sincronização, adicionamos o local da nossa fonte de dados, que no caso será o bucket S3 contendo o arquivo `Employee_Onboarding_Guide.pdf`.

![image](/Amazon%20Kendra/images/index-10.png)

Na frequência de sincronização, podemos deixar a opção **Run on demand**, já que estamos apenas realizando um teste.

![image](/Amazon%20Kendra/images/index-11.png)

Depois disso, podemos clicar em **Next**.

Na etapa **Set field mappings**, podemos seguir com a configuração padrão.

Em seguida, revise as informações e clique em **Add data source**.

![image](/Amazon%20Kendra/images/index-12.png)

Nosso **data source** será criado, mas ainda não estará sincronizado com o índice. Para isso, basta selecionarmos a opção **Sync now**.

![image](/Amazon%20Kendra/images/index-13.png)

Pronto, agora nosso **index** foi criado e sincronizado com o nosso **data source**.