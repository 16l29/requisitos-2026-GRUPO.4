# 🎓 Sistema ENADE

> Plataforma web/mobile de preparação para o **Exame Nacional de Desempenho dos Estudantes (ENADE)**, desenvolvida como projeto da disciplina de **Requisitos e Modelagem de Sistemas** — Universidade de Fortaleza (UNIFOR).

[![Status](https://img.shields.io/badge/status-concluído-brightgreen)](https://sistema-enade.lovable.app/)
[![Licença](https://img.shields.io/badge/licença-acadêmica-blue)](#)
[![UNIFOR](https://img.shields.io/badge/instituição-UNIFOR-green)](#)

---

## 📌 Visão Geral

O **Sistema ENADE** centraliza a preparação para o ENADE de forma **dinâmica, colaborativa e direcionada por dados**. A plataforma combina prática com questões oficiais, aprendizado visual por mapas mentais, simulados cronometrados e ferramentas analíticas para docentes e coordenação.

**Problema resolvido:** A descentralização de materiais de estudo e a escassez de indicadores de desempenho em tempo real nas instituições de ensino.

---

## 🚀 Demonstração

Acesse o protótipo funcional: **[sistema-enade.lovable.app](https://sistema-enade.lovable.app/)**

[![Página Inicial do Sistema ENADE](prototipos/01_home_page.png)](https://sistema-enade.lovable.app/)

---

## ✨ Funcionalidades Principais

| Funcionalidade                | Descrição                                                     | Ator                      |
| ----------------------------- | --------------------------------------------------------------- | ------------------------- |
| 🔐 Cadastro e Login           | Autenticação integrada ao Sistema Acadêmico da instituição | Estudante                 |
| 🔍 Filtrar Banco de Questões | Busca avançada por área, ano, tipo e competência             | Estudante                 |
| 🗺️ Mapa Mental              | Resolução comentada de questões em formato visual            | Estudante                 |
| ⏱️ Simulado Cronometrado    | Treino em condições reais de prova com gestão de tempo       | Estudante                 |
| 💬 Fórum de Debate           | Discussão colaborativa por questão                            | Estudante / Professor     |
| 📊 Dashboard do Fórum        | Métricas de engajamento e desempenho das turmas                | Professor / Coordenação |
| 🔄 Sincronização INEP       | Importação de questões e gabaritos oficiais                  | Sistema INEP              |
| 👥 Gerenciar Usuários        | Controle de acesso de estudantes e professores                  | Coordenação             |
| 📚 Gerenciar Cursos           | Cadastro e vinculação de matrizes curriculares                | Coordenação             |
| 📝 Cadastrar Questões        | Inclusão manual de questões inéditas ou adaptadas            | Equipe de Professores     |
| 🎯 Gerenciar Competências    | Alinhamento do banco de itens com as diretrizes do MEC          | Equipe de Professores     |

---

## 👥 Equipe

**Professor Orientador / Product Owner:** Prof. Marcelo Bezerra

| Integrante                    | Matrícula |
| ----------------------------- | ---------- |
| Gustavo Viana Lima            | 2320257    |
| Karlos Eduardo Sousa Pinto    | 2320262    |
| Kayo Nicholas Gomes Alcantara | 2320258    |

### 🧩 Contribuições por Integrante

| Integrante                              | Entregáveis                                                                                                                                                                                                                                                   |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Gustavo Viana Lima**            | Documento de Visão, Ordenação de telas do protótipo                                                                                                                                                                                                        |
| **Karlos Eduardo Sousa Pinto**    | Diagrama de Implantação, Diagrama de Stakeholders, Diagrama de Componentes, Documento de Visão, Glossário, Protótipos, SRS, Revisão de Consistência, Regras de Negócio, Requisitos Funcionais, Requisitos Não Funcionais, Entrega_1, Entrega_2, Pitch |
| **Kayo Nicholas Gomes Alcantara** | Diagrama de Casos de Uso, Documento de Visão, Especificação dos Casos de Uso, Lista de Stakeholders, Requisitos Funcionais, Regras de Negócio, Requisitos Não Funcionais, Entrega_1                                                                      |

---

## 📁 Estrutura do Repositório

## 📁 Estrutura do Repositório

```
requisitos-2026-GRUPO.4/
│
├── docs/                          # Documentação do projeto
│   ├── 01_documento_visao.md      # Visão da demanda e proposta de valor
│   ├── 02_lista_stakeholders.md   # Partes interessadas detalhadas
│   ├── 03_glossario.md            # Glossário de termos do domínio
│   ├── 04_regras_de_negocio.md    # Regras de negócio do sistema
│   ├── 05_requisitos_funcionais.md  # Requisitos funcionais levantados
│   ├── 06_requisitos_nao_funcionais.md  # Requisitos não funcionais e restrições
│   ├── 07_SRS.md                  # Software Requirements Specification (IEEE 830)
│   ├── 08_revisao_consistencia.md # Relatório de revisão e consistência dos requisitos
│   └── 09_acesso_prototipo.md     # Guia de acesso e navegação no protótipo
│
├── modelagem/                     # Especificações de Casos de Uso
│   ├── CDU-01_Efetuar_Cadastro_e_Login.md          # Autenticação via sistema acadêmico
│   ├── CDU-02_Filtrar_Banco_de_Dados.md            # Busca avançada no banco de questões
│   ├── CDU-03_Visualizar_Resolucao_Mapa_Mental.md  # Resolução visual comentada
│   ├── CDU-04_Realizar_Simulado_Cronometrado.md    # Simulado com controle de tempo
│   ├── CDU-05_Participar_Forum_Debate.md           # Discussão colaborativa por questão
│   ├── CDU-06_Visualizar_Dashboard_Forum.md        # Métricas de desempenho e engajamento
│   ├── CDU-07_Sincronizar_Questoes_INEP.md         # Importação de questões e gabaritos oficiais
│   ├── CDU-08_Gerenciar_Usuarios.md                # Controle de acesso de estudantes e professores
│   ├── CDU-09_Gerenciar_Cursos.md                  # Cadastro e vinculação de matrizes curriculares
│   ├── CDU-10_Gerenciar_Competencias_Questoes.md   # Alinhamento com diretrizes do MEC
│   └── CDU-11_Cadastrar_Questoes.md                # Inclusão manual de questões inéditas ou adaptadas
│
├── diagramas/                     # Diagramas UML do sistema
│   ├── Diagrama_Caso_de_Uso.png   # Diagrama geral de casos de uso
│   ├── Diagrama_de_Componentes.png  # Arquitetura de componentes do sistema
│   ├── Diagrama_Implantacao.png   # Diagrama de implantação e infraestrutura
│   └── Diagrama_Stakeholders.png  # Mapa de partes interessadas
│
├── prototipos/                    # Telas do protótipo (24 telas)
│
└── entregas/                      # PDFs e arquivos das entregas acadêmicas
    ├── P1_GRUPO4.pdf              # Entrega 1: visão, stakeholders e requisitos
    ├── P2_GRUPO4.pdf              # Entrega 2: modelagem, SRS e protótipos
    └── PITCH_GRUPO4.html          # Apresentação de pitch do projeto
```

---

## 📐 Diagramas

<table>
  <tr>
    <td align="center"><b>Diagrama de Casos de Uso</b></td>
    <td align="center"><b>Diagrama de Componentes</b></td>
  </tr>
  <tr>
    <td><img src="diagramas/Diagrama_Caso_de_Uso.png" alt="Diagrama de Casos de Uso"/></td>
    <td><img src="diagramas/Diagrama_de_Componentes.png" alt="Diagrama de Componentes"/></td>
  </tr>
  <tr>
    <td align="center"><b>Diagrama de Implantação</b></td>
    <td align="center"><b>Mapa de Stakeholders</b></td>
  </tr>
  <tr>
    <td><img src="diagramas/Diagrama_Implantacao.png" alt="Diagrama de Implantação"/></td>
    <td><img src="diagramas/Diagrama_Stakeholders.png" alt="Stakeholders"/></td>
  </tr>
</table>

---

## 🗂️ Entregas Acadêmicas

| Entrega         | Descrição                                                                                               | Arquivo                                      |
| --------------- | --------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **P1**    | Visão da demanda, stakeholders, requisitos funcionais e não funcionais, glossário e regras de negócio | [P1_GRUPO4.pdf](entregas/P1_GRUPO4.pdf)         |
| **P2**    | Modelagem de casos de uso (CDU-01 a CDU-11), SRS (IEEE 830), protótipos e revisão de consistência      | [P2_GRUPO4.pdf](entregas/P2_GRUPO4.pdf)         |
| **PITCH** | Apresentação de pitch do projeto em formato web interativo                                              | [PITCH_GRUPO4.html](entregas/PITCH_GRUPO4.html) |

---

## 🛠️ Disciplina e Contexto

- **Disciplina:** Requisitos e Modelagem de Sistemas
- **Instituição:** Universidade de Fortaleza — UNIFOR
- **Semestre:** 2026.1
- **Metodologia:** Documento de Visão · SRS IEEE 830 · UML · Prototipação
