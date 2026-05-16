# 📖 Glossário de Termos do Projeto ENADE

> Documento destinado a registrar e padronizar os termos, siglas e jargões relevantes do projeto do aplicativo auxiliar de preparação para o ENADE.

## Instruções

- Liste todos os termos, siglas ou expressões relevantes para o projeto.
- Use definições claras, objetivas e sem jargões desnecessários.
- Sempre que possível, cite a fonte ou contexto do termo.
- Atualize o glossário continuamente durante o projeto.

## Histórico de Versões

| Data       | Versão | Descrição                                       | Autor                     |
| ---------- | ------- | ----------------------------------------------- | ------------------------- |
| 01/05/2026 | 1.0     | Criação e atualização inicial do glossário.     | Kayo Gomes & Karlos Sousa |
| 16/05/2026 | 1.1     | Inclusão de termos técnicos (RN, RF e RNF).     | Karlos Eduardo             |

## Glossário do Projeto

| Termo/Sigla                             | Definição                                                                                                                             | Fonte/Observação                 |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| **API RESTful** | Arquitetura central do sistema que conectará o banco de dados aos aplicativos clientes (Web e Mobile).                                | Documento de Visão / RNF         |
| **Dashboard / Painel Analítico** | Painel de gerenciamento web focado em exibir gráficos de taxa de acertos e erros dos alunos, segmentado por conteúdo.               | Documento de Visão               |
| **Domínio Institucional** | Sufixo do endereço de e-mail pertencente à universidade (ex: `@edu.br`), utilizado para restringir e autorizar acessos.               | Regras de Negócio (RN)           |
| **ENADE** | Exame Nacional de Desempenho de Estudantes. É o alvo central do sistema de preparação proposto.                                       | Documento de Visão               |
| **Google OAuth** | Protocolo de autorização utilizado para delegar a autenticação de usuários de forma segura, sem armazenar senhas localmente.          | Regras de Negócio / RNF          |
| **HTTPS/TLS** | Protocolos de segurança obrigatórios para garantir a criptografia dos dados trafegados entre o usuário e o servidor.                  | Requisitos Não Funcionais (RNF)  |
| **INEP** | Instituto responsável pelos dados públicos e banco de questões originais que alimentarão o sistema.                                 | Documento de Visão               |
| **LGPD** | Lei Geral de Proteção de Dados. Exige a anonimização de dados individuais em painéis analíticos expostos a terceiros.                 | Regras de Negócio (RN)           |
| **Mapa Mental** | Recurso visual que oferece uma explicação estruturada da resposta correta de uma questão, permitindo fixação rápida do aluno.   | Documento de Visão / RF          |
| **Matriz de Rastreabilidade** | Tabela que correlaciona Regras de Negócio e Requisitos Funcionais, garantindo a consistência do escopo do projeto.                    | Regras de Negócio (RN)           |
| **Mobile-First** | Abordagem de design em que a interface é desenhada primeiro para telas de celulares e depois adaptada para computadores.              | Requisitos Não Funcionais (RNF)  |
| **Node.js** | Ambiente de execução JavaScript utilizado para construir a API RESTful (Back-end) do sistema.                                         | Requisitos Não Funcionais (RNF)  |
| **PO (Product Owner)** | Papel responsável por definir a visão do produto, priorizar o backlog e validar entregas (representado pelo Prof. Marcelo Bezerra). | Lista de Stakeholders            |
| **PostgreSQL** | Sistema de gerenciamento de banco de dados relacional utilizado para persistir dados estruturados e os arquivos do sistema.           | Requisitos Não Funcionais (RNF)  |
| **React** | Biblioteca/Framework utilizado para construir a interface de usuário (Front-end) responsiva.                                          | Requisitos Não Funcionais (RNF)  |
| **Simulado Cronometrado** | Prova simulada gerada a partir do banco de questões, contando com um controle de tempo regressivo (condições reais de prova).      | Documento de Visão               |
| **Sprint** | Ciclo de desenvolvimento ao fim do qual entregas são feitas e validadas no repositório do projeto.                                  | Lista de Stakeholders            |
| **Stakeholder** | Qualquer pessoa ou grupo que tem interesse ou é impactado pelo projeto (ex: Estudantes, Professores, Coordenação).                 | Lista de Stakeholders            |
| **Timeout (Exaustão de Tempo)** | Situação onde o tempo do simulado se esgota, forçando o congelamento da tela e a submissão automática das respostas atuais.           | Regras de Negócio (RN)           |
| **Uptime (Disponibilidade)** | Tempo em que o sistema está operacional e acessível pelos usuários (estipulado em 99.5% nos meses de preparação).                     | Requisitos Não Funcionais (RNF)  |