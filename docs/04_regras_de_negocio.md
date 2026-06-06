# Regras de Negócio (RN) - Sistema de Apoio ao ENADE

## Histórico de Versões

| Data       | Versão | Descrição                                  | Autor      |
| ---------- | ------- | -------------------------------------------- | ---------- |
| 16/05/2026 | 1.0     | Criação do documento e mapeamento das RNs. | Kayo Gomes |
| 19/05/2026 | 2.0     | Correções                                  | Kayo Gomes |
| 06/06/2026 | 2.1     | Esclarecimento da RN10 sobre visão nominal restrita ao professor vinculado à turma. | Karlos Eduardo     |

## 1. Introdução

Este documento apresenta o catálogo de **Regras de Negócio (RN)** para o Sistema de Apoio ao ENADE. As regras de negócio definem as diretrizes, políticas, restrições e premissas operacionais que o software deve obrigatoriamente seguir e aplicar. Elas são independentes de tecnologia e servem para garantir que as funcionalidades implementadas estejam perfeitamente alinhadas aos objetivos pedagógicos e institucionais da universidade.

---

## 2. Catálogo de Regras de Negócio

### 2.1. Autenticação e Acesso (Segurança)

#### RN01 - Restrição de Domínio Institucional

* **Descrição:** O acesso à plataforma por meio do componente Google OAuth é restrito exclusivamente a usuários que possuam e-mail com o domínio institucional da universidade (ex: `nome@unifor.edu.br` para alunos e docentes).
* **Severidade:** Crítica
* **Origem:** Coordenação do Curso / LGPD

#### RN02 - Vinculação de Escopo de Visão

* **Descrição:** Um usuário com perfil de "Professor" só poderá visualizar painéis analíticos e relatórios de desempenho de turmas com as quais possua vínculo direto de regência ativo no sistema acadêmico. Não é permitido o acesso a dados de turmas de outros docentes, exceto para o perfil de "Coordenação", que possui visão global do curso.
* **Severidade:** Alta
* **Origem:** Coordenação do Curso

---

### 2.2. Banco de Questões

#### RN03 - Imutabilidade das Questões Oficiais

* **Descrição:** Toda questão extraída ou carregada a partir da base histórica do INEP/ENADE é imutável. O enunciado, as alternativas e o gabarito oficial não podem sofrer edições ou exclusões por nenhum nível de usuário, garantindo a fidelidade ao exame real.
* **Severidade:** Crítica
* **Origem:** Base do INEP / Premissa de Projeto

#### RN04 - Associação de Elementos Pedagógicos

* **Descrição:** Cada questão do banco de dados deve estar obrigatoriamente categorizada em, no mínimo, uma Área de Conteúdo Curricular (ex: Engenharia de Software, Banco de Dados, Redes) e um Ano de Edição do ENADE correspondente.
* **Severidade:** Alta
* **Origem:** Equipe de TI / Professores de Apoio

---

### 2.3. Simulados e Cronometragem

#### RN05 - Tempo Padrão por Questão

* **Descrição:** Na geração de simulados cronometrados automáticos, o tempo limite total regressivo do cronômetro deve ser calculado com base na constante de **3 minutos por questão** incluída no simulado (ex: um simulado de 10 questões terá obrigatoriamente 30 minutos de duração máxima).
* **Severidade:** Média
* **Origem:** Prática de Condições Reais de Prova

#### RN06 - Encerramento por Exaustão de Tempo (Timeout)

* **Descrição:** Caso o cronômetro regressivo atinja o valor zero antes que o estudante finalize o simulado voluntariamente, o sistema deve congelar a tela, salvar imediatamente todas as respostas assinaladas até aquele momento e realizar a submissão automática do simulado para correção.
* **Severidade:** Alta
* **Origem:** Regra de Condição de Prova (INEP)

#### RN07 - Unicidade de Questões por Sessão

