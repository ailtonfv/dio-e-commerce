# dio-e-commerce
Exercício simulando um e-commerce, objetivo é a utilização de banco relacional
📦 Projeto de Modelagem de Dados — E-commerce

(Exercício conceitual e prático — DIO)

📌 Objetivo do Projeto

Este projeto tem como objetivo modelar e implementar a estrutura de dados de um sistema de e-commerce, com foco em:

boas práticas de modelagem relacional;

clareza nas decisões de design;

separação entre entidades estáticas e eventos/processos;

preparação para análises futuras via SQL.

Embora inspirado em um cenário de comércio eletrônico, este projeto também serve como exercício de treino conceitual para sistemas mais complexos, como plataformas de políticas públicas (ex.: CadÚnico), onde há forte dependência de eventos, status e histórico.

🧠 Escopo Funcional

O modelo contempla, entre outros, os seguintes requisitos:

Clientes podem ser Pessoa Física (PF) ou Pessoa Jurídica (PJ)
(CPF e CNPJ são tratados como identificadores distintos).

Um cliente pode realizar múltiplos pedidos.

Um pedido pode conter múltiplos itens, com quantidades e preços unitários distintos.

Um pedido pode:

ser pago por diferentes modalidades de pagamento;

ser cancelado;

gerar uma entrega, que possui status próprio.

O valor do frete é determinado a partir do endereço do cliente.

O sistema contempla controle básico de estoque e fornecedores.

🗂️ Principais Entidades do Modelo

O modelo inclui, mas não se limita, às seguintes entidades essenciais:

Cliente

Endereço

Produto

Estoque

Fornecedor

Pedido

Item do Pedido

Pagamento

Entrega

Entidades como Pagamento e Entrega são tratadas explicitamente como entidades próprias, e não como atributos, por representarem eventos/processos que podem ocorrer mais de uma vez ou evoluir ao longo do tempo.

⚙️ Decisões de Design (Resumo)

Algumas decisões importantes adotadas neste projeto:

Pagamento como entidade
Um pedido pode possuir múltiplos registros de pagamento (parcelas, tentativas, métodos distintos).

Entrega como entidade com status
A entrega possui ciclo de vida próprio (ex.: criada, enviada, entregue, cancelada).

Cliente PF/PJ
O modelo diferencia Pessoa Física e Pessoa Jurídica, respeitando suas naturezas distintas.

Histórico e rastreabilidade
O modelo privilegia a possibilidade de análise histórica (eventos), evitando estruturas excessivamente estáticas.

Essas decisões foram tomadas com base no mini-mundo descrito no enunciado e em boas práticas de modelagem.

📐 Estrutura do Repositório
ecommerce-modelagem/
├── README.md
├── modelo/
│   ├── diagrama.dbml
│   └── diagrama.png
├── sql/
│   ├── ddl.sql
│   └── queries_exemplo.sql
└── docs/
    └── decisoes_de_design.md

🛠️ Tecnologias Utilizadas

SQL (DDL e consultas)

dbdiagram.io (modelagem conceitual/lógica)

GitHub (versionamento e documentação)

🎯 Finalidade Didática

Este projeto não visa simular um sistema comercial real em produção, mas sim:

consolidar conceitos de modelagem de dados;

treinar leitura e interpretação de requisitos;

exercitar decisões arquiteturais;

preparar terreno para projetos de maior complexidade.

📎 Observação Final

As escolhas de modelagem aqui apresentadas refletem opções conscientes, e não verdades absolutas.
Em cenários reais, decisões semelhantes devem sempre considerar contexto institucional, volume de dados, governança e requisitos legais.
