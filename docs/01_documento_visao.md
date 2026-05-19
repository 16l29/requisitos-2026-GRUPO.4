# Visão da Demanda (VD)

## Histórico de Versões

| Data       | Versão | Descrição                                                                     | Autor                            |
| ---------- | ------- | ------------------------------------------------------------------------------- | -------------------------------- |
| 21/04/2026 | 1.0     | Identificar requisitos, stakeholders, personas e elaborar documento de visão.  | Kayo Gomes,<br />Karlos Eduardo, |
| 23/04/2026 | 1.1     | Refinamentos.                                                                   | Gustavo Lima                     |
| 01/05/2026 | 1.2     | Inclusão do Product Owner nas Partes Interessadas.                             | Kayo Gomes                       |
| 11/05/2026 | 1.3     | Revisão das personas e atualização da arquitetura de demanda do sistema.     | Karlos Eduardo                   |
| 16/05/2026 | 1.4     | Inclusão da seção de Premissas (integração com a base do ENADE)            | Karlos Eduardo                   |
| 19/05/2026 | 2.0     | Adição da persona "Coordenação" e conjugação infinitiva das necessidades. | Kayo Gomes                       |

## 1. Objetivo

&emsp;&emsp;Este documento visa definir a proposta de valor na idealização, construção e gerenciamento de um aplicativo web/mobile auxiliar para o processo de preparação e realização do Exame Nacional de Desempenho de Estudantes (ENADE).

## 2. Proposta de Valor

&emsp;&emsp;A solução centralizará a preparação para o ENADE de forma dinâmica e direcionada. Para os estudantes, reduzirá o tempo de estudo improdutivo ao oferecer resoluções visuais e práticas em condições reais de prova. Para o corpo docente, eliminará o "voo cego" no acompanhamento das turmas, fornecendo dados em tempo real sobre as deficiências de aprendizado para intervenções pedagógicas mais precisas.

## 3. Descrição da Demanda

&emsp;&emsp;Atualmente, estudantes enfrentam dificuldades na preparação para o ENADE devido à escassez de materiais organizados e feedback de desempenho. Para resolver isso, o sistema fornecerá uma API web/mobile composta por um banco de questões filtrável (por palavras-chave, tipo e conteúdo), resoluções em formato de mapas mentais, fóruns de debate para cada questão, geração de simulados cronometrados e um painel analítico para acompanhamento docente.

## 4. Partes Interessadas

Estudantes de graduação, Universidade de ensino (coordenação de cursos), professores que acompanham o processo do exame e a gestão do produto.

| Nome                      | Papel              | Responsabilidades                                                                                                      | Representante                                    |
| ------------------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Coordenação do Curso    | Cliente            | Avaliar métricas gerais de uso e qualidade.                                                                           | Coordenador                                      |
| Estudante                 | Usuário final     | Resolver questões, acessar mapas e fazer simulados.                                                                   | -                                                |
| Professor do Enade        | Stakeholder        | Analisar o desempenho da turma e apoiar no fórum.                                                                     | Corpo Docente                                    |
| Professor Marcelo Bezerra | Product Owner (PO) | Definir a visão do produto, priorizar o backlog, validar entregas e garantir que a solução atenda às necessidades. | Professor Marcelo Bezerra                        |
| Equipe de TI              | Desenvolvimento    | Implementar e manter a API web/mobile.                                                                                 | Kayo Gomes<br />Karlos Eduardo<br />Gustavo Lima |

## 5. Personas

### 5.1. Estudante

- **Descrição:** Aluno em fase de conclusão de curso que precisa realizar a prova do ENADE.
- **Objetivo:** Praticar com questões reais, entender rapidamente os conceitos através de resumos visuais (mapas mentais) e testar seu tempo de resolução.

### 5.2. Professor de Apoio

- **Descrição:** Docente responsável por preparar e revisar os conteúdos do ENADE com as turmas concluintes.
- **Objetivo:** Identificar rapidamente quais tópicos a turma tem mais dificuldade para focar suas aulas de revisão.

### 5.3. Coordenador de Curso

- **Descrição:** Responsável pela gestão pedagógica, estrutural e administrativa do curso de graduação.
- **Objetivo:** Avaliar as métricas gerais de engajamento no aplicativo e analisar os relatórios e dashboards de desempenho consolidado das turmas para tomadas de decisão institucionais e melhorias contínuas no projeto pedagógico do curso.

## 6. Necessidades e Funcionalidades

### Necessidade 1: Praticar com questões direcionadas

#### F1.1 Banco de questões com busca avançada

- **Descrição:** Permitir ao aluno filtrar questões do ENADE por palavras-chave, tipo e área de conteúdo.
- **Incluída**
- **Atores:** Estudante
- **Frequência:** Alta
- **Valor:** Alto

### Necessidade 2: Compreender visualmente as respostas

#### F2.1 Resoluções via mapas mentais

- **Descrição:** Exibir a explicação estruturada da resposta correta em formato de mapa mental para fixação rápida.
- **Incluída**
- **Atores:** Estudante
- **Frequência:** Alta
- **Valor:** Alto

### Necessidade 3: Treinar em condições de prova

