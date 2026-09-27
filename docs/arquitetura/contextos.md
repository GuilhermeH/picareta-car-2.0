# Contextos

A Picareta Car separa três áreas porque cada uma responde a uma pergunta diferente e guarda dados diferentes. Juntar tudo num único modelo faria o comprador enxergar fila, reprovação e regra comercial, e faria a avaliação depender do histórico de preço do vendedor.

Notificação não é uma quarta área. Ela não decide nada: reage à aprovação ou à reprovação e avisa o vendedor.

Os termos abaixo seguem a [linguagem ubíqua](../dominio/linguagem-ubiqua.md).

## Operação de veículos

Dona da intenção de venda, do preço pretendido e do histórico de preço.

O vendedor cadastra a intenção, escolhe um modelo já existente, informa o preço, acompanha o andamento e altera o preço por aqui. Cada alteração grava o valor anterior, o novo valor e a data.

A Operação não conhece a faixa de preço e não decide se o veículo entra na vitrine. Ela guarda, para o vendedor, o resultado que a Administração comunicar: recebida, em análise, aprovada ou reprovada.

## Administração

Dona do catálogo de modelos, da faixa de preço e da decisão.

Cada modelo tem identificação, valor mínimo e valor máximo. Esses limites são a regra da avaliação. Se o preço pretendido está dentro da faixa, a aprovação é automática. Se está fora, a intenção fica em análise manual até o administrador aprovar ou reprovar. A reprovação exige motivo.

A Administração não guarda o histórico de preço nem o anúncio que o comprador vê. Ela emite a decisão e segue em frente.

## Vendas

Dona somente da vitrine.

O comprador consulta modelos e, ao escolher um, vê os veículos daquele modelo que estão aprovados e disponíveis. Cadastrados, em análise e reprovados não aparecem. O portal não explica a avaliação.

A Vendas não recalcula a faixa. Ela inclui, atualiza ou retira um anúncio quando a Administração confirma o que pode ser mostrado.

## Notificações

Capacidade de apoio. Quando a intenção é aprovada ou reprovada, o vendedor é avisado. Na reprovação, o aviso leva o motivo. Não há catálogo, faixa nem vitrine aqui.

## Uma decisão, três leituras

"Aprovada" aparece nos três contextos, com papéis diferentes:

- a Administração **emite** a decisão;
- a Operação **guarda** o resultado para o vendedor acompanhar;
- a Vendas **materializa** o anúncio.

A fonte da decisão é uma só. As outras duas são leituras desse fato, cada uma no formato de quem consulta. Isso evita um status global compartilhado e deixa explícito por que o mesmo veículo pode existir em mais de um sistema sem ser o mesmo registro.
