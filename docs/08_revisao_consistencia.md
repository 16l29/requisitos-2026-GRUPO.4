# Revisão de Consistência — Sistema ENADE
## Alinhamento entre Diagramas UML e Artefatos de Requisitos
---

## Histórico de Versões

| Data | Versão | Descrição | Autor |
|------|--------|-----------|-------|
| 06/06/2026 | 1.0 | Criação do documento de revisão de consistência | Karlos Eduardo |

---

## 1. Objetivo

Este documento tem como finalidade verificar o alinhamento e a rastreabilidade entre os diagramas UML produzidos (Diagrama de Casos de Uso, Diagrama de Componentes, Diagrama de Implantação e Mapa de Stakeholders) e os artefatos de requisitos do projeto (Documento de Visão, Regras de Negócio, Requisitos Funcionais, Requisitos Não Funcionais, CDUs e Protótipos de Interface). Eventuais inconsistências, lacunas ou pontos de atenção são registrados com recomendações de correção.

---

## 2. Escopo da Revisão

Os artefatos analisados e atualizados nesta revisão foram:

**Diagramas UML:**
- Diagrama de Casos de Uso (CDU) — Sistema ENADE
- Diagrama de Componentes (UML)
- Diagrama de Implantação (Deployment)
- Diagrama de Mapeamento de Stakeholders

**Documentos de Requisitos (Atualizados):**
- Documento de Visão da Demanda (VD) — v4.0
- Lista de Stakeholders — v1.1
- Glossário — v1.1
- Regras de Negócio (RN) — v2.1
- Requisitos Funcionais (RF) — v1.1
- Requisitos Não Funcionais (RNF) — v1.0
- CDU-01 a CDU-11 (especificações de casos de uso atualizadas)

**Protótipos de Interface (telas):**
- 01 a 15 (abrangendo perfis Estudante, Professor e fluxos completos)

---

## 3. Metodologia

A revisão foi conduzida por três eixos de verificação:

1. **Atores × CDUs × RFs:** Verificação se cada ator do Diagrama de Casos de Uso possui CDU correspondente e se os RFs cobrem as ações descritas.
2. **Regras de Negócio × CDUs × Protótipos:** Verificação se as RNs aparecem refletidas nos fluxos dos CDUs e nas interfaces prototipadas.
3. **Diagramas Arquiteturais × RNFs:** Verificação se os componentes e nós descritos nos diagramas de Componentes e Implantação estão cobertos pelos Requisitos Não Funcionais.

---

## 4. Matriz de Rastreabilidade: Atores × CDUs × Requisitos Funcionais

A tabela abaixo cruza cada caso de uso do Diagrama UML com o CDU especificado e os RFs correspondentes.

| Caso de Uso (Diagrama UML) | CDU | Ator(es) | RFs Relacionados | Status |
|---|---|---|---|---|
| Efetuar Cadastro e Login | CDU-01 | Estudante, Sist. Acadêmico | RF01, RF02, RF03 | ✅ Consistente |
| Filtrar Banco de Dados | CDU-02 | Estudante | RF04, RF05 | ✅ Consistente |
| Visualizar Resolução via Mapa Mental | CDU-03 | Estudante | RF06 | ✅ Consistente |
| Realizar Simulado Cronometrado | CDU-04 | Estudante | RF08, RF09, RF10, RF11, RF12 | ✅ Consistente |
| Participar de Fórum de Debate | CDU-05 | Estudante, Professor | RF13, RF14, RF15 | ✅ Consistente |
| Visualizar Dashboard de Desempenho | CDU-06 | Estudante, Professor | RF25, RF26, RF27 | ✅ Consistente |
| Sincronizar Questões do INEP | CDU-07 | Sistema INEP | — (automação) | ✅ Consistente |
| Gerenciar Usuários | CDU-08 | Coordenação | RF19 | ✅ Consistente |
| Gerenciar Cursos | CDU-09 | Coordenação | RF20 | ✅ Consistente |
| Gerenciar Competências das Questões | CDU-10 | Equipe de Professores | RF21, RF22 | ✅ Consistente |
| Cadastrar Questões | CDU-11 | Equipe de Professores | RF23, RF24 | ✅ Consistente |

*Nota sobre a resolução: Os RFs complementares (RF19 a RF27) foram criados no documento de Requisitos Funcionais (v1.1) cobrindo todos os módulos de gestão e separando o dashboard de engajamento do fórum.*

---

## 5. Análise por CDU — Consistência com Diagrama UML e Protótipos

### 5.1. CDU-01 — Efetuar Cadastro e Login

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ O ator Estudante está corretamente representado. O Sistema Acadêmico como ator secundário (`<<include>>`) está coerente com o diagrama. |
| Alinhamento com RF | ✅ RF01 (Google OAuth), RF02 (validação de domínio) e RF03 (atribuição de perfil) cobrem os fluxos principais e alternativos do CDU. |
| Alinhamento com RN | ✅ RN01 (Restrição de Domínio Institucional) e RNF05 referenciadas explicitamente na seção 15 do CDU-01 (Corrigido). |
| Alinhamento com Protótipo (tela 03) | ✅ Fluxo principal do CDU atualizado para Google OAuth (P1–P7), com e-mail/senha reposicionado como fluxo alternativo A2, refletindo fielmente a interface prototipada. |

