# Caso de Uso: Sistema de Gestão de Pedidos - Loja Virtual

## Visão Geral

Este sistema tem como objetivo permitir que clientes realizem pedidos de produtos em uma loja virtual, possibilitando cadastro, gerenciamento de pedidos, pagamento, geração de nota fiscal e notificações.

---

## Atores Principais

- **Cliente**: Usuário do sistema que realiza compras.
- **Sistema de Pagamento**: Responsável por processar os pagamentos.
- **Sistema de Notificação**: Envia e-mails ou SMS ao cliente.
- **Admin (opcional)**: Gerencia produtos e acompanha pedidos.

---

## Objetivo Principal

Permitir que clientes:
- Realizem o cadastro com múltiplos endereços.
- Visualizem produtos disponíveis.
- Realizem pedidos com múltiplos itens.
- Efetivem o pagamento e recebam uma nota fiscal.
- Sejam notificados do status do pedido.

---

## Casos de Uso

### UC01 - Cadastrar Cliente
**Ator:** Cliente  
**Descrição:** Permite que o cliente crie uma conta com seus dados e endereços.  
**Fluxo Principal:**
1. Cliente informa nome, e-mail, senha e endereço(s).
2. Sistema valida e armazena os dados.
3. Sistema confirma o cadastro com uma mensagem de boas-vindas.

---

### UC02 - Listar Produtos
**Ator:** Cliente  
**Descrição:** Permite que o cliente visualize os produtos disponíveis na loja.  
**Fluxo Principal:**
1. Cliente acessa a listagem de produtos.
2. Sistema exibe nome, preço e estoque disponível.

---

### UC03 - Criar Pedido
**Ator:** Cliente  
**Descrição:** Cliente seleciona produtos, define quantidade e adiciona ao carrinho.  
**Fluxo Principal:**
1. Cliente seleciona produtos.
2. Sistema cria um novo Pedido com `ItemPedido`.
3. Cliente confirma o pedido.
4. Sistema associa o pedido ao cliente.

---

### UC04 - Efetuar Pagamento
**Ator:** Cliente  
**Descrição:** Cliente escolhe a forma de pagamento e conclui a compra.  
**Fluxo Principal:**
1. Cliente escolhe forma de pagamento.
2. Sistema processa o pagamento.
3. Sistema gera `Pagamento` e `NotaFiscal`.

---

### UC05 - Enviar Notificação
**Ator:** Sistema de Notificação  
**Descrição:** Após confirmação de pagamento, o sistema envia uma notificação ao cliente.  
**Fluxo Principal:**
1. Pagamento é confirmado.
2. Sistema invoca o `Notificador`.
3. Cliente recebe notificação por e-mail ou SMS.

---

## Requisitos Funcionais

- RF01: O sistema deve permitir o cadastro de clientes com múltiplos endereços.
- RF02: O sistema deve permitir o cadastro e listagem de produtos.
- RF03: O cliente deve ser capaz de criar um pedido com múltiplos itens.
- RF04: O sistema deve gerar nota fiscal ao concluir o pagamento.
- RF05: O sistema deve enviar notificações por e-mail ou SMS após cada pedido.

---

## Tecnologias e Padrões Recomendados

- Java + Spring Boot
- JPA (Hibernate) para ORM
- PostgreSQL para persistência
- Arquitetura MVC
- REST API
- UML para documentação

---

## Casos de Expansão

- Implementar histórico de pedidos por cliente.
- Integração com gateway de pagamento (ex: Stripe, Mercado Pago).
- Implementar interface gráfica responsiva (React, Angular).
- Adicionar login com OAuth (Google, Facebook).
