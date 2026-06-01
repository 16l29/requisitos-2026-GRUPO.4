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
| 01/06/2026 | 4.0 | Atualização completa com base no Diagrama de Casos de Uso (Atores e Fluxos). | Karlos Eduardo | 

## 1. Objetivo

Este documento visa definir a proposta de valor na idealização, construção e gerenciamento de uma solução de software (aplicativo web/mobile) auxiliar para o processo de preparação e realização do Exame Nacional de Desempenho de Estudantes (ENADE).

## 2. Proposta de Valor

A solução centralizará a preparação para o ENADE de forma dinâmica, colaborativa e direcionada por dados:
* **Para os Estudantes:** Reduz o tempo de estudo improdutivo ao oferecer resoluções visuais por mapas mentais, filtragem inteligente de conteúdo, simulados cronometrados em condições reais de prova e um espaço de debate enriquecedor.
* **Para o Corpo Docente e Coordenação:** Elimina o "voo cego" no acompanhamento das turmas concluintes. Fornece dados analíticos em tempo real (através de dashboards de desempenho dos fóruns) sobre as reais deficiências de aprendizado, permitindo intervenções pedagógicas e revisões curriculares precisas.

## 3. Descrição da Demanda

Atualmente, as instituições de ensino e os estudantes enfrentam severas dificuldades na preparação para o ENADE devido à descentralização de materiais e à escassez de indicadores de desempenho em tempo real. 

Para mitigar este problema, o **Sistema ENADE** funcionará como uma plataforma unificada que provê recursos de estudo individualizado (simulados, filtros de questões, mapas mentais), aprendizado social (fóruns de debate com dashboards analíticos de engajamento) e ferramentas de gestão institucional (cadastro de questões, controle de competências, gerenciamento de usuários e cursos), com integrações automatizadas a sistemas parceiros e governamentais.

## 4. Partes Interessadas (Stakeholders)

| Nome | Papel | Responsabilidades | Representante |
| :--- | :--- | :--- | :--- |
| **Coordenação** | Cliente / Gestor | Gerenciar usuários e cursos na plataforma; avaliar métricas consolidadas de adesão e qualidade. | Coordenador do Curso |
| **Estudante** | Usuário Final | Realizar simulados, praticar com questões filtradas, consultar mapas mentais e debater nos fóruns. | Alunos concluintes |
| **Professor** | Stakeholder / Mediador | Monitorar discussões nos fóruns de debate e analisar os dashboards de desempenho das turmas. | Corpo Docente |
| **Equipe de Professores** | Especialistas de Conteúdo | Realizar a curadoria pedagógica, cadastrar novas questões e gerenciar as matrizes de competências. | Comitê Estruturante (NDE) |
| **Professor Marcelo Bezerra** | Product Owner (PO) | Definir e defender a visão do produto, priorizar o backlog de desenvolvimento e validar as entregas. | Professor Marcelo Bezerra |
| **Equipe de TI** | Time de Desenvolvimento | Implementar as interfaces, manter a API estável e garantir as integrações com sistemas externos. | Kayo Gomes, Karlos Eduardo, Gustavo Lima |

## 5. Personas e Sistemas Atores (Mapeamento do Diagrama)

### 5.1. Estudante
* **Descrição:** Aluno matriculado em um curso superior na fase de conclusão de curso, elegível ou selecionado para realizar o exame do ENADE.
* **Objetivos no Sistema:** Autenticar-se de forma segura, filtrar e resolver questões de provas anteriores, acelerar sua compreensão por meio de mapas mentais estruturados, treinar gestão de tempo em simulados e sanar dúvidas de forma colaborativa nos fóruns.

### 5.2. Professor
* **Descrição:** Docente designado para acompanhar, orientar e revisar os conteúdos curriculares específicos com as turmas concluintes.
* **Objetivos no Sistema:** Atuar ativamente como mediador nos fóruns de debate de cada questão e extrair insights valiosos por meio dos dashboards de desempenho gerados a partir destas interações.

### 5.3. Coordenação
* **Descrição:** Responsável direto pela gestão pedagógica, administrativa e estratégica do curso de graduação.
* **Objetivos no Sistema:** Controlar o acesso à ferramenta por meio da gestão de usuários (estudantes/professores) e cadastrar/vincular as matrizes dos cursos avaliados.

