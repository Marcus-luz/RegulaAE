# US08 – Registrar Realização ou Encerramento da Solicitação

## Descrição da História:
> **Como** profissional da regulação municipal,
> **quero** registrar a realização ou não realização de uma consulta ou exame,
> **para** encerrar corretamente o fluxo da solicitação.

## Dicionário de Dados:
> - **Status Final** (Enum): Realizada, Não Realizada.
> - **Data de Execução** (Date): Data da realização ou encerramento.
> - **Motivo de Não Realização** (String): Justificativa quando aplicável.

## Regra(s) de Negócio:
> 1. Solicitações finalizadas não podem retornar para a fila ativa.
> 2. O motivo é obrigatório quando o status final for “Não Realizada”.

## Critério(s) de Aceite:
> 1. Solicitações encerradas não devem aparecer na fila ativa.
> 2. O encerramento deve ficar visível para a ESF solicitante.
