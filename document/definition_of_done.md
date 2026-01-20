# Definition of Done (DoD) — RegulaAE (MVP)

> Este Definition of Done (DoD) define **quando um item é considerado pronto** no contexto do **MVP do RegulaAE**.
Se qualquer regra abaixo for violada, o item **não está pronto**, mesmo que “funcione” ou passe em testes superficiais.

> O MVP prioriza **clareza arquitetural, correção funcional e sustentabilidade**, evitando complexidade desnecessária.

---

## 1. Arquitetura (Obrigatório)

> A arquitetura de referência do projeto é **Hexagonal (Ports & Adapters)**.

### Regras Gerais
> - Não existem dependências circulares entre pacotes.
> - Nenhuma camada “pula” outra.
> - Violações arquiteturais invalidam o item.

### Dependências Permitidas
> - `application` **não depende** de `infrastructure`.
> - `domain` **não depende** de `dto`, `port`, `usecase` ou `infrastructure`.
> - `infrastructure` **depende** de `application`, nunca o contrário.
> - `bootstrap` pode depender de todas as camadas.
> - Nenhuma camada depende de `bootstrap`.

### Domínio (`application.domain`)
> - Contém apenas regras de negócio.
> - Não importa frameworks web, ORM ou bibliotecas técnicas.
> - Não conhece DTOs, controllers ou modelos de banco.
> - Entidades, VOs e serviços garantem invariantes do domínio.
> - Exceções de domínio são definidas aqui.

### Casos de Uso (`application.usecase`)
> - Representam intenções claras de negócio.
> - Orquestram domínio e portas.
> - Não contêm lógica técnica (HTTP, SQL, serialização).
> - Não instanciam implementações concretas.

### Portas
> - **Entrada (`application.port.input`)**
>   - Definem o contrato dos casos de uso.
>   - Não conhecem protocolos externos.
> - **Saída (`application.port.output`)**
>   - Definem necessidades do domínio em relação ao mundo externo.
>   - Não conhecem detalhes técnicos.

### Adaptadores
> - **Inbound (`infrastructure.inbound.ui.web`)**
>   - Lidam apenas com protocolo (HTTP), validação sintática e conversão para DTO.
>   - Não contêm regras de negócio.
>   - Chamam casos de uso apenas via portas.
> - **Outbound (`infrastructure.outbound.persistence`)**
>   - Implementam portas de saída.
>   - Contêm detalhes técnicos (ORM, SQL).
>   - Não contêm regras de negócio.

### Bootstrap
> - Criação de objetos e injeção de dependências ocorrem apenas aqui.
> - Não existe lógica de negócio em `bootstrap`.

---

## 2. Estrutura do Projeto (Obrigatório)

> Todo artefato deve estar no local correto, conforme a estrutura oficial:

> - `application.domain`
>   - `entity`, `enum`, `exception`, `service`, `vo`
> - `application.dto`
>   - `input`, `output`
> - `application.port`
>   - `input`, `output`
> - `application.usecase`
> - `infrastructure.inbound.ui.web`
> - `infrastructure.outbound.persistence`
>   - `migration`, `model`, `repository`
> - `bootstrap`

> Código fora do lugar **não está pronto**.

---

## 3. Idioma (Obrigatório)

> - **Código (identificadores):** inglês (`en_US`)
> - **Interface e mensagens ao usuário:** português (`pt_BR`)
> - **Docstrings e comentários:** `pt_BR`
> - Não há mistura de idiomas no mesmo contexto.
> - Mensagens ao usuário não expõem detalhes técnicos.

---

## 4. Nomenclatura (Obrigatório)

> Seguir **PEP 8**:

> - Pacotes e módulos: `snake_case`
> - Classes: `PascalCase`
> - Funções e métodos: `snake_case`
> - Exceções terminam com `Error`
> - Constantes: `UPPER_SNAKE_CASE`
> - Evitar nomes genéricos (`utils`, `manager`, `handler`).

---

## 5. Tratamento de Erros e Logs (MVP)

> - Exceções de domínio representam erros de negócio.
> - Exceções técnicas não vazam para o domínio.
> - Adaptadores convertem erros internos em respostas adequadas ao usuário.
> - Erros relevantes são registrados em log.
> - Logs não contêm dados sensíveis.
> - Não existem erros silenciosos.

### Auditoria (MVP)
> No MVP, apenas **ações sensíveis** devem ser registradas:

> - criação de solicitação;
> - alteração de prioridade;
> - encerramento de solicitação;
> - alteração de perfil de usuário.

---

## 6. Qualidade de Código (Obrigatório)

> - Código é legível sem explicação oral.
> - Classes e métodos possuem responsabilidade única.
> - Não existem “classes Deus” ou módulos genéricos.
> - Dependências são injetadas, não instanciadas na lógica.
> - Domínio e casos de uso são determinísticos.
> - Invariantes do domínio são garantidos no domínio.
> - Evitar complexidade desnecessária e otimizações prematuras.

---

## 7. Testes (MVP)

### Especificação

> - Todo item possui issue associada.
> - Critérios de aceitação estão explícitos na issue.
> - Existe rastreabilidade clara: issue → código → testes.

### Testes de Unidade

> - Domínio e casos de uso possuem testes.
> - Testes não dependem de banco, rede ou Flask.
> - Portas são mockadas/stubadas quando necessário.
> - Testes são determinísticos e repetíveis.

### Testes de Integração

> - Adaptadores críticos (ex.: persistência, web) possuem testes de integração.
> - Integrações técnicas são testadas de forma controlada.

---

## 8. Critério Final de Pronto

> Um item está **Pronto** quando:

> - respeita integralmente a arquitetura hexagonal;
> - está corretamente posicionado na estrutura;
> - atende aos critérios de aceitação da issue;
> - possui testes adequados ao seu nível;
> - não introduz acoplamento indevido ou dívida estrutural;
> - mantém o escopo enxuto do MVP do RegulaAE.
