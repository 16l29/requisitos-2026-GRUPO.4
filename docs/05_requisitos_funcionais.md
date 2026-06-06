# Requisitos Funcionais (RF) - Sistema de Apoio ao ENADE

## Histórico de Versões

| Data       | Versão | Descrição                                                                                                    | Autor                           |
| ---------- | ------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| 16/05/2026 | 1.0     | Criação do documento e elicitação dos RFs.                                                                 | Kayo Gomes,<br />Karlos Eduardo |
| 06/06/2026 | 1.1     | Inclusão dos RFs de gestão de usuários, cursos, competências, cadastro de questões e dashboard de fórum. | Karlos Eduardo                  |

---

## 1. Introdução

Este documento lista os **Requisitos Funcionais (RF)** do Sistema de Apoio ao ENADE. Eles descrevem as ações específicas que o sistema deve ser capaz de executar, traduzindo as necessidades mapeadas no Documento de Visão em funcionalidades técnicas e interações sistêmicas que serão implementadas pela equipe de desenvolvimento.

---

## 2. Catálogo de Requisitos Funcionais

### 2.1. Módulo de Autenticação e Usuários

| ID             | Descrição                                                                                                                                                | Prioridade |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: |
| **RF01** | **Permitir** o login de estudantes e professores utilizando a integração com o Google OAuth.                                                       |    Alta    |
| **RF02** | **Validar** o domínio de e-mail institucional durante o primeiro acesso para autorizar a entrada no sistema.                                        |    Alta    |
| **RF03** | **Atribuir** automaticamente o nível de permissão ("Estudante", "Professor" ou "Coordenador") com base nos dados integrados do sistema acadêmico. |    Alta    |

### 2.2. Módulo de Banco de Questões e Mapas Mentais

| ID             | Descrição                                                                                                                                          | Prioridade |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: |
| **RF04** | **Permitir** ao usuário buscar questões do ENADE aplicando filtros simultâneos por: palavra-chave, ano de aplicação e área de conteúdo. |    Alta    |
| **RF05** | **Exibir** o enunciado completo, imagens de apoio (se houver) e as alternativas de cada questão recuperada do banco.                          |    Alta    |
| **RF06** | **Exibir** o mapa mental com a explicação estruturada da resposta correta após o aluno submeter a sua tentativa de resolução.             |    Alta    |
| **RF07** | **Registrar** a resposta assinalada pelo estudante no banco de dados para compor os cálculos estatísticos futuros.                           |    Alta    |

### 2.3. Módulo de Simulados Cronometrados

| ID             | Descrição                                                                                                                                                         | Prioridade |
| :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------: |
| **RF08** | **Gerar** um simulado dinâmico com base na seleção de áreas de conhecimento escolhidas pelo estudante.                                                    |    Alta    |
| **RF09** | **Calcular** e **exibir** um cronômetro regressivo na tela de prova, considerando 3 minutos por questão incluída no simulado.                        |   Média   |
| **RF10** | **Salvar** automaticamente em *background* a alternativa selecionada a cada avanço de questão, prevenindo perda de dados por fechamento acidental da aba. |    Alta    |
| **RF11** | **Submeter** o simulado automaticamente para correção quando o cronômetro regressivo atingir o valor zero.                                                 |    Alta    |
| **RF12** | **Exibir** a nota final do simulado (quantidade de acertos, erros e o tempo total gasto) imediatamente após a sua submissão.                                |    Alta    |

### 2.4. Módulo de Fórum de Debate

| ID             | Descrição                                                                                                                                         | Prioridade |
| :------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: |
| **RF13** | **Permitir** que os usuários autenticados publiquem comentários de texto em uma seção de fórum atrelada a cada questão do banco.        |   Média   |
| **RF14** | **Exibir** os comentários em ordem cronológica de envio, identificando o nome e a tag de perfil (Estudante/Professor) do autor da mensagem. |   Média   |
| **RF15** | **Permitir** que usuários com perfil de Professor ou Coordenador excluam comentários de qualquer usuário para fins de moderação.         |   Baixa   |

### 2.5. Módulo de Painel Gerencial (Dashboard)

| ID             | Descrição                                                                                                                                                | Prioridade |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: |
| **RF16** | **Gerar** gráficos visuais contendo as taxas percentuais de acertos e erros agregadas dos estudantes, segmentadas por eixo de conteúdo curricular. |    Alta    |
| **RF17** | **Permitir** que o professor filtre os dados exibidos no painel selecionando apenas as turmas com as quais possui vínculo ativo.                    |    Alta    |
| **RF18** | **Listar** um ranking automático das "Top 5 Questões com Maior Índice de Erros" da turma filtrada para direcionamento das aulas de revisão.      |   Média   |

### 2.6. Módulo de Gestão Administrativa

| ID             | Descrição                                                                                                                                                                        | Prioridade |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: |
| **RF19** | **Permitir** que usuários com perfil de Coordenação realizem o gerenciamento (cadastro, edição, ativação/desativação e exclusão) de usuários da plataforma.       |    Alta    |
| **RF20** | **Permitir** que usuários com perfil de Coordenação cadastrem e editem os cursos oferecidos, além de vincular usuários (professores/estudantes) aos respectivos cursos. |    Alta    |

### 2.7. Módulo de Gestão Pedagógica e Curadoria

| ID             | Descrição                                                                                                                                                            | Prioridade |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------: |
| **RF21** | **Permitir** que a Equipe de Professores crie, edite e exclua competências e habilidades de acordo com as diretrizes e matrizes do INEP.                        |   Média   |
| **RF22** | **Permitir** que a Equipe de Professores vincule e associe as competências cadastradas às questões do banco de dados.                                         |   Média   |
| **RF23** | **Permitir** que a Equipe de Professores cadastre manualmente questões originais (inéditas ou adaptadas), englobando enunciado, alternativas e gabarito.       |    Alta    |
| **RF24** | **Permitir** que a Equipe de Professores selecione e importe em lote questões diretamente do acervo oficial sincronizado do INEP para o banco ativo do sistema. |    Alta    |
