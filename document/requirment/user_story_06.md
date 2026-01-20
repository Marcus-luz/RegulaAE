# US06 – Definir Prioridade da Solicitação

## Descrição da História:
> **Como** profissional da regulação municipal,
> **quero** definir a prioridade de uma solicitação,
> **para** garantir ordenação adequada da fila conforme necessidade assistencial.

## Dicionário de Dados:
> - **Prioridade** (Enum): Normal, Prioritária.
> - **Data de Classificação** (Date): Data da definição ou alteração da prioridade.

## Regra(s) de Negócio:
> 1. Apenas profissionais da regulação podem alterar a prioridade.
> 2. Alterações de prioridade devem ser registradas no histórico da solicitação.

## Critério(s) de Aceite:
> 1. Ao alterar a prioridade, a solicitação deve ser reposicionada automaticamente na fila.
> 2. O sistema deve manter a prioridade atual visível.
