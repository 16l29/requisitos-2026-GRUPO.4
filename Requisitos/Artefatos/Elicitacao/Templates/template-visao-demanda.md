# Visão da Demanda (VD)

## Histórico de Versões

| Data       | Versão | Descrição                                                                    | Autor                     |
| ---------- | ------- | ------------------------------------------------------------------------------ | ------------------------- |
| 21/04/2026 | 1.0     | Identificar requisitos, stakeholders, personas e elaborar documento de visão. | Kayo Gomes & Karlos Pinto |

## 1. Objetivo

    Este documento visa definir a proposta de valor na idealização, construção e gerenciamento de um aplicativo web/mobile auxiliar para o processo de preparação e realização do Exame Nacional de Desempenho de Estudantes (ENADE).

## 2. Proposta de Valor

    [cite start]A solução centralizará a preparação para o ENADE de forma dinâmica e direcionada. Para os estudantes, reduzirá o tempo de estudo improdutivo ao oferecer resoluções visuais e práticas em condições reais de prova. Para o corpo docente, eliminará o "voo cego" no acompanhamento das turmas, fornecendo dados em tempo real sobre as deficiências de aprendizado para intervenções pedagógicas mais precisas.

## 3. Descrição da Demanda

    Atualmente, estudantes enfrentam dificuldades na preparação para o ENADE devido à escassez de materiais organizados e feedback de desempenho. Para resolver isso, o sistema fornecerá uma API web/mobile composta por um banco de questões filtrável (por palavras-chave, tipo e conteúdo), resoluções em formato de mapas mentais, fóruns de debate para cada questão, geração de simulados cronometrados e um painel analítico para acompanhamento docente.

## 4. Partes Interessadas

Estudantes de graduação, Universidade de ensino (coordenação de cursos) e professores que acompanham o processo do exame.

| Nome                   | Papel           | Responsabilidades                                    | Representante             |
| ---------------------- | --------------- | ---------------------------------------------------- | ------------------------- |
| Coordenação do Curso | Cliente         | Avaliar métricas gerais de uso e qualidade.         | Coordenador               |
| Estudante              | Usuário final  | Resolver questões, acessar mapas e fazer simulados. | -                         |
| Professor              | Stakeholder     | Analisar o desempenho da turma e apoiar no fórum.   | Corpo Docente             |
| Equipe de TI           | Desenvolvimento | Implementar e manter a API web/mobile.               | Kayo Gomes & Karlos Pinto |

## 5. Personas

### 5.1. Estudante de Graduação

- **Descrição:** Aluno em fase de conclusão de curso que precisa realizar a prova do ENADE.
- **Objetivo:** Praticar com questões reais, entender rapidamente os conceitos através de resumos visuais (mapas mentais) e testar seu tempo de resolução.

### 5.2. Professor de Apoio

- **Descrição:** Docente responsável por preparar e revisar os conteúdos do ENADE com as turmas concluintes.
- **Objetivo:** Identificar rapidamente quais tópicos a turma tem mais dificuldade para focar suas aulas de revisão.

## 6. Necessidades e Funcionalidades

### Necessidade 1: Prática com questões direcionadas

#### F1.1 Banco de questões com busca avançada

- **Descrição:** Permite ao aluno filtrar questões do ENADE por palavras-chave, tipo e área de conteúdo.
- **Incluída**
- **Atores:** Estudante
- **Frequência:** Alta
- **Valor:** Alto

### Necessidade 2: Compreensão visual das respostas

#### F2.1 Resoluções via mapas mentais

- **Descrição:** Exibe a explicação estruturada da resposta correta em formato de mapa mental para fixação rápida.
- **Incluída**
- **Atores:** Estudante
- **Frequência:** Alta
- **Valor:** Alto

### Necessidade 3: Treinamento em condições de prova

#### F3.1 Simulados cronometrados

- **Descrição:** Gera provas simuladas a partir do banco de questões, com controle de tempo regressivo.
- **Incluída**
- **Atores:** Estudante
- **Frequência:** Média
- **Valor:** Alto

### Necessidade 4: Aprendizado colaborativo

#### F4.1 Fórum de debate por questão

- **Descrição:** Espaço de comentários atrelado a cada questão para que alunos e professores discutam a resolução.
- **Incluída**
- **Atores:** Estudante, Professor
- **Frequência:** Média
- **Valor:** Médio

### Necessidade 5: Acompanhamento pedagógico

#### F5.1 Painel de gerenciamento e análise

- **Descrição:** Dashboard web com gráficos de taxa de acertos e erros dos alunos, segmentado por conteúdo.
- **Incluída**
- **Atores:** Professor, Coordenação
- **Frequência:** Média
- **Valor:** Alto

## 7. Arquitetura da Demanda

A arquitetura será baseada em uma API RESTful central que servirá a dois clientes principais:

- **Aplicativo Mobile:** Focado na experiência do estudante (acesso rápido a simulados, mapas mentais e fórum).
- **Aplicação Web (Portal):** Focada no painel de gerenciamento para professores e administradores (visualização de relatórios e dashboards).
- **Integrações:** O sistema consumirá dados públicos do INEP para alimentar o banco de questões e fará integração com o sistema acadêmico da universidade para autenticação e vinculação de turmas.

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
