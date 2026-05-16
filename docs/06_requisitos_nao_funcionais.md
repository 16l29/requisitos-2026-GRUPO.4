# Requisitos Não Funcionais (RNF) - Sistema de Apoio ao ENADE

## Histórico de Versões

| Data       | Versão | Descrição                                     | Autor          |
| ---------- | ------- | ----------------------------------------------- | -------------- |
| 16/05/2026 | 1.0     | Criação do documento e elicitação dos RNFs. | Karlos Eduardo |

---

## 1. Introdução

Este documento lista os **Requisitos Não Funcionais (RNF)** do Sistema de Apoio ao ENADE. Diferente dos requisitos funcionais (que descrevem *o que* o sistema faz), os requisitos não funcionais descrevem *como* o sistema faz, estabelecendo critérios de qualidade, restrições tecnológicas, padrões de desempenho, segurança e usabilidade que a arquitetura deve suportar.

---

## 2. Catálogo de Requisitos Não Funcionais

Abaixo estão os requisitos categorizados de acordo com as restrições arquiteturais definidas previamente (React, Node.js, PostgreSQL e Google OAuth).

### 2.1. Desempenho e Eficiência (Performance)

| ID              | Descrição                                                                                                                                                                                                        | Justificativa                                                                                   |
| :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------- |
| **RNF01** | O tempo de resposta da API (Node.js) para consultas simples ao banco de questões não deve exceder**500 milissegundos** em condições normais de rede.                                                     | Garantir fluidez para o estudante que está pelo celular com tempo contado no simulado.         |
| **RNF02** | O sistema deve ser capaz de suportar até**500 acessos simultâneos** (concorrência) durante períodos de pico (ex: vésperas do exame do ENADE) sem degradação do tempo de resposta acima de 2 segundos. | Assegurar a estabilidade do sistema quando turmas inteiras acessarem o simulado ao mesmo tempo. |
| **RNF03** | A renderização inicial das páginas no Front-end (React) deve ocorrer em menos de**3 segundos** em conexões de banda larga padrão.                                                                       | Evitar que o usuário abandone o sistema devido a telas de carregamento demoradas.              |

### 2.2. Segurança e Privacidade (Security)

| ID              | Descrição                                                                                                                                                                  | Justificativa                                                                                            |
| :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| **RNF04** | A comunicação entre o Front-end (React), a API RESTful (Node.js) e o Banco de Dados (PostgreSQL) deve ser obrigatoriamente criptografada via protocolo**HTTPS/TLS**. | Proteger os dados acadêmicos e as credenciais de interceptação na rede.                               |
| **RNF05** | O sistema não deve armazenar senhas locais de usuários; toda a autenticação deve ser delegada e gerida exclusivamente pelo protocolo**OAuth 2.0 (Google OAuth)**.  | Minimizar riscos de vazamento de credenciais e aproveitar a infraestrutura de segurança do Google.      |
| **RNF06** | O banco de dados (PostgreSQL) deve possuir rotinas automatizadas de**backup diário (incremental)**, com retenção mínima de 30 dias.                                | Garantir a recuperação das estatísticas de turmas e do histórico de fóruns em caso de falha severa. |

### 2.3. Usabilidade e Acessibilidade (Usability)

| ID              | Descrição                                                                                                                                                                    | Justificativa                                                                                       |
| :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------- |
| **RNF07** | A interface de usuário (Front-end) deve ser**100% responsiva**, adaptando-se automaticamente a resoluções de telas de smartphones, tablets e desktops (Mobile-First). | Cumprir a restrição arquitetural de possuir uma única interface portável (web/mobile).          |
| **RNF08** | O sistema deve fornecer mensagens de erro amigáveis e feedback visual (ex:*spinners* de carregamento, alertas de sucesso) para todas as ações assíncronas do usuário.   | Melhorar a experiência de uso (UX) e reduzir a frustração de estudantes em momentos de estresse. |

### 2.4. Confiabilidade e Disponibilidade (Reliability)

| ID              | Descrição                                                                                                                                                                                      | Justificativa                                                                                          |
| :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------- |
| **RNF09** | O sistema deve garantir uma taxa de**disponibilidade (*uptime*) de 99.5%** durante os meses de preparação ativa para o ENADE (Agosto a Novembro).                                      | Evitar que o sistema fique fora do ar nos momentos em que os professores mais precisam dos dashboards. |
| **RNF10** | A API RESTful deve implementar tratamento global de exceções, garantindo que o sistema nunca exiba a*stack trace* (código interno de erro) para o cliente em caso de falhas na aplicação. | Manter o profissionalismo do sistema e evitar exposição de vulnerabilidades da arquitetura Node.js.  |

### 2.5. Portabilidade e Manutenibilidade (Portability)

| ID              | Descrição                                                                                                                                                              | Justificativa                                                                                |
| :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------- |
| **RNF11** | O Front-end deve ser compatível com as duas últimas versões dos principais navegadores de mercado (Google Chrome, Mozilla Firefox, Safari e Microsoft Edge).          | Garantir que nenhum aluno seja impedido de estudar por usar um navegador diferente.          |
| **RNF12** | O código-fonte do Back-end e do Front-end deve seguir os padrões de formatação de código (Linting e Prettier) estabelecidos para a linguagem JavaScript/TypeScript. | Facilitar a manutenção e a legibilidade do código pela Equipe de TI ao longo das Sprints. |