### 5.4. Equipe de Professores
* **Descrição:** Colegiado ou comitê de docentes focado na qualidade do banco de itens de teste e alinhamento com as diretrizes do Ministério da Educação (MEC).
* **Objetivos no Sistema:** Expandir o banco de dados por meio do cadastro manual de novas questões inéditas ou adaptadas e gerenciar minuciosamente as competências associadas a cada questão.

### 5.5. Sistemas Externos Integrados
* **Sistema INEP (MEC):** Sistema governamental externo consumido pela plataforma para sincronizar e importar as questões oficiais, gabaritos e padrões de resposta de edições anteriores do ENADE.
* **Sistema Acadêmico da Instituição:** Infraestrutura interna da universidade responsável por fornecer suporte básico de dados para o ciclo de vida do Sistema ENADE, atuando diretamente como dependência (`<<include>>`) para processos de autenticação, validação de matrículas e consistência de turmas.

## 6. Necessidades e Funcionalidades

### Necessidade 1: Autenticação e Acesso Unificado
#### F1.1 Efetuar cadastro e login
* **Descrição:** Permitir que os estudantes se cadastrem e acessem a plataforma utilizando credenciais seguras. Esta funcionalidade possui interdependência com o barramento do Sistema Acadêmico da universidade.
* **Atores:** Estudante
* **Frequência:** Alta | **Valor:** Alto

### Necessidade 2: Prática Baseada em Evidências e Estudo Direcionado
#### F2.1 Filtrar banco de dados
* **Descrição:** Disponibilizar uma busca avançada que permita ao estudante selecionar questões específicas filtrando por termos, áreas de conhecimento, ano ou tipo de questão (discursiva/objetiva).
* **Atores:** Estudante
* **Frequência:** Alta | **Valor:** Alto

#### F2.2 Visualizar resolução via mapa mental
* **Descrição:** Apresentar a resolução comentada de cada questão estruturada visualmente em formato de mapa mental, facilitando a memorização e correlação de conceitos complexos.
* **Atores:** Estudante
* **Frequência:** Alta | **Valor:** Alto

#### F2.3 Realizar simulado cronometrado
* **Descrição:** Permitir a geração e execução de blocos de questões que emulam o cenário real da prova do ENADE, contendo um cronômetro regressivo para o monitoramento do tempo.
* **Atores:** Estudante
* **Frequência:** Média | **Valor:** Alto

### Necessidade 3: Aprendizado Social e Monitoramento Analítico
#### F3.1 Participar de fórum de debate
* **Descrição:** Ambiente integrado a cada questão onde os usuários podem inserir comentários, compartilhar resoluções alternativas, tirar dúvidas e interagir de forma síncrona/assíncrona.
* **Atores:** Estudante, Professor
* **Frequência:** Média | **Valor:** Médio

#### F3.2 Visualizar dashboard de desempenho de fórum de debate
* **Descrição:** Exibir relatórios gráficos contendo dados consolidados sobre as taxas de acerto, erro, nível de engajamento e as dúvidas mais recorrentes manifestadas nas discussões.
* **Atores:** Estudante, Professor
* **Frequência:** Média | **Valor:** Alto

### Necessidade 4: Governança e Administração da Plataforma
#### F4.1 Gerenciar usuários
* **Descrição:** Permitir o cadastro, edição, suspensão e exclusão de contas de usuários (alunos e professores) e controle de permissões.
* **Atores:** Coordenação
* **Frequência:** Baixa | **Valor:** Alto

#### F4.2 Gerenciar Cursos
* **Descrição:** Mapear e estruturar os cursos da instituição que passarão pela avaliação do ENADE, vinculando-os às suas respectivas grades ou turmas.
* **Atores:** Coordenação
* **Frequência:** Baixa | **Valor:** Alto

### Necessidade 5: Engenharia e Qualificação Pedagógica de Conteúdo
#### F5.1 Cadastrar questões
* **Descrição:** Funcionalidade interna para inclusão de novas questões, alternativas, enunciados e gabaritos oficiais de forma manual ou em lote.
* **Atores:** Equipe de Professores
* **Frequência:** Média | **Valor:** Alto

