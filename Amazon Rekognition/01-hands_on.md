Vamos começar acessando o serviço **Amazon Rekognition** e explorando alguns dos exemplos de ferramentas e casos de uso disponíveis.

Na lateral esquerda da página do serviço, podemos visualizar diferentes exemplos prontos e testar os casos de uso utilizando nossas próprias imagens. Além de experimentar as funcionalidades e analisar os resultados, também podemos observar o formato da **request** e da **response**, que é bastante simples e fácil de entender.

![image](/Amazon%20Rekognition/images/rekognition-01.png)

Vamos testar a **detecção de rótulos** com uma imagem nossa e observar os resultados. Para este exemplo, escolhi uma imagem de um churrasco.

![image](/Amazon%20Rekognition/images/rekognition-02.png)

A capacidade de detecção desse serviço é impressionante. Podemos ver que ele conseguiu identificar corretamente que há pessoas cozinhando, alimentos sendo preparados, a presença de uma grelha, o contexto de churrasco e também as pessoas presentes na imagem.

Agora vamos analisar outro exemplo com a mesma imagem, mas desta vez utilizando a ferramenta de **detecção facial**.

![image](/Amazon%20Rekognition/images/rekognition-03.png)

Podemos ver que o resultado também é muito interessante. O serviço reconheceu o rosto da criança e retornou informações como uma **faixa estimada de idade**, além de indicar que ela **não está sorrindo** e **não utiliza óculos**, nem de grau nem de sol.