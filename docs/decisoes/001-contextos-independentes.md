# Contextos independentes

Cada contexto conclui o próprio trabalho com o que é dele e com o que chegou num fato. Nenhum chama o outro no meio da operação. A Operação registra a intenção sem perguntar a faixa. A Administração decide sem ler o histórico de preço nem a vitrine. A Vendas publica sem recalcular a regra. O aviso ao vendedor escuta a decisão sem consultar o catálogo e sem guardar o que recebeu.

Os termos seguem a [linguagem ubíqua](../dominio/linguagem-ubiqua.md). Quem publica, quem consome e o que cada fato leva estão em [Fluxo e integração](../arquitetura/fluxo-e-integracao.md).

## A faixa fica na Administração

A faixa de preço é a regra comercial da avaliação. Só a Administração compara o preço pretendido com ela. O fato que atravessa a fronteira leva o resultado dessa comparação, não os limites.

A Operação e a Vendas guardam identificação e nome do modelo para o vendedor escolher e para o comprador consultar. Essa cópia não inclui valor mínimo nem valor máximo. Se a faixa viajasse, os dois contextos passariam a conhecer a regra e a tentação seria reavaliar localmente, em vez de esperar a decisão.

## ModeloCatalogado

O vendedor escolhe um modelo já existente. O comprador consulta modelos. O catálogo é da Administração. Sem uma cópia local, a Operação teria de perguntar quais modelos existem no momento do cadastro, e a Vendas no momento da consulta.

**ModeloCatalogado** é o fato que monta essa cópia. A Administração publica quando passa a reconhecer um modelo. A Operação e a Vendas guardam identificação e nome. Os veículos de cada modelo só entram na vitrine por **IntencaoAprovada**.

## IntencaoEmAnalise

A Operação mostra ao vendedor quatro resultados: recebida, em análise, aprovada ou reprovada. "Recebida" ela grava sozinha, ao aceitar o cadastro. "Aprovada" e "reprovada" já tinham fato. "Em análise" não tinha.

Só a Administração sabe que o preço ficou fora da faixa. **IntencaoEmAnalise** comunica isso à Operação, no cadastro ou depois de uma alteração de preço. A Vendas não consome: se o veículo já estava na vitrine, quem o retira é **AnuncioRetirado**. O aviso ao vendedor não entra. O vendedor só é avisado na aprovação ou na reprovação.

## O aviso ao vendedor

O aviso não é contexto. Não há base, área nem serviço para construir. **IntencaoAprovada** e **IntencaoReprovada** continuam os fatos. Quando a aplicação existir, um ouvinte escreve uma linha de que o vendedor foi avisado. Na reprovação, a linha leva o motivo. O ouvinte não guarda estado. Se a linha atrasar ou não sair, a decisão na Administração, o resultado na Operação e a vitrine permanecem.

Entrada em análise e alteração de preço não geram aviso.

## O que a decisão não carrega

**IntencaoAprovada** não diz se a aprovação foi automática ou manual. A Operação guarda o resultado, a Vendas materializa o anúncio e o ouvinte escreve o aviso. A origem não muda nenhum dos três. Esse detalhe permanece na Administração.
