# Contextos

A Picareta Car separa três áreas porque cada uma responde a uma pergunta diferente e guarda dados diferentes. Juntar tudo num único modelo faria o comprador enxergar fila, reprovação e regra comercial, e faria a avaliação depender do histórico de preço do vendedor.

Cada contexto conclui o próprio trabalho com o que é dele e com o que chegou num fato. Nenhum chama o outro no meio da operação. A premissa e o que ela exclui estão em [Contextos independentes](../decisoes/001-contextos-independentes.md).

O aviso ao vendedor não é área nem serviço. Quando a aplicação existir, um ouvinte reage à aprovação ou à reprovação e escreve que o vendedor foi avisado.

Os termos abaixo seguem a [linguagem ubíqua](../dominio/linguagem-ubiqua.md).

## Operação de veículos

Dona da intenção de venda, do preço pretendido e do histórico de preço.

Também guarda uma cópia local da identificação e do nome de cada modelo, alimentada por ModeloCatalogado. Essa cópia não inclui a faixa de preço. O vendedor escolhe o modelo nessa lista, informa o preço, acompanha o andamento e altera o preço por aqui. Cada alteração grava o valor anterior, o novo valor e a data.

A Operação não conhece a faixa de preço e não decide se o veículo entra na vitrine. Ao aceitar o cadastro, ela mesma marca a intenção como recebida. Em análise, aprovada e reprovada chegam depois, como fatos da Administração.

## Administração

Dona do catálogo de modelos, da faixa de preço e da decisão.

Cada modelo tem identificação, nome, valor mínimo e valor máximo. Quando a Administração passa a reconhecer um modelo, publica ModeloCatalogado com identificação e nome. Os limites ficam aqui: são a regra da avaliação e não saem neste fato.

Se o preço pretendido está dentro da faixa, a aprovação é automática. Se está fora, a Administração publica IntencaoEmAnalise e a intenção fica em análise manual até o administrador aprovar ou reprovar. A reprovação exige motivo. Se o modelo da intenção não está no catálogo, a Administração não emite decisão.

A Administração não guarda o histórico de preço nem o anúncio que o comprador vê. Ela emite a decisão e segue em frente.

## Vendas

Dona somente da vitrine.

Guarda a mesma cópia de identificação e nome do modelo, para o comprador consultar os modelos. Os veículos de cada modelo só aparecem quando a Administração confirma o que pode ser mostrado. Cadastrados, em análise e reprovados não entram. O portal não explica a avaliação.

A Vendas não recalcula a faixa e não consome IntencaoEmAnalise. Ela inclui, atualiza ou retira um anúncio pelos fatos da Administração.

## Aviso ao vendedor

Não é contexto. Quando a intenção é aprovada ou reprovada, um ouvinte escreve que o vendedor foi avisado. Na reprovação, a linha leva o motivo. O ouvinte não guarda catálogo, faixa, vitrine nem a decisão. Entrada em análise e alteração de preço não geram aviso. Se a linha atrasar ou não sair, a decisão e a vitrine permanecem.

## Uma decisão, três leituras

"Aprovada" aparece nos três contextos, com papéis diferentes:

- a Administração **emite** a decisão;
- a Operação **guarda** o resultado para o vendedor acompanhar;
- a Vendas **materializa** o anúncio.

A fonte da decisão é uma só. As outras duas são leituras desse fato, cada uma no formato de quem consulta. Isso evita um status global compartilhado e deixa explícito por que o mesmo veículo pode existir em mais de um sistema sem ser o mesmo registro.

"Em análise" não tem essas três leituras. Só a Operação mostra esse resultado ao vendedor. A Vendas, se o veículo estava na vitrine, apenas deixa de mostrá-lo.
