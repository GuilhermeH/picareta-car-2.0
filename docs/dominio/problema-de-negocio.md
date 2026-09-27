# Picareta Car

## Contexto do negócio

A **Picareta Car** é uma empresa especializada na intermediação da compra e venda de veículos usados e seminovos.

A empresa funciona como um marketplace automotivo: proprietários interessados em vender seus veículos podem cadastrá-los na plataforma e, após um processo de avaliação, os veículos aprovados passam a fazer parte do catálogo disponível para potenciais compradores.

O objetivo da Picareta Car é simplificar o encontro entre quem deseja vender um veículo e quem procura um carro para comprar, mantendo um catálogo organizado e aplicando regras comerciais antes que um veículo seja anunciado publicamente.

## Como funciona a Picareta Car

O negócio possui três grandes áreas de atuação:

1. **Operação de veículos**, responsável pela entrada e manutenção dos veículos que serão comercializados;
2. **Vendas**, responsável pela exposição dos veículos aprovados aos compradores;
3. **Administração**, responsável pelas regras comerciais, catálogo de modelos e avaliação dos anúncios.

Essas áreas participam de diferentes etapas do ciclo de vida de um veículo dentro da empresa.

## Venda de um veículo

Um proprietário que deseja vender seu carro pode cadastrar uma **intenção de venda** na Picareta Car.

Durante o cadastro, o vendedor informa os dados necessários para identificar o veículo, incluindo o modelo e o valor pretendido para a venda.

Os modelos disponíveis para cadastro são definidos previamente pela própria Picareta Car. Dessa forma, todo veículo anunciado precisa estar associado a um modelo reconhecido pelo catálogo da empresa.

O simples cadastro do veículo não significa que ele será imediatamente anunciado.

Antes de aparecer para os compradores, a intenção de venda precisa passar pelo processo de avaliação da Picareta Car.

## Avaliação da intenção de venda

Para cada modelo de veículo, a Picareta Car mantém uma **faixa de preço considerada aceitável**, composta por um valor mínimo e um valor máximo.

Quando uma nova intenção de venda é recebida, o valor solicitado pelo vendedor é comparado com essa faixa.

Se o valor estiver dentro dos limites definidos para aquele modelo, o veículo poderá ser **aprovado automaticamente**.

Caso o valor esteja fora da faixa esperada, a intenção de venda será encaminhada para **análise manual de um administrador**.

O administrador poderá então aprovar ou reprovar o veículo.

Quando uma intenção de venda for reprovada, o administrador deverá informar o motivo da decisão e o vendedor será notificado.

## Publicação do veículo

Depois de aprovado, o veículo passa a fazer parte do catálogo comercial da Picareta Car e fica disponível para consulta pelos compradores.

Somente veículos aprovados podem ser apresentados no portal de vendas.

Dessa forma, existe uma separação clara entre:

- veículos cadastrados pelos vendedores;
- veículos aguardando avaliação;
- veículos reprovados;
- veículos aprovados e disponíveis para venda.

## Alteração de preço

Enquanto o veículo estiver sendo comercializado, o vendedor poderá alterar o preço solicitado.

A Picareta Car mantém o histórico dessas alterações.

Sempre que o preço for modificado, são registrados:

- o valor anterior;
- o novo valor;
- a data da alteração.

Esse histórico permite acompanhar a evolução do preço de um veículo durante o período em que ele permanece disponível para venda.

Uma alteração de preço também poderá exigir uma nova avaliação caso o novo valor deixe de atender às regras comerciais estabelecidas para o modelo.

## Experiência do comprador

No portal de vendas, os compradores podem consultar os modelos de veículos comercializados pela Picareta Car.

Ao selecionar um determinado modelo, a plataforma apresenta os veículos daquele modelo que estão atualmente aprovados e disponíveis para venda.

O comprador não precisa conhecer os processos internos de avaliação. Para ele, o catálogo representa apenas veículos que já passaram pelas regras comerciais da Picareta Car e estão efetivamente disponíveis.

## Administração do catálogo

A Picareta Car mantém um catálogo próprio de modelos de veículos.

Para cada modelo, a administração pode definir informações utilizadas pelas regras comerciais da empresa, incluindo:

- identificação do modelo;
- valor mínimo aceitável;
- valor máximo aceitável.

Esses limites são utilizados durante a avaliação das intenções de venda e permitem que parte do processo seja automatizada.

A administração também possui acesso às intenções que precisam de análise manual, podendo aprová-las ou reprová-las.

## Principais participantes do negócio

### Vendedor

É o proprietário ou responsável pelo veículo que deseja comercializá-lo através da Picareta Car.

Entre suas principais ações estão:

- cadastrar uma intenção de venda;
- selecionar o modelo do veículo;
- informar o preço pretendido;
- acompanhar a avaliação;
- receber notificações sobre aprovação ou reprovação;
- alterar o preço do veículo.

### Comprador

É a pessoa interessada em adquirir um veículo anunciado pela Picareta Car.

O comprador consulta o catálogo de modelos e visualiza os veículos aprovados que estão disponíveis para venda.

### Administrador

É o responsável pela gestão das regras comerciais da plataforma.

Entre suas responsabilidades estão:

- manter o catálogo de modelos;
- definir as faixas de preço dos modelos;
- analisar intenções de venda que não puderam ser aprovadas automaticamente;
- aprovar ou reprovar veículos;
- informar o motivo de uma reprovação.

## Ciclo de vida de um veículo

De forma simplificada, um veículo percorre o seguinte fluxo dentro da Picareta Car:

**Intenção de venda → Avaliação → Aprovação → Publicação → Disponível para venda**

Quando a intenção não atende às regras de aprovação automática:

**Intenção de venda → Avaliação automática → Análise manual → Aprovação ou reprovação**

Uma reprovação encerra o processo naquele momento e gera uma comunicação ao vendedor com o respectivo motivo.

## Objetivo deste projeto

Este repositório utiliza o negócio fictício da **Picareta Car** como cenário para estudo e implementação de uma aplicação distribuída.

O domínio foi escolhido por possuir processos que naturalmente atravessam diferentes responsabilidades do negócio, como cadastro de veículos, avaliação, administração do catálogo, publicação para venda, histórico de preços e notificações.

Ao longo do projeto, esse contexto servirá como base para explorar decisões de arquitetura, integração entre componentes, comunicação síncrona e assíncrona, consistência de dados, eventos e outros desafios comuns em sistemas distribuídos.

> A Picareta Car é uma empresa fictícia criada exclusivamente para fins de estudo de arquitetura e desenvolvimento de software.
