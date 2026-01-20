# US02 – Controlar Acesso às Funcionalidades do Sistema

## Descrição da História:
> **Como** administrador do sistema,
> **quero** definir perfis de acesso para os usuários,
> **para** garantir que cada usuário execute apenas as funcionalidades permitidas.

## Dicionário de Dados:
> - **Usuário** (Objeto): Usuário autenticado no sistema.
> - **Perfil de Acesso** (Enum): Administrador, Regulação, Atenção Primária, Cidadão.
> - **Funcionalidade** (String): Ação ou recurso disponível no sistema.

## Regra(s) de Negócio:
> 1. Cada usuário deve possuir exatamente um perfil de acesso ativo.
> 2. O acesso às funcionalidades deve ser condicionado ao perfil do usuário.
> 3. Usuários inativos não podem executar nenhuma funcionalidade.

## Critério(s) de Aceite:
> 1. Dado um administrador, quando atribuir um perfil a um usuário, então a alteração deve ser aplicada com sucesso.
> 2. Dado um usuário, quando acessar uma funcionalidade, então o sistema deve validar seu perfil.
> 3. Dado um usuário sem permissão, quando tentar executar uma ação, então o acesso deve ser negado.
