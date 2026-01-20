# US01 – Acessar o Sistema de Forma Segura

## Descrição da História:
> **Como** usuário do sistema,
> **quero** autenticar-me para acessar o RegulaAE,
> **para** garantir acesso seguro e identificação adequada durante o uso do sistema.

## Dicionário de Dados:
> - **Usuário** (Objeto): Pessoa autenticada no sistema.
> - **Identificação** (String): Identificador único do usuário (ex.: e-mail).
> - **Status do Usuário** (Enum): Ativo ou Inativo.

## Regra(s) de Negócio:
> 1. Apenas usuários autenticados podem acessar o sistema.
> 2. Usuários com status inativo não podem acessar o sistema.

## Critério(s) de Aceite:
> 1. Dado um usuário válido, quando autenticar-se com sucesso, então o acesso deve ser concedido.
> 2. Dado um usuário não autenticado, quando tentar acessar o sistema, então o acesso deve ser negado.
> 3. Dado um usuário inativo, quando tentar autenticar-se, então o acesso deve ser negado.