#### F3.1 Simulados cronometrados

- **Descrição:** Gerar provas simuladas a partir do banco de questões, com controle de tempo regressivo.
- **Incluída**
- **Atores:** Estudante
- **Frequência:** Média
- **Valor:** Alto

### Necessidade 4: Aprender de forma colaborativa

#### F4.1 Fórum de debate por questão

- **Descrição:** Disponibilizar um espaço de comentários atrelado a cada questão para que alunos e professores discutam a resolução de forma colaborativa.
- **Incluída**
- **Atores:** Estudante, Professor
- **Frequência:** Média
- **Valor:** Médio

### Necessidade 5: Acompanhar pedagogicamente o desempenho

#### F5.1 Painel de gerenciamento e análise

- **Descrição:** Disponibilizar um dashboard web com gráficos de taxa de acertos e erros dos alunos, segmentado por conteúdo curricular.
- **Incluída**
- **Atores:** Professor, Coordenação
- **Frequência:** Média
- **Valor:** Alto

## 7. Arquitetura da Demanda

A arquitetura será baseada em uma API RESTful central que servirá a dois clientes principais:

- **Interface Mobile (Responsiva):** Versão otimizada para dispositivos móveis, focada na experiência do estudante (acesso rápido a simulados, mapas mentais e fórum) via navegador ou atalho no celular.
- **Aplicação Web (Portal):** Focada no painel de gerenciamento para professores e administradores (visualização de relatórios e dashboards).
- **Integrações:** O sistema consumirá dados públicos do INEP para alimentar o banco de questões e fará integração com o sistema acadêmico da universidade para autenticação e vinculação de turmas.

## 8. Premissas

Para a viabilidade do desenvolvimento e correto funcionamento da solução, estabeleceu-se a seguinte premissa tecnológica e de negócio:

**8.1. Premissas de Negócio e de Dados:**

* **Disponibilidade e Acesso à Base Histórica do ENADE:** Assume-se como verdadeira a existência, estabilidade e livre acesso a um repositório ou base de dados estruturada contendo o histórico de questões de exames anteriores do ENADE (provenientes de dados públicos do INEP ou repositórios institucionais). Supõe-se que esses arquivos forneçam de forma clara os enunciados, as alternativas de resposta, os gabaritos oficiais e a classificação por competências/eixos temáticos, viabilizando o processo automatizado de extração, transformação e carga (ETL) para alimentar o banco de dados do sistema.

**8.2. Premissas Técnicas e de Infraestrutura (Suporte ao Diagrama de Implantação):**

As diretrizes abaixo atuam como premissas fundamentais para o mapeamento dos nós físicos e
componentes no Diagrama de Implantação UML:

* **Hospedagem em Provedor de Nuvem (Cloud Computing):** Assume-se que toda a infraestrutura de servidores será hospedada em ambiente de nuvem público (ex: AWS, GCP ou Azure), utilizando serviços gerenciados para garantir alta disponibilidade, elasticidade e segurança.
* **Topologia Desacoplada (Client-Server Architecture):** O ecossistema será dividido de forma estrita em nós independentes: os clientes front-end (Aplicação Web Portal e a Interface Mobile Responsiva) serão distribuídos via Redes de Entrega de Conteúdo (CDNs) ou servidores de arquivos estáticos, enquanto a lógica de negócio (API RESTful) rodará em um nó de aplicação dedicado.
* **Ambiente de Execução da API (Containerização):** A API RESTful central será encapsulada e executada em containers (ex: Docker), permitindo que seja implantada de forma padronizada em servidores virtuais ou serviços de orquestração (como instâncias gerenciadas ou Kubernetes).
* **Camada de Persistência Isolada (SGBD Relacional):** Presume-se o uso de um Sistema Gerenciador de Banco de Dados Relacional (como PostgreSQL ou MySQL). O banco de dados residirá em um nó
  próprio e isolado (servidor de banco de dados dedicado), comunicando-se unicamente com o nó da API RESTful através de conexões seguras internas.
* **Conectividade e Integrações Externas via HTTPS:** O nó do servidor de aplicação (API) possuirá conectividade de saída externa via protocolo HTTPS seguro para consumir os endpoints públicos do INEP e para se comunicar com o servidor/gateway de autenticação do Sistema Acadêmico da Universidade.
* **Dispositivos dos Usuários Finais (Target Nodes):** Os nós de destino do usuário final consistem em dispositivos desktop (computadores de professores e coordenadores rodando navegadores web modernos) e dispositivos móveis (smartphones de alunos operando a interface responsiva/PWA via browser).

---

## Checklist de Validação do Documento de Visão

- [X] O objetivo está claro e alinhado ao problema/necessidade?
- [X] A proposta de valor é mensurável e relevante?
- [X] Todas as partes interessadas estão listadas com papéis definidos?
- [X] Existem pelo menos duas personas descritas?
- [X] Todas as necessidades e funcionalidades estão relacionadas a atores?
- [X] Há indicação de valor e frequência para cada funcionalidade?
- [X] A arquitetura está ilustrada (mesmo que de forma simples)?
- [X] O documento está escrito em linguagem clara e objetiva?
