# Especificação de Requisitos de Software

## Para Sistema ENADE

Preparado por Kayo Gomes, Karlos Eduardo, Gustavo Lima
Orientador: Prof. Marcelo Bezerra
Junho de 2026

## Sumário

* [1. Introdução](#1-introdução)
  * [1.1 Propósito do Documento](#11-propósito-do-documento)
  * [1.2 Escopo do Produto](#12-escopo-do-produto)
  * [1.3 Definições, Acrônimos e Abreviações](#13-definições-acrônimos-e-abreviações)
  * [1.4 Referências](#14-referências)
  * [1.5 Visão Geral do Documento](#15-visão-geral-do-documento)
* [2. Descrição Geral do Produto](#2-descrição-geral-do-produto)
  * [2.1 Perspectiva do Produto](#21-perspectiva-do-produto)
  * [2.2 Funções do Produto](#22-funções-do-produto)
  * [2.3 Restrições do Produto](#23-restrições-do-produto)
  * [2.4 Características dos Usuários](#24-características-dos-usuários)
  * [2.5 Premissas e Dependências](#25-premissas-e-dependências)
  * [2.6 Distribuição de Requisitos](#26-distribuição-de-requisitos)
* [3. Requisitos](#3-requisitos)
  * [3.1 Interfaces Externas](#31-interfaces-externas)
  * [3.2 Funções](#32-funções)
  * [3.3 Qualidade de Serviço](#33-qualidade-de-serviço)
  * [3.4 Conformidade](#34-conformidade)
  * [3.5 Design e Implementação](#35-design-e-implementação)
* [4. Verificação](#4-verificação)
* [5. Apêndices](#5-apêndices)

## Histórico de Revisões

| Nome                       | Data       | Razão para as Alterações                                       | Versão |
| -------------------------- | ---------- | ----------------------------------------------------------------- | ------- |
| Kayo Gomes, Karlos Eduardo | 21/04/2026 | Identificação de requisitos, stakeholders e documento de visão | 1.0     |
| Gustavo Lima               | 23/04/2026 | Refinamentos gerais                                               | 1.1     |
| Kayo Gomes                 | 01/05/2026 | Inclusão do Product Owner nas Partes Interessadas                | 1.2     |
| Karlos Eduardo, Kayo Gomes | 16/05/2026 | Elicitação dos Requisitos Funcionais e Não Funcionais          | 1.3     |
| Kayo Gomes                 | 19/05/2026 | Adição da persona Coordenação e regras de negócio            | 1.4     |
| Kayo Gomes                 | 28/05/2026 | Especificação dos CDUs 01 ao 09                                 | 1.5     |
| Kayo Gomes, Karlos Eduardo | 01/06/2026 | Atualização do Diagrama de Casos de Uso e CDU-10 e CDU-11       | 1.6     |
| Karlos Eduardo             | 06/06/2026 | Consolidação final em documento SRS (IEEE 830)                  | 2.0     |

---

## 1. Introdução

Este documento constitui a Especificação de Requisitos de Software (SRS) do Sistema ENADE, elaborado em conformidade com o padrão IEEE 830. Seu propósito é registrar de forma estruturada, completa e rastreável todos os requisitos funcionais, não funcionais, regras de negócio e casos de uso que orientarão o desenvolvimento, validação e manutenção da plataforma.

### 1.1 Propósito do Documento

O presente documento tem por objetivo definir o escopo funcional e as restrições de qualidade do Sistema ENADE — uma plataforma web/mobile voltada ao apoio da preparação de estudantes de graduação para o Exame Nacional de Desempenho de Estudantes (ENADE). O SRS serve como contrato técnico entre a Equipe de TI (Kayo Gomes, Karlos Eduardo e Gustavo Lima) e as demais partes interessadas, garantindo alinhamento entre as necessidades pedagógicas e institucionais e a solução implementada.

### 1.2 Escopo do Produto

O Sistema ENADE é uma aplicação web responsiva que centraliza recursos de preparação para o ENADE, oferecendo banco de questões com filtros avançados, simulados cronometrados, resoluções em formato de mapa mental, fóruns de debate colaborativo e painéis analíticos de desempenho. A plataforma integra-se ao Sistema INEP para importação automática de questões oficiais e ao Sistema Acadêmico da instituição para autenticação e validação de vínculos.

O sistema **não abrange** funcionalidades de gestão financeira, emissão de certificados ou controle de frequência acadêmica.

### 1.3 Definições, Acrônimos e Abreviações

| Termo       | Definição                                                                     |
| ----------- | ------------------------------------------------------------------------------- |
| API RESTful | Interface de Programação baseada em arquitetura REST via HTTP                 |
| CDU         | Caso de Uso                                                                     |
| ENADE       | Exame Nacional de Desempenho de Estudantes                                      |
| ETL         | Extract, Transform, Load — processo de extração e carga de dados             |
| INEP        | Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira         |
| LGPD        | Lei Geral de Proteção de Dados Pessoais (Lei nº 13.709/2018)                 |
| MEC         | Ministério da Educação                                                       |
| NDE         | Núcleo Docente Estruturante                                                    |
| OAuth 2.0   | Protocolo de autorização delegada usado para autenticação via Google        |
| PO          | Product Owner — responsável pela visão e priorização do produto            |
| PWA         | Progressive Web App — aplicação web com comportamento similar a app nativo   |
| RF          | Requisito Funcional                                                             |
| RN          | Regra de Negócio                                                               |
| RNF         | Requisito Não Funcional                                                        |
| SRS         | Software Requirements Specification (Especificação de Requisitos de Software) |
| TLS         | Transport Layer Security — protocolo de criptografia de rede                   |
| UML         | Unified Modeling Language                                                       |

### 1.4 Visão Geral do Documento

O presente SRS está organizado em três seções principais. A Seção 1 (Introdução) apresenta o propósito, o escopo, as definições e as referências do documento. A Seção 2 (Descrição Geral) descreve o contexto do produto, as funções principais, o perfil dos usuários, as premissas e as restrições gerais. A Seção 3 (Requisitos Detalhados) especifica os requisitos funcionais, não funcionais, as regras de negócio e os casos de uso em sua totalidade.

---

## 2. Descrição Geral do Produto

### 2.1 Perspectiva do Produto

O Sistema ENADE é uma solução de software independente que opera em conjunto com dois sistemas externos: o Sistema INEP, fornecedor governamental de questões oficiais, e o Sistema Acadêmico da instituição de ensino, responsável pela validação de vínculos e credenciais dos usuários. A plataforma adota arquitetura cliente-servidor, com front-end desenvolvido em React, back-end em Node.js (API RESTful), banco de dados PostgreSQL e autenticação delegada via Google OAuth 2.0. Toda a infraestrutura é hospedada em ambiente de nuvem, com comunicação criptografada por TLS.

### 2.2 Funções do Produto

| Módulo                    | Funções                                                                                                                  |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Autenticação e Usuários | Cadastro e login via Google OAuth; validação de domínio institucional; atribuição automática de perfis.              |
| Banco de Questões         | Filtro avançado por palavra-chave, ano e área; exibição de enunciados e alternativas; registro de respostas.           |
| Mapas Mentais              | Visualização de resolução estruturada em mapa mental; alternância com resolução textual.                            |
| Simulados Cronometrados    | Geração dinâmica de simulados; cronômetro regressivo (3 min/questão); salvamento automático; correção automática. |
| Fórum de Debate           | Publicação e resposta em tópicos; moderação por professores e coordenação.                                          |
| Dashboard Analítico       | Taxas de acerto/erro agregadas por turma; ranking de questões mais erradas; filtros por turma.                            |
| Gestão Institucional      | Gerenciamento de usuários e cursos; cadastro e curadoria de questões; gestão de competências.                          |
| Integração INEP          | Sincronização automática e manual de questões oficiais com tratamento de erros e log de auditoria.                     |

### 2.3 Restrições do Produto

- **Tecnológicas:** o sistema deve ser implementado com React (front-end), Node.js (back-end), PostgreSQL (banco de dados) e Google OAuth 2.0 (autenticação), conforme decisões arquiteturais da equipe.
- **Segurança:** toda comunicação deve utilizar HTTPS/TLS; senhas locais não devem ser armazenadas; os dados do PostgreSQL devem residir em sub-rede isolada.
- **Privacidade:** o sistema deve estar em conformidade com a LGPD, garantindo anonimização de dados individuais nos painéis analíticos.
- **Compatibilidade:** a interface deve ser responsiva (Mobile-First) e compatível com as duas últimas versões dos navegadores Chrome, Firefox, Safari e Edge.
- **Disponibilidade:** uptime mínimo de 99,5% durante o período de preparação intensiva (agosto a novembro).
- **Integração:** a sincronização com o Sistema INEP depende da manutenção da política de dados abertos do INEP e da estabilidade da API governamental.

### 2.4 Características dos Usuários

| Perfil                      | Papel                                                                       | Nível Técnico            | Frequência de Uso |
| --------------------------- | --------------------------------------------------------------------------- | -------------------------- | ------------------ |
| Estudante de Graduação    | Usuário final — realiza simulados, filtra questões, participa de fóruns | Básico a intermediário   | Alta (diária)     |
| Professor                   | Mediador — participa de fóruns e analisa dashboards                       | Intermediário             | Média (semanal)   |
| Equipe de Professores (NDE) | Especialista — cadastra questões e gerencia competências                 | Intermediário a avançado | Média             |
| Coordenação do Curso      | Gestor — administra usuários, cursos e monitora métricas                 | Básico                    | Baixa (mensal)     |
| Sistema INEP                | Ator externo — provê questões oficiais via integração                  | N/A (sistema automatizado) | Baixa (agendada)   |
| Sistema Acadêmico          | Ator externo — valida credenciais e vínculos institucionais               | N/A (sistema automatizado) | Alta (por sessão) |

### 2.5 Premissas e Dependências

#### 2.5.1 Premissas

- A política de dados abertos do INEP permanece vigente, permitindo acesso ao banco histórico de questões.
- O provedor de nuvem (AWS, Azure ou GCP) garante escalabilidade horizontal automática.
- O Sistema Acadêmico da instituição expõe uma interface de integração (API ou barramento) para validação de matrículas e vínculos.
- Os usuários possuem e-mail institucional com domínio reconhecido pelo Google OAuth.

#### 2.5.2 Dependências

- API ou endpoint do Sistema INEP para sincronização de questões (CDU-07).
- Serviço Google OAuth 2.0 para autenticação federada (RF01, RNF05).
- Barramento ou API do Sistema Acadêmico para validação de credenciais e perfis (RF02, RF03).
- Provedor de nuvem para hospedagem do back-end (Node.js) e do banco de dados (PostgreSQL).

### 2.6 Distribuição de Requisitos

**Mapeamento de Stakeholders**

| Stakeholder                          | Papel                                                                       | Influência | Impacto |
| ------------------------------------ | --------------------------------------------------------------------------- | ----------- | ------- |
| Prof. Marcelo Bezerra                | Product Owner / Orientador — valida entregas e defende a visão do produto | Alta        | Alto    |
| Coordenação do Curso               | Cliente / Patrocinador — define diretrizes e avalia métricas gerais       | Alta        | Alto    |
| Professores do ENADE                 | Usuário Estratégico — monitora dashboards e media fóruns                | Média      | Alto    |
| Estudantes de Graduação            | Usuário Final — principal beneficiário das funcionalidades de estudo     | Baixa       | Alto    |
| Equipe de TI (Kayo, Karlos, Gustavo) | Desenvolvedores — implementam e mantêm o sistema                          | Alta        | Médio  |

---

## 3. Requisitos

### 3.1 Interfaces Externas

#### 3.1.1 Interfaces de Usuário

A interface deve ser 100% responsiva (Mobile-First), compatível com smartphones, tablets e desktops. Deve fornecer mensagens de erro amigáveis e feedback visual (spinners, alertas) para todas as ações assíncronas. Deve ser compatível com as duas últimas versões dos navegadores Chrome, Firefox, Safari e Microsoft Edge.

#### 3.1.2 Interfaces de Hardware

Não há interações diretas com dispositivos físicos específicos. O sistema acessa o hardware do usuário exclusivamente por meio do navegador web.

#### 3.1.3 Interfaces de Software

| Sistema Externo                     | Tipo de Integração                 | Finalidade                                                            |
| ----------------------------------- | ------------------------------------ | --------------------------------------------------------------------- |
| Sistema INEP                        | API/endpoint governamental           | Sincronização automática e manual de questões oficiais (CDU-07)   |
| Google OAuth 2.0                    | Protocolo de autenticação federada | Login e autenticação de usuários (RF01, RNF05)                     |
| Sistema Acadêmico da Instituição | API ou barramento de serviços       | Validação de matrículas, vínculos e perfis de acesso (RF02, RF03) |
| Provedor de Nuvem (AWS/Azure/GCP)   | Infraestrutura como serviço         | Hospedagem de back-end (Node.js) e banco de dados (PostgreSQL)        |

### 3.2 Funções

#### 3.2.1 Módulo de Autenticação e Usuários

| ID   | Descrição                                                                                                                                | Prioridade | CDU Relacionado |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- |
| RF01 | Permitir o login de estudantes e professores utilizando a integração com o Google OAuth.                                                 | Alta       | CDU-01          |
| RF02 | Validar o domínio de e-mail institucional durante o primeiro acesso para autorizar a entrada no sistema.                                  | Alta       | CDU-01          |
| RF03 | Atribuir automaticamente o nível de permissão (Estudante, Professor ou Coordenador) com base nos dados integrados do sistema acadêmico. | Alta       | CDU-01          |

#### 3.2.2 Módulo de Banco de Questões e Mapas Mentais

| ID   | Descrição                                                                                                                                | Prioridade | CDU Relacionado |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- |
| RF04 | Permitir ao usuário buscar questões do ENADE aplicando filtros simultâneos por: palavra-chave, ano de aplicação e área de conteúdo. | Alta       | CDU-02          |
| RF05 | Exibir o enunciado completo, imagens de apoio (se houver) e as alternativas de cada questão recuperada do banco.                          | Alta       | CDU-02          |
| RF06 | Exibir o mapa mental com a explicação estruturada da resposta correta após o estudante submeter sua tentativa de resolução.           | Alta       | CDU-03          |
| RF07 | Registrar a resposta assinalada pelo estudante no banco de dados para compor os cálculos estatísticos futuros.                           | Alta       | CDU-02 / CDU-03 |

#### 3.2.3 Módulo de Simulados Cronometrados

| ID   | Descrição                                                                                                                                           | Prioridade | CDU Relacionado |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- |
| RF08 | Gerar um simulado dinâmico com base na seleção de áreas de conhecimento escolhidas pelo estudante.                                                | Alta       | CDU-04          |
| RF09 | Calcular e exibir um cronômetro regressivo na tela de prova, considerando 3 minutos por questão incluída no simulado.                              | Média     | CDU-04          |
| RF10 | Salvar automaticamente em background a alternativa selecionada a cada avanço de questão, prevenindo perda de dados por fechamento acidental da aba. | Alta       | CDU-04          |
| RF11 | Submeter o simulado automaticamente para correção quando o cronômetro regressivo atingir o valor zero.                                             | Alta       | CDU-04          |
| RF12 | Exibir a nota final do simulado (acertos, erros e tempo total gasto) imediatamente após a sua submissão.                                            | Alta       | CDU-04          |

#### 3.2.4 Módulo de Fórum de Debate

| ID   | Descrição                                                                                                                               | Prioridade | CDU Relacionado |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- |
| RF13 | Permitir que os usuários autenticados publiquem comentários de texto em uma seção de fórum atrelada a cada questão do banco.        | Média     | CDU-05          |
| RF14 | Exibir os comentários em ordem cronológica de envio, identificando o nome e a tag de perfil (Estudante/Professor) do autor da mensagem. | Média     | CDU-05          |
| RF15 | Permitir que usuários com perfil de Professor ou Coordenador excluam comentários de qualquer usuário para fins de moderação.         | Baixa      | CDU-05          |

#### 3.2.5 Módulo de Painel Gerencial (Dashboard)

| ID   | Descrição                                                                                                                                      | Prioridade | CDU Relacionado |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- |
| RF16 | Gerar gráficos visuais contendo as taxas percentuais de acertos e erros agregadas dos estudantes, segmentadas por eixo de conteúdo curricular. | Alta       | CDU-06          |
| RF17 | Permitir que o professor filtre os dados exibidos no painel selecionando apenas as turmas com as quais possui vínculo ativo.                    | Alta       | CDU-06          |
| RF18 | Listar um ranking automático das 'Top 5 Questões com Maior Índice de Erros' da turma filtrada para direcionamento das aulas de revisão.      | Média     | CDU-06          |

#### 3.2.6 Regras de Negócio

##### 3.2.6.1 Autenticação e Acesso

| ID   | Descrição                                                                                                                          | Severidade | Origem                 |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------ | ---------- | ---------------------- |
| RN01 | O acesso via Google OAuth é restrito a usuários com e-mail de domínio institucional da universidade (ex.: @unifor.edu.br).        | Crítica   | Coordenação / LGPD   |
| RN02 | Um professor só pode visualizar painéis de turmas com as quais possui vínculo ativo. Apenas a Coordenação possui visão global. | Alta       | Coordenação do Curso |

##### 3.2.6.2 Banco de Questões

| ID   | Descrição                                                                                                                                                 | Severidade | Origem                             |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------------------------- |
| RN03 | Questões extraídas do INEP/ENADE são imutáveis: enunciado, alternativas e gabarito não podem ser editados ou excluídos por nenhum nível de usuário. | Crítica   | Base do INEP / Premissa de Projeto |
| RN04 | Cada questão deve estar categorizada em pelo menos uma Área de Conteúdo Curricular e um Ano de Edição do ENADE.                                        | Alta       | Equipe de TI / Professores         |

##### 3.2.6.3 Simulados e Cronometragem

| ID   | Descrição                                                                                                                                     | Severidade | Origem                              |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ----------------------------------- |
| RN05 | O tempo limite de um simulado cronometrado é calculado à razão de 3 minutos por questão incluída (ex.: 10 questões = 30 minutos).         | Média     | Condições Reais de Prova          |
| RN06 | Quando o cronômetro atingir zero, o sistema deve congelar a tela, salvar todas as respostas assinaladas e submeter automaticamente o simulado. | Alta       | Regra de Condição de Prova (INEP) |
| RN07 | O algoritmo de geração de simulados deve garantir a unicidade das questões dentro de uma mesma sessão de simulado.                          | Alta       | Qualidade de Software               |

##### 3.2.6.4 Mapas Mentais e Aprendizado Colaborativo

| ID   | Descrição                                                                                                                                                             | Severidade | Origem                     |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------------------------- |
| RN08 | Cada questão possui apenas um mapa mental oficial, validado pelo PO ou corpo docente autorizado antes de ser disponibilizado aos estudantes.                           | Alta       | Prof. Marcelo Bezerra (PO) |
| RN09 | Comentários do fórum são públicos para leitura, mas podem ser excluídos permanentemente por professores ou coordenação quando infringirem políticas de conduta. | Média     | Coordenação do Curso     |

##### 3.2.6.5 Painel Analítico e Métricas

| ID   | Descrição                                                                                                                                                                                 | Severidade | Origem                                 |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------------------------------------- |
| RN10 | Em conformidade com a LGPD, os painéis exibem apenas métricas de desempenho de forma agregada e percentual por turma. O desempenho individual de cada aluno não é exposto publicamente. | Alta       | LGPD / Comitê de Ética Institucional |

##### 3.2.6.6 Matriz de Rastreabilidade RN × RF

| Regra de Negócio              | Requisitos Funcionais Relacionados | Objetivo Garantido                             |
| ------------------------------ | ---------------------------------- | ---------------------------------------------- |
| RN01 — Domínio Institucional | RF01, RF02                         | Segurança e conformidade de acesso            |
| RN02 — Escopo de Visão       | RF17                               | Isolamento de dados confidenciais por docente  |
| RN03 — Imutabilidade INEP     | RF04, RF05                         | Fidelidade histórica ao exame real            |
| RN04 — Categorização        | RF04                               | Filtros precisos por área de conteúdo        |
| RN05 — Tempo Padrão          | RF09                               | Treinamento de gestão de tempo                |
| RN06 — Submissão Automática | RF11                               | Simulação fiel do encerramento real da prova |
| RN07 — Unicidade de Questões | RF08                               | Variedade de tópicos no treinamento           |
| RN08 — Mapa Mental Oficial    | RF06                               | Qualidade técnica do conteúdo visual         |
| RN09 — Moderação Fórum     | RF15                               | Ambiente acadêmico saudável e focado         |
| RN10 — Anonimização         | RF16, RF17, RF18                   | Conformidade com a LGPD                        |

#### 3.2.7 Especificação dos Casos de Uso

##### CDU-01 — Efetuar Cadastro e Login

| Campo                      | Detalhe                                                                                                 |
| -------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que o estudante crie uma conta no Sistema ENADE e realize o acesso autenticado à plataforma.  |
| **Tipo**             | Concreto                                                                                                |
| **Ator Primário**   | Estudante — ator que inicia o processo de cadastro ou login para acessar o sistema.                    |
| **Ator Secundário** | Sistema Acadêmico — sistema externo incluído para validação ou integração de dados do estudante. |
| **RFs Relacionados** | RF01, RF02, RF03                                                                                        |
| **Frequência**      | Alta — acionado a cada acesso ao sistema.                                                              |

**Pré-condições**

- O estudante deve ter acesso à internet e ao endereço do Sistema ENADE.
- Para login, o estudante deve possuir cadastro prévio no sistema.

**Fluxo Principal**

- P1. O estudante acessa a página inicial do Sistema ENADE.
- P2. O sistema exibe as opções de 'Cadastrar' e 'Entrar'.
- P3. O estudante seleciona a opção 'Entrar'.
- P4. O sistema exibe o formulário de login com campos de e-mail e senha.
- P5. O estudante preenche o e-mail e a senha e confirma o acesso.
- P6. O sistema valida as credenciais informadas.
- P7. O sistema autentica o estudante e redireciona para a tela principal.

**Fluxos Alternativos**

- A1. Estudante realiza cadastro pela primeira vez: seleciona 'Cadastrar', preenche nome, e-mail, senha, curso e instituição, confirma e o sistema cria a conta, exibindo mensagem de confirmação e redirecionando para a tela de login.

**Fluxos de Exceção**

- E1. Credenciais inválidas: exibe mensagem 'E-mail ou senha inválidos' e retorna ao formulário de login.
- E2. E-mail já cadastrado: exibe mensagem orientando o uso de outro e-mail ou recuperação de senha.
- E3. Campos obrigatórios não preenchidos: destaca os campos em branco e exibe mensagem de validação.

**Pós-condições**

- O estudante está autenticado no sistema e tem acesso às funcionalidades de seu perfil.
- Uma sessão ativa é criada para o estudante.

---

##### CDU-02 — Filtrar Banco de Dados

| Campo                      | Detalhe                                                                                                                                                                 |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que o estudante aplique filtros sobre o banco de questões do Sistema ENADE, refinando a seleção por área de conhecimento, ano, disciplina ou competência. |
| **Tipo**             | Concreto                                                                                                                                                                |
| **Ator Primário**   | Estudante — ator que inicia e opera a filtragem do banco de questões.                                                                                                 |
| **Ator Secundário** | Não se aplica.                                                                                                                                                         |
| **RFs Relacionados** | RF04, RF05, RF07                                                                                                                                                        |
| **Frequência**      | Alta — utilizado frequentemente para personalizar o estudo.                                                                                                            |

**Pré-condições**

- O estudante deve estar autenticado no Sistema ENADE.
- O banco de questões deve estar populado com questões sincronizadas.

**Fluxo Principal**

- P1. O estudante acessa a seção de banco de questões no sistema.
- P2. O sistema exibe a listagem de questões disponíveis com os filtros disponíveis.
- P3. O estudante seleciona um ou mais critérios de filtro (ano, área, disciplina, competência).
- P4. O estudante aplica os filtros selecionados.
- P5. O sistema processa os critérios e retorna as questões correspondentes.
- P6. O sistema exibe a listagem filtrada de questões.
- P7. O estudante visualiza e interage com as questões retornadas.

**Fluxos Alternativos**

- A1. Estudante limpa os filtros: seleciona 'Limpar filtros' e o sistema exibe a listagem completa.
- A2. Estudante salva combinação de filtros como favorito: nomeia e confirma a configuração para uso futuro.

**Fluxos de Exceção**

- E1. Nenhuma questão encontrada: exibe 'Nenhuma questão encontrada para os filtros selecionados' e retorna para nova seleção.
- E2. Filtros incompatíveis: exibe alerta de incompatibilidade e retorna para seleção de critérios.

**Pós-condições**

- O estudante visualiza a listagem filtrada.
- Os filtros são mantidos enquanto a sessão estiver ativa.

---

##### CDU-03 — Visualizar Resolução via Mapa Mental

| Campo                      | Detalhe                                                                                                                                                                  |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Objetivo**         | Permitir que o estudante visualize a resolução de uma questão em formato de mapa mental, facilitando a compreensão dos conceitos e conexões envolvidos na resposta. |
| **Tipo**             | Concreto                                                                                                                                                                 |
| **Ator Primário**   | Estudante — ator que solicita e consome a visualização da resolução em formato de mapa mental.                                                                      |
| **Ator Secundário** | Não se aplica.                                                                                                                                                          |
| **RFs Relacionados** | RF06                                                                                                                                                                     |
| **Frequência**      | Média — utilizado após tentativa de resolução de questões.                                                                                                         |

**Pré-condições**

- O estudante deve estar autenticado no Sistema ENADE.
- A questão selecionada deve possuir resolução associada em formato de mapa mental.

**Fluxo Principal**

- P1. O estudante acessa o banco de questões e seleciona uma questão.
- P2. O sistema exibe o enunciado completo e as opções de resposta.
- P3. O estudante seleciona a opção 'Visualizar resolução via mapa mental'.
- P4. O sistema carrega e exibe o mapa mental associado à resolução.
- P5. O estudante navega pelo mapa mental, expandindo e contraindo os nós de conteúdo.
- P6. O estudante conclui a visualização.

**Fluxos Alternativos**

- A1. Estudante alterna entre mapa mental e resolução textual: seleciona 'Ver resolução em texto' e pode retornar ao mapa mental.
- A2. Estudante expande um nó: clica e o sistema exibe detalhes, explicações ou referências associadas ao nó.

**Fluxos de Exceção**

- E1. Resolução em mapa mental não disponível: exibe mensagem e oferece visualização em formato textual.
- E2. Erro ao carregar o mapa mental: exibe mensagem de erro e oferece opção de tentar novamente.

**Pós-condições**

- O estudante visualizou a resolução em mapa mental.
- O acesso à resolução é registrado no histórico de atividades do estudante.

---

##### CDU-04 — Realizar Simulado Cronometrado

| Campo                      | Detalhe                                                                                                                                               |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que o estudante realize um simulado com questões do banco de dados do ENADE sob controle de tempo, simulando as condições reais do exame. |
| **Tipo**             | Concreto                                                                                                                                              |
| **Ator Primário**   | Estudante — ator que configura, inicia e responde ao simulado cronometrado.                                                                          |
| **Ator Secundário** | Não se aplica.                                                                                                                                       |
| **RFs Relacionados** | RF08, RF09, RF10, RF11, RF12                                                                                                                          |
| **Frequência**      | Alta — utilizado regularmente como ferramenta de preparação.                                                                                       |

**Pré-condições**

- O estudante deve estar autenticado no Sistema ENADE.
- O banco de questões deve estar populado com ao menos uma questão disponível.

**Fluxo Principal**

- P1. O estudante acessa a funcionalidade 'Simulado Cronometrado'.
- P2. O sistema exibe as opções de configuração (número de questões, área, tempo).
- P3. O estudante define as configurações e inicia o simulado.
- P4. O sistema monta a lista de questões e inicia o cronômetro.
- P5. O sistema exibe a primeira questão com o cronômetro em execução.
- P6. O estudante lê o enunciado e seleciona uma alternativa.
- P7. O estudante avança para a próxima questão.
- P8. Os passos P6 e P7 repetem-se até o estudante responder todas as questões ou o tempo se esgotar.
- P9. O estudante finaliza o simulado ou o sistema encerra ao término do tempo.
- P10. O sistema calcula e exibe o resultado com percentual de acertos e gabarito.

**Fluxos Alternativos**

- A1. Estudante pula uma questão: registra como não respondida e avança para a próxima.
- A2. Estudante revisa questões antes de finalizar: navega pelo painel de questões respondidas e não respondidas, altera ou confirma respostas.

**Fluxos de Exceção**

- E1. Tempo esgotado: o sistema encerra automaticamente, registra as respostas até aquele momento e exibe o resultado.
- E2. Perda de conexão: salva o estado do simulado em memória temporária e oferece retomada ao restabelecer conexão.
- E3. Questões insuficientes: informa a quantidade disponível e solicita confirmação para prosseguir.

**Pós-condições**

- O resultado do simulado é registrado no histórico de desempenho do estudante.
- As questões respondidas e os erros ficam disponíveis para revisão posterior.

---

##### CDU-05 — Participar de Fórum de Debate

| Campo                      | Detalhe                                                                                                                                                                                          |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Objetivo**         | Permitir que estudantes e professores interajam em fóruns de debate vinculados a questões ou temas do ENADE, trocando argumentos, esclarecendo dúvidas e enriquecendo o aprendizado coletivo. |
| **Tipo**             | Concreto                                                                                                                                                                                         |
| **Ator Primário**   | Estudante — ator que inicia a interação ao acessar e publicar no fórum.                                                                                                                      |
| **Ator Secundário** | Professor — ator que participa do fórum, podendo responder, moderar e orientar discussões.                                                                                                    |
| **RFs Relacionados** | RF13, RF14, RF15                                                                                                                                                                                 |
| **Frequência**      | Média — regularmente durante períodos de preparação para o ENADE.                                                                                                                           |

**Pré-condições**

- O ator deve estar autenticado no Sistema ENADE.
- Deve existir ao menos um fórum de debate criado e ativo no sistema.

**Fluxo Principal**

- P1. O estudante acessa a seção 'Fórum de Debate' no sistema.
- P2. O sistema exibe a lista de tópicos de debate disponíveis.
- P3. O estudante seleciona um tópico de interesse.
- P4. O sistema exibe o tópico com todas as postagens existentes.
- P5. O estudante redige uma nova postagem ou resposta no campo de texto.
- P6. O estudante publica a postagem.
- P7. O sistema valida o conteúdo e registra a postagem no tópico.
- P8. O sistema exibe a postagem publicada para todos os participantes.

**Fluxos Alternativos**

- A1. Professor responde a uma postagem: seleciona 'Responder', redige e publica; o sistema associa a resposta à postagem original.
- A2. Ator cria um novo tópico: preenche título, descrição e vínculo opcional com questão; sistema registra e exibe na listagem.
- A3. Ator edita uma postagem própria: campo de edição habilitado; sistema atualiza e registra histórico de edição.

**Fluxos de Exceção**

- E1. Postagem com conteúdo vazio: exibe validação e retorna ao campo de texto.
- E2. Tópico encerrado ou arquivado: exibe em modo somente leitura sem opção de publicar.
- E3. Postagem excede o limite de caracteres: exibe mensagem com o limite e quantidade excedida.

**Pós-condições**

- A postagem é registrada e visível a todos os participantes autorizados.
- A participação é contabilizada para o painel de desempenho do fórum.

---

##### CDU-06 — Visualizar Painel de Desempenho do Fórum de Debate

| Campo                      | Detalhe                                                                                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que estudantes e professores acompanhem métricas de engajamento e desempenho relacionadas à participação nos fóruns de debate do Sistema ENADE. |
| **Tipo**             | Concreto                                                                                                                                                      |
| **Ator Primário**   | Estudante — ator que acessa o painel para acompanhar seu próprio desempenho.                                                                                |
| **Ator Secundário** | Professor — ator que acessa o painel para monitorar o engajamento coletivo da turma.                                                                         |
| **RFs Relacionados** | RF16, RF17, RF18                                                                                                                                              |
| **Frequência**      | Média — consultado periodicamente para acompanhar evolução no engajamento.                                                                                |

**Pré-condições**

- O ator deve estar autenticado no Sistema ENADE.
- Deve haver ao menos um registro de participação em fórum para o ator ou para a turma.

**Fluxo Principal**

- P1. O estudante acessa a seção 'Painel de Desempenho do Fórum'.
- P2. O sistema coleta e processa os dados de participação do estudante.
- P3. O sistema exibe o painel com métricas de engajamento (postagens, tópicos, respostas, curtidas).
- P4. O estudante navega pelas métricas exibidas.
- P5. O estudante seleciona filtro de período ou tópico.
- P6. O sistema atualiza o painel conforme os filtros.

**Fluxos Alternativos**

- A1. Professor visualiza painel coletivo: seleciona 'Visualizar turma' e o sistema exibe métricas agregadas de todos os estudantes vinculados.
- A2. Estudante exporta relatório: gera em PDF ou CSV e disponibiliza para download.

**Fluxos de Exceção**

- E1. Sem dados de participação: exibe 'Você ainda não possui participações registradas' e sugere acesso ao CDU-05.
- E2. Falha no carregamento: exibe mensagem de erro e oferece opção de recarregar.

**Pós-condições**

- O ator visualizou as métricas de desempenho.
- Os dados exibidos refletem o estado mais recente registrado.

---

##### CDU-07 — Sincronizar Questões do INEP

| Campo                      | Detalhe                                                                                                                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que o Sistema ENADE obtenha e atualize automaticamente o banco de questões a partir do Sistema INEP, mantendo o acervo atualizado para uso pelos estudantes. |
| **Tipo**             | Concreto                                                                                                                                                               |
| **Ator Primário**   | Sistema INEP — sistema externo que provê questões oficiais por meio de integração.                                                                                |
| **Ator Secundário** | Coordenação — ator que pode acionar manualmente a sincronização ou monitorar seu status.                                                                          |
| **RFs Relacionados** | RF04, RF05 (indiretamente via CDU-11)                                                                                                                                  |
| **Frequência**      | Baixa — acionada por agendamento periódico ou manualmente pela coordenação.                                                                                        |

**Pré-condições**

- O Sistema ENADE deve possuir configuração de integração ativa com o Sistema INEP.
- As credenciais de acesso ao Sistema INEP devem estar válidas e configuradas.

**Fluxo Principal**

- P1. O sistema dispara a sincronização automaticamente conforme agendamento configurado.
- P2. O sistema realiza a autenticação junto ao Sistema INEP.
- P3. O Sistema INEP confirma a autenticação e disponibiliza o endpoint de questões.
- P4. O sistema solicita as questões novas ou atualizadas desde a última sincronização.
- P5. O Sistema INEP retorna o conjunto de questões conforme solicitado.
- P6. O sistema valida e processa os dados recebidos.
- P7. O sistema insere questões novas e atualiza existentes no banco de dados local.
- P8. O sistema registra o log da sincronização com data, hora e quantidade processada.

**Fluxos Alternativos**

- A1. Coordenação aciona sincronização manualmente: acessa painel, confirma a ação e o sistema executa a partir do P2.
- A2. Sincronização parcial por período: coordenação informa intervalo de datas e o sistema filtra a solicitação ao INEP.

**Fluxos de Exceção**

- E1. Falha na autenticação: registra erro, notifica a coordenação e encerra a tentativa.
- E2. Tempo esgotado ou indisponibilidade do INEP: registra falha e agenda nova tentativa automaticamente.
- E3. Dados com formato inválido: descarta itens inválidos, registra no log e notifica a coordenação.

**Pós-condições**

- O banco de questões está atualizado com os dados do INEP.
- Registro de log armazenado para auditoria.

---

##### CDU-08 — Gerenciar Usuários

| Campo                      | Detalhe                                                                                                                                                                               |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que a coordenação cadastre, edite, ative, desative e exclua usuários do Sistema ENADE, controlando os perfis de acesso de estudantes, professores e outros coordenadores. |
| **Tipo**             | Concreto                                                                                                                                                                              |
| **Ator Primário**   | Coordenação — ator responsável por administrar os usuários do sistema.                                                                                                           |
| **Ator Secundário** | Não se aplica.                                                                                                                                                                       |
| **RFs Relacionados** | RF03                                                                                                                                                                                  |
| **Frequência**      | Baixa a média — principalmente no início de semestres.                                                                                                                             |

**Pré-condições**

- A coordenação deve estar autenticada com perfil de administrador.

**Fluxo Principal**

- P1. A coordenação acessa o painel de administração e seleciona 'Gerenciar Usuários'.
- P2. O sistema exibe a listagem de usuários com filtros de busca.
- P3. A coordenação localiza o usuário desejado por busca ou navegação.
- P4. A coordenação seleciona a ação: cadastrar, editar, ativar/desativar ou excluir.
- P5. O sistema exibe o formulário ou confirmação correspondente.
- P6. A coordenação preenche ou confirma as informações.
- P7. O sistema valida os dados e executa a operação.
- P8. O sistema exibe mensagem de confirmação do resultado.

**Fluxos Alternativos**

- A1. Cadastro de novo usuário: preenche nome, e-mail, perfil, curso e instituição; sistema cria a conta e envia credenciais por e-mail.
- A2. Edição de dados: altera os campos necessários; sistema atualiza o cadastro.
- A3. Ativação ou desativação: confirma a ação; sistema altera o status de acesso.

**Fluxos de Exceção**

- E1. E-mail já cadastrado: exibe 'Este e-mail já está cadastrado para outro usuário'.
- E2. Exclusão com vínculos ativos: alerta sobre dados vinculados e sugere desativação como alternativa.
- E3. Campos obrigatórios não preenchidos: destaca campos e exibe validação.

**Pós-condições**

- Usuário criado, atualizado, ativado, desativado ou excluído.
- Registro de auditoria documenta a operação, o ator e a data/hora.

---

##### CDU-09 — Gerenciar Cursos

| Campo                      | Detalhe                                                                                                                                                                          |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que a coordenação cadastre, edite, ative e desative cursos no Sistema ENADE, associando-os aos usuários e às questões do banco de dados por área de conhecimento. |
| **Tipo**             | Concreto                                                                                                                                                                         |
| **Ator Primário**   | Coordenação — ator que administra os cursos cadastrados no sistema.                                                                                                           |
| **Ator Secundário** | Não se aplica.                                                                                                                                                                  |
| **RFs Relacionados** | RF03 (indiretamente, via perfis e turmas)                                                                                                                                        |
| **Frequência**      | Baixa — início de semestres ou criação/encerramento de cursos.                                                                                                               |

**Pré-condições**

- A coordenação deve estar autenticada com perfil de administrador.

**Fluxo Principal**

- P1. A coordenação acessa o painel e seleciona 'Gerenciar Cursos'.
- P2. O sistema exibe a listagem de cursos com opções de busca e filtro.
- P3. A coordenação localiza o curso desejado ou opta por criar um novo.
- P4. A coordenação seleciona a ação: cadastrar, editar, ativar ou desativar.
- P5. O sistema exibe o formulário ou confirmação correspondente.
- P6. A coordenação preenche ou confirma as informações.
- P7. O sistema valida e executa a operação.
- P8. O sistema exibe mensagem de confirmação.

**Fluxos Alternativos**

- A1. Cadastro de novo curso: preenche nome, código MEC, área, instituição e status; sistema valida e registra.
- A2. Edição de dados: altera campos e sistema atualiza o cadastro.
- A3. Vínculo de usuários ao curso: seleciona usuários disponíveis e sistema associa ao curso.

**Fluxos de Exceção**

- E1. Nome do curso já cadastrado para a mesma instituição: exibe mensagem e retorna ao formulário.
- E2. Desativação com usuários ativos: exibe alerta e permite decisão de prosseguir ou cancelar.
- E3. Campos obrigatórios não preenchidos: destaca campos e exibe validação.

**Pós-condições**

- Curso criado, atualizado, ativado ou desativado.
- Questões associadas automaticamente com base na área de conhecimento cadastrada.

---

##### CDU-10 — Gerenciar Competências das Questões

| Campo                      | Detalhe                                                                                                                                                                            |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que a equipe de professores cadastre, edite, associe e remova competências vinculadas às questões do banco de dados, garantindo a correta classificação pedagógica. |
| **Tipo**             | Concreto                                                                                                                                                                           |
| **Ator Primário**   | Equipe de Professores — ator responsável pela gestão das competências.                                                                                                         |
| **Ator Secundário** | Coordenação — pode consultar as competências para fins de supervisão pedagógica.                                                                                             |
| **RFs Relacionados** | RF04 (indiretamente, via filtros de competência)                                                                                                                                  |
| **Frequência**      | Baixa — após sincronização com o INEP ou revisão pedagógica.                                                                                                                 |

**Pré-condições**

- A equipe de professores deve estar autenticada com perfil de professor.
- O banco de questões deve estar populado com ao menos uma questão.

**Fluxo Principal**

- P1. O professor acessa o painel e seleciona 'Gerenciar Competências das Questões'.
- P2. O sistema exibe a listagem de competências com filtros disponíveis.
- P3. O professor seleciona a ação: cadastrar, editar, associar ou remover.
- P4. O sistema exibe o formulário ou confirmação correspondente.
- P5. O professor preenche ou confirma as informações.
- P6. O sistema valida e executa a operação.
- P7. O sistema exibe mensagem de confirmação.

**Fluxos Alternativos**

- A1. Cadastro de nova competência: preenche nome, descrição, área e nível; sistema valida e registra.
- A2. Associação de competências a questões: seleciona questões e competências; sistema registra os vínculos.
- A3. Edição de competência: altera campos e sistema propaga alteração para todas as questões vinculadas.

**Fluxos de Exceção**

- E1. Nome de competência já existente na mesma área: exibe mensagem e retorna ao formulário.
- E2. Remoção com questões vinculadas: exibe alerta com quantidade vinculada e permite decisão.
- E3. Campos obrigatórios não preenchidos: destaca campos e exibe validação.

**Pós-condições**

- Competência criada, atualizada, associada ou removida.
- Questões vinculadas refletem imediatamente as competências atualizadas nos filtros.

---

##### CDU-11 — Cadastrar Questões

| Campo                      | Detalhe                                                                                                                                                                                                                          |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Objetivo**         | Permitir que a equipe de professores cadastre manualmente novas questões no banco de dados, aproveitando o acervo do INEP ou criando-as originalmente, garantindo ampliação e curadoria do banco disponível para estudantes. |
| **Tipo**             | Concreto                                                                                                                                                                                                                         |
| **Ator Primário**   | Equipe de Professores — ator responsável por cadastrar e revisar questões.                                                                                                                                                    |
| **Ator Secundário** | Sistema INEP — sistema externo incluído via CDU-07 que fornece questões oficiais como base de referência.                                                                                                                    |
| **RFs Relacionados** | RF04, RF05, RF06 (indiretamente via banco de questões)                                                                                                                                                                          |
| **Frequência**      | Média — periodicamente após atualizações do banco INEP ou início de semestres.                                                                                                                                             |

**Pré-condições**

- A equipe de professores deve estar autenticada com perfil de professor.
- O CDU-07 deve ter sido executado ao menos uma vez para que o banco do INEP esteja disponível como referência.

**Fluxo Principal**

- P1. O professor acessa o painel e seleciona 'Cadastrar Questões'.
- P2. O sistema exibe as opções: 'Criar questão original' ou 'Importar do banco INEP'.
- P3. O professor seleciona 'Importar do banco INEP'.
- P4. O sistema executa o include do CDU-07 para garantir que o acervo do INEP esteja atualizado.
- P5. O sistema exibe o acervo sincronizado com filtros por área, ano e competência.
- P6. O professor seleciona uma ou mais questões.
- P7. O sistema pré-preenche o formulário com os dados da questão importada.
- P8. O professor revisa e complementa os dados.
- P9. O professor confirma o cadastro.
- P10. O sistema valida e registra a questão no banco do Sistema ENADE.
- P11. O sistema exibe 'Questão cadastrada com sucesso'.

**Fluxos Alternativos**

- A1. Criação de questão original: formulário em branco com enunciado, alternativas (mín. 4), gabarito, área, dificuldade, competências e referências bibliográficas; suporte a imagens e fórmulas.
- A2. Cadastro em lote a partir do INEP: seleção de múltiplas questões; sistema processa e exibe relatório com acertos e erros de importação.
- A3. Edição pós-cadastro: professor edita questão recém-cadastrada e confirma ajustes.

**Fluxos de Exceção**

- E1. Banco do INEP indisponível: exibe mensagem e oferece a opção de criar questão original.
- E2. Questão já existente no banco local: exibe alerta e permite manter ou sobrescrever.
- E3. Campos obrigatórios não preenchidos: destaca campos e exibe validação.
- E4. Gabarito não informado: exibe 'É obrigatório indicar a alternativa correta antes de salvar'.

**Pós-condições**

- Questão registrada e disponível para CDU-02, CDU-03 e CDU-04.
- Competências vinculadas conforme CDU-10.
- Registro de cadastro documenta professor, origem e data/hora.

#### 3.2.8 Matriz de Rastreabilidade Global

| CDU    | Nome                                      | RFs                          | RNs              |
| ------ | ----------------------------------------- | ---------------------------- | ---------------- |
| CDU-01 | Efetuar Cadastro e Login                  | RF01, RF02, RF03             | RN01             |
| CDU-02 | Filtrar Banco de Dados                    | RF04, RF05, RF07             | RN03, RN04       |
| CDU-03 | Visualizar Resolução via Mapa Mental    | RF06                         | RN08             |
| CDU-04 | Realizar Simulado Cronometrado            | RF08, RF09, RF10, RF11, RF12 | RN05, RN06, RN07 |
| CDU-05 | Participar de Fórum de Debate            | RF13, RF14, RF15             | RN09             |
| CDU-06 | Visualizar Painel de Desempenho do Fórum | RF16, RF17, RF18             | RN02, RN10       |
| CDU-07 | Sincronizar Questões do INEP             | RF04, RF05 (ind.)            | RN03             |
| CDU-08 | Gerenciar Usuários                       | RF03                         | RN01, RN02       |
| CDU-09 | Gerenciar Cursos                          | RF03 (ind.)                  | RN02             |
| CDU-10 | Gerenciar Competências das Questões     | RF04 (ind.)                  | RN04             |
| CDU-11 | Cadastrar Questões                       | RF04, RF05, RF06 (ind.)      | RN03, RN04, RN08 |

### 3.3 Qualidade de Serviço

#### 3.3.1 Desempenho

| ID    | Descrição                                                                                                                                | Justificativa                                                                      |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| RNF01 | O tempo de resposta da API (Node.js) para consultas simples ao banco de questões não deve exceder 500 ms em condições normais de rede. | Garantir fluidez para o estudante em simulados com tempo controlado.               |
| RNF02 | O sistema deve suportar até 500 acessos simultâneos durante períodos de pico sem degradação acima de 2 segundos.                      | Assegurar estabilidade quando turmas inteiras acessarem o simulado ao mesmo tempo. |
| RNF03 | A renderização inicial das páginas no front-end (React) deve ocorrer em menos de 3 segundos em conexões de banda larga padrão.        | Evitar abandono do sistema por carregamento demorado.                              |

#### 3.3.2 Segurança

| ID    | Descrição                                                                                                                        | Justificativa                                                            |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| RNF04 | A comunicação entre front-end, API RESTful e banco de dados deve ser obrigatoriamente criptografada via HTTPS/TLS.               | Proteger dados acadêmicos e credenciais contra interceptação na rede. |
| RNF05 | O sistema não deve armazenar senhas locais; toda autenticação deve ser delegada ao Google OAuth 2.0.                            | Minimizar riscos de vazamento de credenciais.                            |
| RNF06 | O banco de dados (PostgreSQL) deve possuir rotinas automatizadas de backup diário incremental, com retenção mínima de 30 dias. | Garantir recuperação de dados em caso de falha severa.                 |

#### 3.3.3 Confiabilidade

| ID    | Descrição                                                                                             | Justificativa                                                                  |
| ----- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| RNF10 | A API RESTful deve implementar tratamento global de exceções, nunca expondo a stack trace ao cliente. | Manter o profissionalismo do sistema e evitar exposição de vulnerabilidades. |

#### 3.3.4 Disponibilidade

| ID    | Descrição                                                                                                      | Justificativa                                                                          |
| ----- | ---------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| RNF09 | O sistema deve garantir uptime de 99,5% durante os meses de preparação ativa para o ENADE (agosto a novembro). | Evitar indisponibilidade nos momentos críticos de uso pelos professores e estudantes. |

#### 3.3.5 Observabilidade

| ID | Descrição | Justificativa |
|----|-----------|---------------|
| RNF07 | A interface deve ser 100% responsiva, adaptando-se automaticamente a smartphones, tablets e desktops (Mobile-First). | Cumprir a restrição de interface portável única (web/mobile). |
| RNF08 | O sistema deve fornecer mensagens de erro amigáveis e retorno visual (indicadores de carregamento, alertas) para todas as ações assíncronas. | Melhorar a experiência do usuário e reduzir a frustração dos estudantes. |
| RNF11 | O front-end deve ser compatível com as duas últimas versões de Chrome, Firefox, Safari e Microsoft Edge. | Garantir que nenhum estudante seja impedido de acessar a plataforma por limitação de navegador. |
| RNF12 | O código-fonte do back-end e front-end deve seguir padrões de formatação (verificação de estilo e formatação automática) para JavaScript/TypeScript. | Facilitar a manutenção e a legibilidade do código pela Equipe de TI ao longo das sprints. |

#### 3.3.6 Observabilidade

Não especificado na versão atual do documento. A definir em iterações futuras.

### 3.4 Conformidade

O sistema deve estar em conformidade com:

- **LGPD (Lei nº 13.709/2018):** painéis analíticos devem exibir apenas métricas agregadas e percentuais por turma, garantindo anonimização dos dados individuais dos estudantes (RN10).
- **IEEE Std 830-1998:** o presente SRS segue a estrutura recomendada por este padrão.
- **Política de Dados Abertos do INEP:** a integração com o banco de questões oficiais depende da manutenção desta política governamental.

### 3.5 Design e Implementação

#### 3.5.1 Instalação

O sistema é hospedado em ambiente de nuvem (AWS, Azure ou GCP). Não há instalação local pelo usuário final — o acesso ocorre exclusivamente via navegador web.

#### 3.5.2 Construção e Entrega

O código-fonte do back-end e front-end deve seguir padrões de formatação (Linting e Prettier) para JavaScript/TypeScript (RNF12).

#### 3.5.3 Distribuição

Arquitetura cliente-servidor hospedada em nuvem. O banco de dados PostgreSQL deve residir em sub-rede isolada. O provedor de nuvem deve garantir escalabilidade horizontal automática.

#### 3.5.4 Manutenibilidade

O código-fonte deve seguir padrões de formatação (Linting e Prettier) para facilitar a manutenção e legibilidade pela Equipe de TI ao longo das sprints (RNF12).

#### 3.5.5 Reusabilidade

A API RESTful (Node.js) é o componente central de integração, podendo ser reutilizada por futuras interfaces ou módulos adicionais.

#### 3.5.6 Portabilidade

O front-end deve ser compatível com as duas últimas versões de Chrome, Firefox, Safari e Microsoft Edge (RNF11). A interface deve ser 100% responsiva, adaptando-se a smartphones, tablets e desktops — Mobile-First (RNF07).

#### 3.5.7 Custo

Não especificado na versão atual do documento.

#### 3.5.8 Prazo

O documento foi consolidado em versão 2.0 em 06/06/2026. Demais marcos a definir conforme cronograma de sprints.

#### 3.5.9 Prova de Conceito

Não aplicável na versão atual do documento.

#### 3.5.10 Gerenciamento de Mudanças

Alterações ao presente SRS devem ser registradas no Histórico de Versões com data, descrição da mudança, autor e nova versão.

---

## 4. Verificação

| Requirement ID | Verification Method                          | Test/Artifact Link | Status    | Evidence |
| -------------- | -------------------------------------------- | ------------------ | --------- | -------- |
| RF01           | Teste funcional (login via Google OAuth)     | CDU-01             | A definir |          |
| RF02           | Teste funcional (validação de domínio)    | CDU-01             | A definir |          |
| RF03           | Teste funcional (atribuição de perfil)     | CDU-01, CDU-08     | A definir |          |
| RF04           | Teste funcional (filtros no banco)           | CDU-02             | A definir |          |
| RF05           | Teste funcional (exibição de enunciado)    | CDU-02             | A definir |          |
| RF06           | Teste funcional (mapa mental)                | CDU-03             | A definir |          |
| RF07           | Teste de integração (registro de resposta) | CDU-02/CDU-03      | A definir |          |
| RF08           | Teste funcional (geração de simulado)      | CDU-04             | A definir |          |
| RF09           | Teste funcional (cronômetro regressivo)     | CDU-04             | A definir |          |
| RF10           | Teste funcional (auto-save)                  | CDU-04             | A definir |          |
| RF11           | Teste funcional (submissão automática)     | CDU-04             | A definir |          |
| RF12           | Teste funcional (exibição de resultado)    | CDU-04             | A definir |          |
| RF13           | Teste funcional (publicação no fórum)     | CDU-05             | A definir |          |
| RF14           | Teste funcional (ordem cronológica)         | CDU-05             | A definir |          |
| RF15           | Teste funcional (moderação)                | CDU-05             | A definir |          |
| RF16           | Teste funcional (gráficos de desempenho)    | CDU-06             | A definir |          |
| RF17           | Teste funcional (filtro por turma)           | CDU-06             | A definir |          |
| RF18           | Teste funcional (ranking de erros)           | CDU-06             | A definir |          |
| RNF01          | Teste de desempenho (latência API ≤ 500ms) | —                 | A definir |          |
| RNF02          | Teste de carga (500 usuários simultâneos)  | —                 | A definir |          |
| RNF03          | Teste de desempenho (carregamento ≤ 3s)     | —                 | A definir |          |
| RNF04          | Inspeção/auditoria (HTTPS/TLS ativo)       | —                 | A definir |          |
| RNF05          | Inspeção (ausência de senhas locais)      | —                 | A definir |          |
| RNF06          | Inspeção (backup diário/30 dias)          | —                 | A definir |          |
| RNF07          | Teste de interface (responsividade)          | —                 | A definir |          |
| RNF08          | Teste de usabilidade (feedback visual)       | —                 | A definir |          |
| RNF09          | Monitoramento (uptime 99,5%)                 | —                 | A definir |          |
| RNF10          | Teste de exceção (sem stack trace)         | —                 | A definir |          |
| RNF11          | Teste de compatibilidade (4 navegadores)     | —                 | A definir |          |
| RNF12          | Inspeção de código (Linting/Prettier)     | —                 | A definir |          |

---

## 5. Apêndices

### Apêndice A — Glossário de Termos

| Termo / Sigla          | Definição                                                                                | Fonte                     |
| ---------------------- | ------------------------------------------------------------------------------------------ | ------------------------- |
| API RESTful            | Arquitetura central do sistema que conecta o banco de dados aos aplicativos clientes.      | Documento de Visão / RNF |
| Dashboard              | Painel com gráficos de taxa de acertos/erros dos alunos, segmentado por conteúdo.        | Documento de Visão       |
| Domínio Institucional | Sufixo de e-mail da universidade (ex.: @edu.br) usado para restringir acessos.             | Regras de Negócio        |
| ENADE                  | Exame Nacional de Desempenho de Estudantes.                                                | Documento de Visão       |
| Google OAuth           | Protocolo de autorização que delega autenticação sem armazenar senhas locais.          | RN / RNF                  |
| HTTPS/TLS              | Protocolos de criptografia obrigatórios para dados trafegados entre usuário e servidor.  | RNF                       |
| INEP                   | Instituto responsável pelos dados públicos e banco de questões oficiais.                | Documento de Visão       |
| LGPD                   | Lei Geral de Proteção de Dados — exige anonimização de dados individuais em painéis. | Regras de Negócio        |
| Mapa Mental            | Recurso visual com explicação estruturada da resposta correta de uma questão.           | Documento de Visão / RF  |
| Mobile-First           | Abordagem de design iniciada para telas de celulares, depois adaptada para desktops.       | RNF                       |
| Node.js                | Ambiente de execução JavaScript usado para o back-end (API RESTful).                     | RNF                       |
| PO (Product Owner)     | Responsável por definir a visão do produto, priorizar o backlog e validar entregas.      | Lista de Stakeholders     |
| PostgreSQL             | SGBD relacional usado para persistir os dados do sistema.                                  | RNF                       |
| React                  | Biblioteca usada para construir a interface de usuário responsiva (front-end).            | RNF                       |
| Simulado Cronometrado  | Prova simulada com controle de tempo regressivo em condições reais de exame.             | Documento de Visão       |
| Sprint                 | Ciclo de desenvolvimento ao fim do qual entregas são feitas e validadas.                  | Lista de Stakeholders     |
| Stakeholder            | Pessoa ou grupo impactado pelo projeto.                                                    | Lista de Stakeholders     |
| Timeout                | Esgotamento do tempo do simulado, causando congelamento e submissão automática.          | Regras de Negócio        |
| Uptime                 | Tempo em que o sistema está operacional (meta: 99,5% no período de preparação).        | RNF                       |
