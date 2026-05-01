# Identificação de Stakeholders

## Histórico de Versões

| Data       | Versão | Descrição                                    | Autor                            |
| ---------- | ------- | ---------------------------------------------- | -------------------------------- |
| 01/05/2026 | 1.0     | Criação do documento e mapeamento de perfis. | Kayo Gomes,<br />Karlos Eduardo, |

---

## 1. Introdução

Este documento tem como objetivo identificar, classificar e descrever todas as partes interessadas (stakeholders) envolvidas no sistema de apoio ao ENADE. O mapeamento correto garante que os requisitos elicitados atendam às reais necessidades dos usuários finais e aos objetivos de negócio da instituição de ensino.

## 2. Matriz de Stakeholders

A tabela abaixo classifica os envolvidos de acordo com seu papel, nível de influência no projeto (poder de decisão) e nível de impacto (o quanto o sistema afeta sua rotina).

| Stakeholder / Nome                       | Papel                  | Interesses e Expectativas                                                                                                        | Influência | Impacto |
| :--------------------------------------- | :--------------------- | :------------------------------------------------------------------------------------------------------------------------------- | :---------: | :-----: |
| **PO** <br />Prof. Marcelo Bezerra | Validador / Orientador | Garantir a aplicação correta da engenharia de requisitos, validar entregas e garantir o valor acadêmico do projeto.           |    Alta    |  Alto  |
| **Coordenação do Curso**         | Cliente / Patrocinador | Deseja relatórios gerais de desempenho para avaliar a qualidade do ensino e melhorar as notas do curso no ENADE.                |    Alta    |  Alto  |
| **Professores do ENADE**           | Usuário Estratégico  | Precisam de painéis analíticos (dashboards) para identificar lacunas de aprendizado nas turmas e direcionar aulas de revisão. |   Média   |  Alto  |
| **Estudantes de Graduação**      | Usuário Final         | Buscam uma ferramenta intuitiva, rápida e focada, com simulados cronometrados e mapas mentais para otimizar o tempo de estudo.  |    Baixa    |  Alto  |
| **Equipe de TI**                   | Desenvolvedores        | Precisam de requisitos claros, bem definidos e regras de negócio documentadas para a modelagem do sistema.                      |    Alta    | Médio |

---

## 3. Descrição Detalhada dos Perfis (Personas)

Para guiar as decisões de interface e fluxos do sistema, foram elaboradas personas baseadas no público-alvo principal.

### 3.1. Persona 1: O Estudante Focado

* **Nome Fictício:** Lucas Mendes
* **Perfil:** Aluno do 8º semestre de Sistemas de Informação, estagia 6 horas por dia e tem pouco tempo livre para estudar para o ENADE.
* **Dores:** Sente-se perdido com o volume de conteúdo acumulado ao longo de 4 anos de curso. Tem preguiça de ler textos longos de gabaritos tradicionais.
* **Necessidades no Sistema:** * Quer resolver questões de provas anteriores pelo celular enquanto está no ônibus.
  * Precisa ver a explicação da resposta rapidamente através de recursos visuais (mapas mentais).
  * Deseja testar seu tempo de resolução com simulados cronometrados.

### 3.2. Persona 2: A Professora Mentora

* **Nome Fictício:** Profa. Helena Silva
* **Perfil:** Coordenadora de TCC e professora da disciplina de revisão para o ENADE. Leciona para 3 turmas simultâneas.
* **Dores:** Atualmente, ela faz um "voo cego". Passa listas de exercícios em PDF, mas não sabe quais questões os alunos mais erram até o dia da prova presencial.
* **Necessidades no Sistema:**
  * Precisa de um *Dashboard* que mostre estatísticas em tempo real (ex: "70% da Turma A errou a questão sobre Banco de Dados").
  * Quer poder interagir com os alunos no fórum de discussão de questões específicas para tirar dúvidas pontuais.

---

## 4. Estratégia de Engajamento

Para garantir o sucesso da elicitação de requisitos, a interação com esses stakeholders ocorrerá da seguinte forma:

* **Estudantes:** Serão engajados através de questionários online e entrevistas curtas para validar o modelo de mapas mentais e simulados.
* **Professores/Coordenação:** Serão entrevistados para definir quais métricas são essenciais no Dashboard analítico.
* **Product Owner:** Validação contínua através das entregas das *Sprints* no repositório do GitHub.
