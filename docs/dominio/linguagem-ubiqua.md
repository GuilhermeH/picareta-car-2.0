# Linguagem ubíqua

Estes são os termos do negócio. Documentos, eventos e código posteriores devem reutilizá-los com o mesmo sentido.

## Participantes

- **Vendedor** — proprietário ou responsável que cadastra o veículo para comercializá-lo pela Picareta Car.
- **Comprador** — pessoa que consulta a vitrine em busca de um veículo disponível.
- **Administrador** — quem mantém o catálogo de modelos, define as faixas de preço e decide as intenções que a avaliação automática não resolve.

## Catálogo e preço

- **Modelo** — tipo de veículo reconhecido pela Picareta Car. Toda intenção de venda aponta para um modelo já existente no catálogo. O vendedor não cria modelos.
- **Faixa de preço** — limites mínimo e máximo aceitáveis para um modelo. É a regra comercial usada na avaliação.
- **Preço pretendido** — valor que o vendedor pede pelo veículo na intenção de venda.
- **Histórico de preço** — registro de cada alteração do preço pretendido: valor anterior, novo valor e data. Pertence à vida do veículo na operação, não à vitrine.

## Intenção e avaliação

- **Intenção de venda** — pedido do vendedor para comercializar um veículo. Informa o modelo e o preço pretendido. Cadastrar a intenção não publica o veículo.
- **Avaliação** — comparação do preço pretendido com a faixa de preço do modelo.
- **Aprovação automática** — a avaliação conclui sozinha que o preço está dentro da faixa e a intenção pode seguir para publicação.
- **Análise manual** — a avaliação não aprova sozinha porque o preço está fora da faixa. A intenção fica com o administrador, que aprova ou reprova.
- **Aprovação** — decisão de que a intenção pode ser publicada. Pode vir da avaliação automática ou do administrador.
- **Reprovação** — decisão do administrador de encerrar a intenção. Exige um motivo e gera notificação ao vendedor.
- **Motivo da reprovação** — texto informado pelo administrador na reprovação. Viaja com a notificação ao vendedor.

## Publicação

- **Publicação** — inclusão do veículo aprovado na vitrine, tornando-o consultável pelo comprador.
- **Vitrine** — catálogo comercial visível no portal de vendas. Contém apenas veículos aprovados e disponíveis.
- **Veículo disponível** — veículo aprovado que o comprador pode ver ao escolher um modelo. Pendentes e reprovados não entram aqui.

## Áreas

- **Operação de veículos** — entrada e manutenção do que o vendedor cadastrou: intenção, preço e histórico.
- **Administração** — regras comerciais, modelos, faixas de preço e avaliação.
- **Vendas** — exposição dos veículos aprovados aos compradores.
- **Notificação** — aviso ao vendedor sobre aprovação ou reprovação. Na reprovação, inclui o motivo. É uma capacidade de apoio, não uma quarta área de negócio.
