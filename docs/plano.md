# Plano

Este arquivo guarda a ordem em que o estudo passa do problema para o código. Cada passo é preenchido quando o anterior já está registrado. O conteúdo da decisão fica no artefato ligado aqui.

## 1. Runtime, transporte e persistência

Operação, Administração, Vendas e o ouvinte rodam em .NET. Os fatos viajam no Kafka. Um SQL Server guarda os bancos `operacao`, `administracao` e `vendas`. O processo grava e publica em seguida. Docker Compose sobe Kafka e SQL Server; os processos sobem no host com `dotnet run`.

O registro está em [Runtime, transporte e persistência](decisoes/002-runtime-transporte-e-persistencia.md).

## 2. Contratos dos fatos

O que este passo fecha: os oito fatos como contrato, com nome, campos, quem publica e quem consome.

Onde o resultado fica: `docs/contratos/`, um arquivo por fato.

Pronto quando: cada fato tem esse contrato registrado e este plano aponta para ele.

## 3. Estado local

O que este passo fecha: o que cada contexto persiste para si.

Onde o resultado fica: `docs/arquitetura/estado-local.md`.

Pronto quando: Operação, Administração e Vendas tiverem o estado local registrado nesse arquivo e este plano apontar para ele.

## 4. Fatia dentro da faixa

O que este passo fecha: a sequência em que o preço já nasce dentro da faixa. ModeloCatalogado, IntencaoRegistrada, IntencaoAprovada e o veículo na vitrine.

Onde o resultado fica: neste plano.

Pronto quando: a sequência de implementação estiver escrita aqui.

## 5. Caminhos seguintes

O que este passo fecha: preço fora da faixa, alteração de preço, modelo desconhecido e o ouvinte do aviso.

Onde o resultado fica: neste plano.

Pronto quando: a ordem desses caminhos estiver escrita aqui.