### 5.2. CDU-02 — Filtrar Banco de Dados

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ Ator Estudante corretamente representado. A dependência com o CDU-07 documentada. |
| Alinhamento com RF | ✅ RF04 e RF05 cobrem o fluxo. |
| Alinhamento com Protótipo (tela 05) | ✅ A tela exibe filtros por área, ano, conteúdo e engenharia, além de busca textual e "Limpar filtros", todos previstos no CDU e RFs. |
| Alinhamento com RN | ✅ A RN04 (categorização por área e ano) sustenta os filtros descritos. |
| Referência interna no CDU | ✅ Referência na seção 15 corrigida para "CDU-07". |

### 5.3. CDU-03 — Visualizar Resolução via Mapa Mental

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ Ator Estudante correto. |
| Alinhamento com RF | ✅ RF06 (exibir mapa mental após submissão) cobre o fluxo. |
| Alinhamento com RN | ✅ RN08 (unicidade do mapa mental oficial) referenciada no CDU-03 (Corrigido). |
| Alinhamento com Protótipo (tela 08) | ✅ A seção 14 do CDU documentou explicitamente que o formato visual seguirá estrutura de tópicos colapsáveis (conforme protótipo), eliminando a ambiguidade com grafos interativos. |

### 5.4. CDU-04 — Realizar Simulado Cronometrado

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ Ator Estudante correto. |
| Alinhamento com RF | ✅ RF08 a RF12 cobrem todos os passos do fluxo principal e os fluxos de exceção. |
| Alinhamento com RN | ✅ RN05 (3 min/questão), RN06 (timeout com submissão automática) e RN07 (unicidade de questões) estão alinhados. |
| Alinhamento com Protótipo (telas 06 e 07) | ✅ Fluxo principal ampliado no CDU-04 para cobrir as 5 modalidades exibidas no protótipo (Completo, Por Área, Refazer Último, Fortificar Pontos Fortes e Relembrar Conteúdos Antigos). |
| Cálculo do cronômetro | ✅ Cálculo do cronômetro convergente: 3 min/questão. |

### 5.5. CDU-05 — Participar de Fórum de Debate

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ Atores Estudante e Professor corretamente representados. |
| Alinhamento com RF | ✅ RF13, RF14 e RF15 estão alinhados. |
| Alinhamento com RN | ✅ RN09 (moderação de conteúdo colaborativo) está alinhada. |
| Alinhamento com Protótipo (telas 09, 10, 14) | ✅ Fluxo A4 incluído no CDU-05 para cobrir a marcação de status do tópico (Pendente / Respondido), presente no protótipo da visão do professor (Corrigido). |

### 5.6. CDU-06 — Visualizar Dashboard de Desempenho de Fórum

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ Atores Estudante e Professor corretos. |
| Alinhamento com RF | ✅ Escopo clarificado. O CDU-06 agora trata exclusivamente do engajamento do fórum (RF25-27), enquanto os simulados são cobertos pelos RF16-18 (Corrigido). |
| Alinhamento com RN | ✅ RN10 refinada na v2.1 para permitir explicitamente a visão nominal individual ao professor vinculado à turma, extinguindo o falso conflito com a tela 15. |

### 5.7. CDU-07 — Sincronizar Questões do INEP

| Dimensão | Situação |
|---|---|
| Alinhamento com Diagrama de CDU | ✅ O ator "Sistema INEP" com relação `<<include>>` está corretamente representado. |
| Alinhamento com RN | ✅ RN03 (imutabilidade das questões oficiais) incluída nas referências da seção 15 do CDU-07 (Corrigido). |

### 5.8 a 5.11. Gestão (CDU-08, 09, 10 e 11)

| Dimensão | Situação |
|---|---|
| Alinhamento Geral e RFs | ✅ Funcionalidades documentadas com RFs formais (RF19 a RF24) no documento `05_requisitos_funcionais_2.md`. |
| Alinhamento RNs (CDU-11) | ✅ RN03 e RN04 referenciadas na seção 15 do CDU-11 (Corrigido). |

---

## 6. Análise dos Diagramas Arquiteturais × Requisitos Não Funcionais

| Componente/Nó | Ajuste Identificado | Status |
|---|---|---|
| Módulos de Integração | Os módulos INEP Link e Acadêmico Gateway foram formalmente absorvidos na arquitetura documentada para suprir a representação do Diagrama de Componentes. | ✅ Resolvido |
| Conexões Seguras (TLS) | Comunicação BD via TLS e suporte horizontal validados nos requisitos para cobrir RNF02 e RNF04. | ✅ Resolvido |

---

## 7. Análise das Regras de Negócio × CDUs × Protótipos

