# Fintech Diagram

# Diagrama de aplicação para Fintech


## 1. Projeto de Arquitetura
### 1.1. FrontEnd
Aplicativo mobile construído em React Native ou Flutter para atender aos sistemas operacionais móveis no mercado, permitindo ao usuário se cadastrar, adquirir produtos e serviços extra, solicitar empréstimos, realizar pagamentos e transações como enviar/receber transferências para/de outros usuários, consultar saldo e extrato de conta.

### 1.2. BackEnd
Aplicação BackEnd criada em Node.js para gerenciar todas as requisições feitas pelo FrontEnd.

#### 1.2.1. Autenticação
Gerencia o login de usuários, tokens JWT e segurança geral da aplicação.

#### 1.2.2. CRUD Usuários
Gerencia o cadastro/edição das informações do usuário.

#### 1.2.3. Empréstimos
Gerencia solicitações de empréstimos, fazendo devidas análises de crédito do usuário.

#### 1.2.4. Produtos/Serviços
Gerencia o catálogo de produtos e serviços oferecidos pela empresa, e.g. pontos por compra em lojas parceiras.

#### 1.2.5. Transações
Gerencia todas as movimentações financeiras realizadas pelo usuário.

#### 1.2.6. Pagamentos
Realiza pagamentos para outros usuários/instituições e gera pagamentos para ser realizados por outros usuários/instituições.

#### 1.2.7. Conta
Gerencia os saldos do usuário, e.g. saldo em conta corrente, saldo em conta poupança.

#### 1.2.8. Integração
Realiza transações com sistemas externos como o sistema da Receita Federal ao realizar análise de crédito.

#### 1.2.9. Cartões
Gerencia solicitações do usuário para geração de cartão novo, novas vias de cartões, cartões virtuais, solicitação de análise de crédito para cartão de crédito.

### 1.3. Infraestrutura
A aplicação utilizaria PostgreSQL para armazenamento de dados, onde seria garantido a consistência transacional de dados, cache Redis para acelerar o acesso a informações acessadas com frequência e processamento assíncrono de eventos, como validação de transações, utilizando o sistema de mensageria RabbitMQ.

## 2. Plano de Escalabilidade
Pensando na expansão da empresa para outros países, poderia ser utilizado o sharding do banco de dados, dividindo as tabelas do BD em parcelas menores, baseando-se no país de exercício. Implementar o Load balancer com a finalidade de distribuir as requisições entre múltiplos servidores.

## 3. Plano de Resiliência e Monitoramento
Implementação de um Failover Automático, permitindo que o sistema redirecione o tráfego para servidores e/ou bancos de dados de backup em caso de falhas, implementação do padrão Circuit Breaker, protegendo o sistema contra sobrecarga ao previnir chamadas constantes a um serviço externo inoperante. Implementação de timeouts para as requisições, evitando que o sistema fique travado. Implantação do serviço Datadog para monitoramento de métricas, performance e implementação de alertas para eventos críticos.

## 4. Definição de Padrões de Desenvolvimento
### 4.1. Padrões Técnicos
Implementação de automatizações utilizando Jenkins ou GitHub Actions, com a finalidade de garantir uma integração e entrega contínuas, juntamente com a revisão de código, sendo obrigatório a criação de Pull Requests para a implantação de modificações e versionamento para facilitar as releases e o gerenciamento de versões. Utilização da ferramenta Swagger para geração da documentação do código.

### 4.2 Testes Automatizados
Garantir uma cobertura mínima de 80% do código em testes unitários e testes de integração utilizando as bibliotecas Mocha e Chai para Node.js



