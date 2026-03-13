Nesta seção, veremos como realizar uma chamada (*invoke*) de um modelo no Amazon Bedrock. Para isso, utilizaremos um modelo da própria AWS: o **Titan Embeddings Text**.

Esse modelo é utilizado para transformar textos em **embeddings**, ou seja, em representações numéricas vetoriais. Esses vetores permitem que aplicações comparem similaridade entre textos, realizem buscas semânticas, recomendações, classificação e outras tarefas relacionadas a NLP.

Praticamente todos os modelos disponíveis no Bedrock possuem uma documentação com exemplos de uso da operação **InvokeModel**.

O **InvokeModel** é a operação utilizada para enviar uma entrada para um modelo e receber sua resposta. Em outras palavras, é a forma de realizar uma inferência diretamente em um modelo hospedado no Amazon Bedrock.

No exemplo de **InvokeModel** do Titan, podemos copiar o código disponibilizado na documentação e testar uma nova chamada ao modelo. Caso você não encontre esse exemplo diretamente na AWS, também pode utilizar o código disponível no arquivo `Bedrock/invoking_titan_model/titan.py`.

![image](/Bedrock/invoking_titan_model/images/TITAN-O1.png)

Neste exemplo, iremos solicitar recomendações de livros parecidos com o filme **Inception (A Origem)**, simulando uma inferência e convertendo o texto em embedding.

Lembre-se sempre de acompanhar o código com atenção e entender o que cada parte está fazendo.

![image](/Bedrock/invoking_titan_model/images/titan-02.png)