| Regra de Negócio | Reflexo Ajustado | Status |
|---|---|---|
| **RN01** — Domínio Institucional | Adicionada como referência no CDU-01. | ✅ Corrigido |
| **RN03** — Imutabilidade INEP | Adicionada como referência nos CDUs 07 e 11. Restrição de UI mapeada para desabilitar exclusão de questões do INEP. | ✅ Corrigido |
| **RN08** — Mapa Mental Oficial | Adicionada como referência no CDU-03. | ✅ Corrigido |
| **RN10** — Anonimização | Redação ajustada (v2.1) esclarecendo que a visão nominal individual é privativa do professor da turma. | ✅ Corrigido |

---

## 8. Consistência entre Atores UML e Stakeholders

| Ator (Diagrama UML) | Stakeholder (Documento de Stakeholders) | Persona Documentada | Status |
|---|---|---|---|
| Estudante | Estudantes de Graduação | Persona 1 — João | ✅ Consistente |
| Professor | Professores do ENADE | Persona 2 — Profa. Maria | ✅ Consistente |
| Coordenação | Coordenação do Curso | Persona 3 — Prof. Roberto | ✅ Persona Incluída |
| Equipe de Professores | Membros NDE | Persona 4 — Prof. Carlos | ✅ Persona Incluída |

---

## 9. Inconsistências Identificadas — Resumo de Resolução

A tabela abaixo rastreia a correção dos 16 itens apontados na primeira versão desta revisão:

| ID | Descrição da Inconsistência Original | Status |
|---|---|---|
| INC-01 | CDU-01 com e-mail/senha como fluxo principal | ✅ Corrigido (Google OAuth promovido a P1-P7) |
| INC-02 | Referência incorreta a CDU-09 no CDU-02 | ✅ Corrigido |
| INC-03 | RN01 (domínio) sem referência no CDU-01 | ✅ Corrigido |
| INC-04 | RN08 (mapa mental) sem referência no CDU-03 | ✅ Corrigido |
| INC-05 | RN03 (imutabilidade) sem referência no CDU-07 | ✅ Corrigido |
| INC-06 | RN03 e RN04 sem referências no CDU-11 | ✅ Corrigido |
| INC-07 | CDUs de gestão sem RFs correspondentes | ✅ Corrigido (Criados RF19 a RF24) |
| INC-08 | Dashboard de fórum confundido com simulados | ✅ Corrigido (Escopo dividido e clarificado) |
| INC-09 | Modalidades de simulado no protótipo não previstas | ✅ Corrigido (Adicionadas ao CDU-04) |
| INC-10 | Botões editar/excluir em possíveis questões INEP | ✅ Ajustado (Documentado bloqueio via RN03) |
| INC-11 | Exibição nominal na Tela 15 conflitando com RN10 | ✅ Corrigido (Redação da RN10 alterada) |
| INC-12 | Módulos de integração omitidos no diag. componentes | ✅ Mitigado e documentado |
| INC-13 | Conexão BD via TCP/IP sem TLS | ✅ Ajustado via RNFs |
| INC-14 | Sem representação de escalabilidade horizontal | ✅ Ajustado via RNFs |
| INC-15 | Coordenação e Eq. Professores sem personas | ✅ Corrigido (Adicionadas Personas 3 e 4) |
| INC-16 | Status "Pendente/Respondido" ausente no CDU-05 | ✅ Corrigido (Incluído fluxo A4) |

---

## 11. Checklist de Consistência Geral

| Critério | Status Atualizado |
|---|---|
| Todos os casos de uso do Diagrama UML possuem CDU especificado? | ✅ Sim |
| Todos os atores humanos do Diagrama UML possuem persona documentada? | ✅ Sim (Lista de Stakeholders v1.1) |
| Todos os CDUs possuem RF correspondente? | ✅ Sim (Requisitos Funcionais v1.1) |
| Todos os RFs possuem CDU correspondente? | ✅ Sim |
| As Regras de Negócio estão referenciadas nos CDUs relevantes? | ✅ Sim |
| Os diagramas arquiteturais cobrem os RNFs definidos? | ✅ Sim |
| Os protótipos são consistentes com os CDUs? | ✅ Sim |
| A nomenclatura é consistente entre todos os artefatos? | ✅ Sim |
| A RN10 (LGPD) é respeitada nos protótipos? | ✅ Sim (exceção nominal justificada) |

---

## 12. Conclusão

Após a aplicação das correções recomendadas na versão 1.0, o conjunto de artefatos do **Sistema ENADE** atingiu rastreabilidade **completa e total alinhamento**. 

As lacunas funcionais foram sanadas com a criação de novos RFs administrativos, as incoerências de interface foram eliminadas por atualizações diretas nos fluxos dos Casos de Uso (como a promoção do OAuth e as 5 modalidades de simulado), e os conflitos com a Lei Geral de Proteção de Dados (LGPD) foram diplomaticamente resolvidos ao refinar as diretrizes das Regras de Negócio, salvaguardando a eficácia do trabalho do professor.

O projeto demonstra base documental robusta, isenta de pontas soltas ou contradições, e está totalmente qualificado para avançar de forma segura às etapas de desenvolvimento e testes.