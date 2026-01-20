# US07 – Acompanhar Status da Solicitação

## Descrição da História:
> **Como** profissional da Atenção Primária à Saúde,
> **quero** acompanhar o status das solicitações da minha ESF,
> **para** informar o usuário e planejar a continuidade do cuidado.

## Dicionário de Dados:
> - **Status da Solicitação** (Enum): Aguardando, Regulada, Realizada.
> - **Data de Atualização** (Date): Data da última mudança de status.

## Regra(s) de Negócio:
> 1. Cada solicitação deve possuir exatamente um status ativo.
> 2. Mudanças de status devem ser registradas automaticamente.

## Critério(s) de Aceite:
> 1. A ESF deve visualizar apenas as solicitações por ela registradas.
> 2. O status exibido deve refletir a situação atual da solicitação.
