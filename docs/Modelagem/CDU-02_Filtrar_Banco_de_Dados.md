# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |

---

## 1. Nome do Caso de Uso

Filtrar Banco de Dados

---

## 2. Objetivo

Permitir que o estudante aplique filtros sobre o banco de questões do Sistema ENADE, refinando a seleção de questões por critérios como área de conhecimento, ano, disciplina ou competência.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Estudante** — ator que inicia e opera a filtragem do banco de questões.

### 4.2 Secundário

Não se aplica.

---

## 5. Precondições

- O estudante deve estar autenticado no Sistema ENADE.
- O banco de questões deve estar populado com questões sincronizadas.

---

## 6. Fluxo Principal

### P1. O estudante acessa a seção de banco de questões no sistema

### P2. O sistema exibe a listagem de questões disponíveis com os filtros disponíveis

### P3. O estudante seleciona um ou mais critérios de filtro (ex.: ano, área, disciplina, competência)

### P4. O estudante aplica os filtros selecionados

### P5. O sistema processa os critérios e retorna as questões que correspondem à seleção

### P6. O sistema exibe a listagem filtrada de questões

### P7. O estudante visualiza e interage com as questões retornadas

---

## 7. Fluxos Alternativos

### A1. Estudante limpa os filtros aplicados

#### A1.1. No P6, o estudante seleciona a opção "Limpar filtros"

#### A1.2. O sistema remove todos os critérios selecionados e exibe a listagem completa de questões

#### A1.3. O fluxo retorna ao P2

### A2. Estudante salva a combinação de filtros como favorito

#### A2.1. No P6, o estudante seleciona a opção "Salvar filtro"

#### A2.2. O sistema solicita um nome para o conjunto de filtros

#### A2.3. O estudante informa o nome e confirma

#### A2.4. O sistema armazena a configuração de filtro para uso futuro

---

## 8. Fluxos de Exceção

### E1. Nenhuma questão encontrada com os filtros aplicados

#### E1.1. No P5, o sistema não localiza questões correspondentes aos critérios informados

#### E1.2. O sistema exibe mensagem: "Nenhuma questão encontrada para os filtros selecionados"

#### E1.3. O fluxo retorna ao P3 para nova seleção de critérios

### E2. Filtros incompatíveis entre si

#### E2.1. O estudante seleciona uma combinação de critérios mutuamente exclusivos

#### E2.2. O sistema exibe alerta indicando a incompatibilidade

#### E2.3. O fluxo retorna ao P3

---

## 9. Pós-condições

- O estudante visualiza a listagem de questões filtradas conforme os critérios selecionados.
- Os filtros aplicados são mantidos enquanto a sessão estiver ativa.

---

## 10. Requisitos Não Funcionais

- A consulta filtrada deve ser retornada em até 2 segundos.
- O sistema deve suportar filtros combinados sem degradação de desempenho.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Alta — utilizado frequentemente por estudantes para personalizar o estudo por área ou período.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar a inclusão de filtros avançados como nível de dificuldade e taxa de acerto da turma.
- Considerar persistência dos filtros entre sessões para melhor experiência do usuário.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- CDU-09: Sincronizar Questões do INEP

---

## 16. Checklist de Validação do Artefato (CDU)

### 16.1 Estrutura mínima

- [ ] Nome do caso de uso iniciado com verbo no infinitivo.
- [ ] Objetivo claro, direto e com foco em um objetivo principal.
- [ ] Tipo do caso de uso informado (concreto/abstrato), quando aplicável.
- [ ] Atores primário e secundários identificados corretamente.
- [ ] Precondições registradas (ou seção marcada como "Não se aplica").
- [ ] Fluxo principal completo e coerente com o objetivo.
- [ ] Fluxos alternativos e de exceção definidos quando necessários.
- [ ] Pós-condições registradas (ou seção marcada como "Não se aplica").
- [ ] Requisitos não funcionais específicos do CDU registrados, quando existirem.
- [ ] Pontos de extensão identificados corretamente, quando existirem.
- [ ] Frequência de utilização estimada.

### 16.2 Qualidade da especificação

- [ ] Passos escritos com linguagem simples e objetiva.
- [ ] Ações descritas com verbos no presente do indicativo (3ª pessoa).
- [ ] Alternância entre ação do ator e ação da solução está clara.
- [ ] Não há ambiguidade (termos vagos sem detalhe técnico).
- [ ] Regras de negócio e mensagens estão referenciadas quando necessário.

### 16.3 Consistência e rastreabilidade

- [ ] Pontos de entrada e saída dos fluxos alternativos estão explícitos.
- [ ] Fluxos de exceção estão vinculados aos passos corretos da solução.
- [ ] Referências internas entre passos (retorna/segue para) estão corretas.
- [ ] Interface visual (IV1 etc.) está coerente com o fluxo descrito.
- [ ] Referências para visão da demanda, glossário e RNF estão atualizadas.

### 16.4 Revisão final

- [ ] Não há contradições entre seções do artefato.
- [ ] Links internos e externos foram validados.
- [ ] Documento revisado por pares.
- [ ] Artefato pronto para uso em desenvolvimento e testes.
