# US05 – Visualizar Fila Única de Regulação

## Descrição da História:
> **Como** profissional da regulação municipal,
> **quero** visualizar a fila única de solicitações,
> **para** ordenar e acompanhar as demandas de consultas e exames de forma transparente.

## Dicionário de Dados:
> - **Solicitação** (Objeto): Registro do pedido regulado.
> - **Data de Entrada** (Date): Data de inclusão na fila.
> - **Tipo de Solicitação** (Enum): Consulta ou Exame.
> - **Prioridade** (Enum): Normal ou Prioritária.

## Regra(s) de Negócio:
> 1. A fila deve ser ordenada por prioridade e, em seguida, por data de entrada.
> 2. Solicitações finalizadas não devem aparecer na fila ativa.

## Critério(s) de Aceite:
> 1. A fila deve exibir todas as solicitações pendentes de forma ordenada.
> 2. Alterações de prioridade ou status devem refletir imediatamente na fila.
