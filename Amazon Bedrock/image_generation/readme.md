Nesta seção, veremos como realizar uma chamada (*invoke*) de um modelo de geração de imagens, o **Titan Image Generator G1**.

Praticamente todos os modelos disponíveis no Amazon Bedrock possuem documentação com exemplos de uso da operação **InvokeModel**.

O **InvokeModel** é a operação utilizada para enviar uma entrada para um modelo e receber sua resposta. Em outras palavras, é a forma de realizar uma inferência diretamente em um modelo hospedado no Amazon Bedrock.

No exemplo de **InvokeModel** do Titan, podemos copiar o código disponibilizado na documentação e testar uma nova chamada ao modelo. Caso você não encontre esse exemplo diretamente na AWS, também pode utilizar o código disponível no arquivo `Bedrock/image_generation/titan_image_generation.py`.

![image](/Bedrock/image_generation/images/titan-image-01.png)

Neste exemplo, iremos solicitar a geração de uma imagem estilizada de um robô steampunk antigo e fofo. No entanto, você pode alterar o *prompt* livremente para testar outros estilos e resultados.

Lembre-se sempre de acompanhar o código com atenção e entender o que cada parte está fazendo.

Ao executar o código, podemos ver que tudo ocorreu como planejado, sem erros.

![image](/Bedrock/image_generation/images/titan-image-02.png)

Nosso script criou uma pasta local onde foi armazenada a saída gerada, ou seja, a imagem do robô.

![image](/Bedrock/image_generation/images/titan-image-03.png)
![image](/Bedrock/image_generation/images/titan-image-04.png)

Também podemos modificar o nosso *input* para gerar outros tipos de imagem. Neste novo teste, tentei gerar uma imagem em estilo cartoon de um bebê fofo.

![image](/Bedrock/image_generation/images/titan-image-05.png)
![image](/Bedrock/image_generation/images/titan-image-06.png)

Vale destacar que alguns *prompts* podem ser bloqueados automaticamente pelos filtros de segurança do modelo, de acordo com as políticas de uso responsável da AWS. Caso isso aconteça, o ideal é ajustar a descrição da imagem para algo mais neutro e tentar novamente.