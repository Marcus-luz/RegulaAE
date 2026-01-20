# US04 – Registrar Solicitação de Consulta ou Exame

## Descrição da História:
> **Como** profissional da Atenção Primária à Saúde,
> **quero** registrar uma solicitação de consulta ou exame especializado,
> **para** que a demanda entre em uma fila única e rastreável de regulação.

## Dicionário de Dados:
> - **Identificador do Usuário** (String): CPF ou Cartão SUS do paciente.
> - **Tipo de Solicitação** (Enum): Consulta ou Exame.
> - **Especialidade/Exame** (String): Especialidade médica ou tipo de exame solicitado.
> - **Data da Solicitação** (Date): Data de registro da solicitação.
> - **ESF Solicitante** (String): Identificação da equipe de Saúde da Família.

## Regra(s) de Negócio:
> 1. Toda solicitação deve estar vinculada a uma ESF.
> 2. Solicitações só podem ser registradas com dados obrigatórios preenchidos.

## Critério(s) de Aceite:
> 1. Ao salvar a solicitação, ela deve entrar automaticamente na fila de regulação.
> 2. O sistema deve impedir o registro sem identificação do usuário ou da ESF.
