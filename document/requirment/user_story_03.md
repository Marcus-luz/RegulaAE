# US03 – Registrar Ações para Rastreabilidade

## Descrição da História:
> **Como** administrador do sistema
> **quero** que as ações relevantes realizadas no RegulaAE sejam registradas,
> **para** garantir rastreabilidade, transparência e apoio à governança do processo de regulação.

## Dicionário de Dados:
> - **Registro de Ação** (Objeto): Registro de uma ação executada no sistema.
> - **Usuário** (Objeto): Usuário responsável pela ação.
> - **Ação** (String): Operação realizada no sistema.
> - **Data da Ação** (DateTime): Momento da execução da ação.

## Regra(s) de Negócio:
> 1. Ações relevantes devem ser registradas automaticamente.
> 2. Registros de ações não podem ser alterados após sua criação.
> 3. Apenas usuários autorizados podem consultar os registros.

## Critério(s) de Aceite:
> 1. Dada a execução de uma ação relevante, quando ela ocorrer, então um registro deve ser criado automaticamente.
> 2. Dado um administrador, quando consultar os registros, então as informações devem ser apresentadas corretamente.
> 3. Dado um usuário não autorizado, quando tentar consultar os registros, então o acesso deve ser negado.
