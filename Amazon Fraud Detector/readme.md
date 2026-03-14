## Amazon Fraud Detector

Nesta seção, vamos aplicar no ambiente da AWS os principais conceitos do **Amazon Fraud Detector**.

O **Amazon Fraud Detector** é um serviço gerenciado da AWS voltado para a detecção de atividades potencialmente fraudulentas em canais digitais, como **fraudes em pagamentos**, **cadastros falsos**, uso de **bots** e outros comportamentos suspeitos. O serviço combina **machine learning**, regras de negócio e variáveis de evento para apoiar a análise de risco e a classificação de transações ou ações online.

Ao longo desta seção, utilizaremos um conjunto de dados de exemplo para entender a configuração dos recursos do serviço, a definição de eventos, variáveis e rótulos, além da estrutura usada no processo de análise de fraude. O dataset utilizado estará disponível na pasta `utils`.

> **Atualização - Importante:** de acordo com a documentação da AWS, o Amazon Fraud Detector não está mais aberto para novos clientes desde **7 de novembro de 2025**. Por isso, dependendo da conta utilizada, pode não ser possível seguir com todas as etapas práticas do serviço.
>
> Ainda assim, o estudo deste conteúdo continua sendo relevante, principalmente para compreender:
>
> - o conceito do serviço
> - a estrutura de um **event type**
> - a definição de **variáveis**
> - o uso de **labels**
>
> Para fins de prova e estudo, entender esses conceitos e outros costuma ser mais importante do que executar o treinamento completo de um modelo, já que não está mais no ar.