* **Descrição:** O algoritmo de sorteio e geração de simulados deve garantir que nenhuma questão seja repetida ou duplicada dentro da mesma sessão de simulado de um usuário.
* **Severidade:** Alta
* **Origem:** Qualidade de Software

---

### 2.4. Mapas Mentais e Aprendizado Colaborativo

#### RN08 - Unicidade do Gabarito Visual

* **Descrição:** Cada questão do banco possui apenas **um único mapa mental oficial** associado, o qual deve ser validado e aprovado pelo Product Owner (ou corpo docente autorizado) antes de ser disponibilizado para visualização dos estudantes.
* **Severidade:** Alta
* **Origem:** Professor Marcelo Bezerra (PO)

#### RN09 - Moderação de Conteúdo Colaborativo

* **Descrição:** O fórum de debate por questão é público para leitura de todos os alunos autenticado, mas as mensagens e comentários podem ser moderados (excluídos permanentemente) a qualquer momento por professores ou pela coordenação, caso infrinjam políticas éticas ou de conduta da instituição.
* **Severidade:** Média
* **Origem:** Coordenação do Curso

---

### 2.5. Painel Analítico e Métricas

#### RN10 - Anonimização Pedagógica no Dashboard

* **Descrição:** Para proteger a privacidade dos estudantes (em conformidade com a LGPD), os painéis de gerenciamento globais visíveis à Coordenação e em visualizações consolidadas exibirão métricas de desempenho apenas de forma **agregada e percentual** por turma (ex: "75% da turma acertou a questão X"). O desempenho nominal detalhado de alunos não será exposto de forma pública nos gráficos de desempenho geral. **No entanto, a visão nominal individual por aluno (tela de Turmas) é permitida única e exclusivamente para o professor vinculado àquela turma específica**, configurando-se como uma ferramenta estrita de acompanhamento pedagógico, e não como um painel público.
* **Severidade:** Alta
* **Origem:** LGPD / Comitê de Ética Institucional / Requisitos de Acompanhamento Docente

---

## 3. Matriz de Rastreabilidade

Esta matriz correlaciona as Regras de Negócio (RN) com as Funcionalidades (F) mapeadas no Documento de Visão para garantir a consistência do escopo.

| Regra de Negócio (RN)                  | Funcionalidade Relacionada (Documento de Visão)     | Objetivo Garantido                                  |
| :-------------------------------------- | :--------------------------------------------------- | :-------------------------------------------------- |
| **RN01** (Domínio Institucional) | Integração com Sistema Acadêmico (Autenticação) | Garantir segurança e conformidade de acesso.       |
| **RN02** (Escopo de Visão)       | F5.1 Painel de gerenciamento e análise              | Isolar dados confidenciais por docente.             |
| **RN03** (Imutabilidade INEP)     | F1.1 Banco de questões com busca avançada          | Preservar fidedignidade histórica do exame.        |
| **RN04** (Categorização)        | F1.1 Banco de questões com busca avançada          | Permitir filtros precisos por área de conteúdo.   |
| **RN05** (Tempo Padrão)          | F3.1 Simulados cronometrados                         | Treinar o gerenciamento de tempo do aluno.          |
| **RN06** (Submissão Automática) | F3.1 Simulados cronometrados                         | Simular fielmente o encerramento real da prova.     |
| **RN07** (Não Duplicação)      | F3.1 Simulados cronometrados                         | Garantir variedade de tópicos no treinamento.      |
| **RN08** (Mapa Mental Oficial)    | F2.1 Resoluções via mapas mentais                  | Assegurar a qualidade técnica do conteúdo visual. |
| **RN09** (Moderação Fórum)     | F4.1 Fórum de debate por questão                   | Manter o ambiente acadêmico saudável e focado.    |
| **RN10** (Anonimização)         | F5.1 Painel de gerenciamento e análise              | Estar em total conformidade com a LGPD.             |