#### F5.2 Gerenciar competências das questões
* **Descrição:** Permitir a indexação de cada item de teste de acordo com a Matriz de Competências e Habilidades exigidas pelas portarias regulamentares do ENADE para cada área profissional.
* **Atores:** Equipe de Professores
* **Frequência:** Média | **Valor:** Alto

### Necessidade 6: Automatização de Carga Oficial Externalizada
#### F6.1 Sincronizar Questões do INEP
* **Descrição:** Rotina automatizada que conecta o ecossistema local ao *Sistema INEP* (`<<include>>`) para extrair e catalogar o histórico público das provas oficiais.
* **Atores:** Sistema (Automação de Background com o Sistema INEP)
* **Frequência:** Baixa | **Valor:** Alto

---

## 7. Arquitetura da Demanda

A arquitetura de software proposta é estruturada sob o modelo cliente-servidor por meio de uma API RESTful centralizada, projetada para atender aos fluxos expressos no Diagrama de Casos de Uso:

1. **Camada de Apresentação (Clientes):**
   * **Interface Mobile Responsiva / PWA:** Voltada essencialmente ao uso fluido do *Estudante* (cadastro, filtros, mapas mentais, simulados e fórum).
   * **Portal Web Administrativo:** Desenvolvido especificamente para atender as demandas analíticas e operacionais do *Professor* (dashboards), da *Coordenação* (gestão de cursos e usuários) e da *Equipe de Professores* (cadastro e gerenciamento de competências).
2. **Camada de Integração de Sistemas Externa:**
   * **Módulo INEP Link:** Conector assíncrono responsável pelo use case `Sincronizar Questões do INEP`.
   * **Módulo Acadêmico Gateway:** Barramento que unifica e valida a segurança global do sistema baseando-se nas regras do `Sistema Acadêmico` corporativo da universidade.

## 8. Premissas

### 8.1. Premissas de Negócio e Dados
* **Garantia de Acesso aos Dados do INEP:** Presume-se a manutenção da política de dados abertos e a estabilidade das fontes oficiais de dados do INEP, assegurando que o sistema possa realizar o processo de extração e transformação (ETL) sem impedimentos legais ou técnicos de segurança.

### 8.2. Premissas Técnicas e de Infraestrutura
* **Hospedagem Baseada em Nuvem:** Todo o ecossistema será implantado em um provedor de nuvem (Cloud Computing) de grande porte (ex: AWS, Azure ou GCP), operando com escalabilidade horizontal automatizada.
* **Isolamento de Persistência (SGBD):** Utilização de um Sistema Gerenciador de Banco de Dados Relacional robusto (ex: PostgreSQL) rodando em uma sub-rede isolada e protegida de acessos externos diretos.
* **Segurança na Comunicação Extensiva:** Todas as trocas de informações e comunicações de borda, incluindo as chamadas para os nós do *Sistema INEP* e do *Sistema Acadêmico*, ocorrerão estritamente sob canais criptografados via protocolo HTTPS (TLS 1.3).
* **Compatibilidade Omnichannel de Clientes:** As interfaces com o usuário final devem apresentar compatibilidade estrita com navegadores web modernos (Chrome, Firefox, Safari, Edge) e sistemas operacionais móveis vigentes (Android e iOS).

---

## Checklist de Validação do Documento de Visão

- [X] O objetivo está claro e alinhado ao problema/necessidade?
- [X] A proposta de valor é mensurável e relevante para todos os públicos?
- [X] Todas as partes interessadas estão listadas com papéis e responsabilidades detalhados?
- [X] Existem as personas descritas espelhando todos os atores humanos do diagrama UML?
- [X] Todas as necessidades e funcionalidades estão rigorosamente atreladas aos atores do diagrama?
- [X] Há indicação clara de valor e frequência para cada funcionalidade descrita?
- [X] A arquitetura ilustra e justifica a presença dos sistemas legados externos (`Sistema INEP` e `Sistema Acadêmico`)?
- [X] O documento está escrito em linguagem técnica, clara e objetiva?