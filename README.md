ste projeto consiste em uma API REST de gerenciamento financeiro pessoal desenvolvida durante a trilha de Spring Boot. O grande diferencial da aplicação foi a integração com inteligência artificial utilizando o ecossistema moderno do Spring AI e Java 25, aplicando conceitos avançados de AI Function Calling (Invocação de Funções por IA).

Tecnologias e Ferramentas Utilizadas
Java 25 & Spring Boot 3.4.x

Spring AI (Starter OpenAI para processamento de linguagem natural)

Spring Data JPA & Banco de Dados para persistência das transações

Lombok (para redução de código boilerplate)

Arquitetura Limpa / Domain-Driven Design (DDD): Separação rigorosa entre as camadas de domínio (domain), aplicação (application) e infraestrutura (infrastructure).

Modelagem e Persistência: Ajuste dos contratos de repositórios (TransactionRepository e JpaTransactionRepository) para garantir a integridade do fluxo de dados de transações (Receitas e Despesas) mapeadas por categorias.

Criação da Camada de Aplicação: Desenvolvimento de Records (SaldoRequest e SaldoResponse) estruturados para trafegar os dados requisitados pela IA de forma leve e performática.

Configuração da Função Inteligente (Function Calling): Criação da classe FinanceFunctionsConfig, onde foi mapeada uma função nativa do Java (Function<SaldoRequest, SaldoResponse>). Esta função analisa o fluxo de caixa, identifica dinamicamente o que é receita ou despesa na base de dados, realiza o cálculo de saldo e disponibiliza essa ferramenta para que o modelo LLM (como o GPT da OpenAI) possa consultá-la de forma autônoma sempre que o usuário perguntar seu saldo por texto ou voz.

Resultado Final
O projeto demonstra como unir o poder de um ecossistema corporativo robusto (Spring Boot) com os recursos mais recentes de Inteligência Artificial Generativa, permitindo que o sistema não apenas converse com o usuário, mas também interaja diretamente com as regras de negócio e dados do banco em tempo real.
