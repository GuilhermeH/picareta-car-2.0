# Runtime, transporte e persistência

Operação, Administração e Vendas rodam em .NET. Cada uma grava o que é dela num banco próprio e publica o fato no Kafka. O aviso ao vendedor é um ouvinte nesse mesmo runtime. Ele não é serviço e não tem base.

Os termos seguem a [linguagem ubíqua](../dominio/linguagem-ubiqua.md). Quem publica, quem consome e o que cada fato leva estão em [Fluxo e integração](../arquitetura/fluxo-e-integracao.md).

## .NET

Os três contextos são processos .NET. O ouvinte também. Ele reage à aprovação ou à reprovação e escreve que o vendedor foi avisado.

## Kafka

O fato que cruza a fronteira é uma mensagem no Kafka. A Operação conclui o cadastro com o que é dela. A Administração conclui a decisão com a faixa que guarda. A Vendas conclui o anúncio com o fato que recebeu. O ouvinte escreve o aviso com o que veio na mensagem.

## Três bancos

Um SQL Server hospeda três bancos: `operacao`, `administracao` e `vendas`. A Operação grava em `operacao`. A Administração grava em `administracao`. A Vendas grava em `vendas`.

## Gravar e publicar em seguida

O processo que tomou a decisão grava no banco dele e, em seguida, publica o fato no Kafka. Entre as duas escritas há uma janela: o registro já existe e a mensagem ainda pode não ter saído. O estudo aceita essa janela.

Um processo à parte, que publicasse o fato depois, entra quando um fluxo for nomeado para isso.

## Ambiente local

Docker Compose sobe o Kafka e o SQL Server. Os processos .NET sobem no host com `dotnet run`.

## O que esta decisão não fixa

Ficam para os passos seguintes os contratos dos oito fatos, os campos de cada banco, os nomes dos tópicos, a versão do SDK, o arquivo do Compose e o código dos processos.
