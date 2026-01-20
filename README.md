# Projeto RegulaAE

> RegulaAE é uma aplicação web que organiza e torna transparente a regulação do acesso à Atenção Especializada, permitindo registrar > solicitações de consultas e exames feitas pela Atenção Primária e acompanhá-las em uma fila única e ordenada, com critérios claros > de priorização e visibilidade do andamento do atendimento.

## Status

>- **Em desenvolvimento:** Versão 1.0.0.
>- **Em homologação:** N/A.
>- **Em produção:** N/A.

## Contribuição
> Para clonar o repositório:
> ```
> git clone https://gitlab.unipampa.edu.br/pet-saude/transparencia/regulaae.git
> ```
>
> Para criar o ambiente virtual:
> ```
> conda env create -f environment.yml
> ```
>
> Para atualizar o ambiente virtual:
> ```
> conda env update -f environment.yml
> ```
>
> Para ativar o ambiente virtual:
> ```
> conda activate health_env
> ```
>
> Para definir health_env no VS Code:
> ```
> Abrir o prompt do VS Code (ctr+shift+p).
> Digitar Python: Selecionar Interpretador.
> Escolher health_env.
> ```
>
> Para executar os testes:
> ```
> pytest test/
> ```

## Repositório

> ```
> regulaae/
> ├── document/                 # Documentação do projeto.
> ├── source/                   # Código fonte do projeto.
> │   └── regulaae/             # Pacote principal do projeto.
> │       ├── application/      # Lógica de aplicação.
> │       ├── bootstrap/        # Arquivos de inicialização.
> │       └── infrastructure/   # Infraestrutura do projeto.
> ├── test/                     # Testes automatizados.
> ├── environment.yml           # Arquivo de configuração do ambiente Conda.
> ├── pyproject.toml            # Arquivo de configuração do projeto.
> ```

## Declaração de IA

>Este projeto faz uso de **ferramentas de IA** para apoiar a redação técnica, a organização do trabalho, o suporte especializado e a geração de código, testes e dados. Todos os conteúdos e implementações são **revisados, validados e aprovados pela equipe responsável**, que detém integralmente a **autoria e a responsabilidade técnica e ética** sobre os resultados.

## Direitos Autorais

> **© Universidade Federal do Pampa (UNIPAMPA).**
> *Todos os direitos são reservados*.
>
> Projeto desenvolvido pelo **Grupo Trasparência**, no âmbito do **PET-Saúde/I&SD Pampa Conectado**, sob titularidade da **Universidade Federal do Pampa (UNIPAMPA)**.
