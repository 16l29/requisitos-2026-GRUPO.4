# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |
| 01/06/2026 | 1.1     | Alteração do ator primário de Coordenação para Equipe de Professores | Kayo Gomes |

---

## 1. Nome do Caso de Uso

Gerenciar Competências das Questões

---

## 2. Objetivo

Permitir que a equipe de professores cadastre, edite, associe e remova competências vinculadas às questões do banco de dados do Sistema ENADE, garantindo a correta classificação pedagógica das questões.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Equipe de Professores** — ator responsável pela gestão das competências associadas às questões.

### 4.2 Secundário

**Coordenação** — pode consultar as competências cadastradas para fins de supervisão pedagógica.

---

## 5. Precondições

- A equipe de professores deve estar autenticada no Sistema ENADE com perfil de professor.
- O banco de questões deve estar populado com ao menos uma questão cadastrada.

---

## 6. Fluxo Principal

### P1. O professor acessa o painel de gestão pedagógica e seleciona "Gerenciar Competências das Questões"

### P2. O sistema exibe a listagem de competências cadastradas com filtros disponíveis

### P3. O professor seleciona a ação desejada: cadastrar nova competência, editar, associar a questões ou remover

### P4. O sistema exibe o formulário ou a confirmação correspondente à ação selecionada

### P5. O professor preenche ou confirma as informações solicitadas

### P6. O sistema valida os dados e executa a operação

### P7. O sistema exibe mensagem de confirmação do resultado da operação

---

## 7. Fluxos Alternativos

### A1. Professor cadastra nova competência

#### A1.1. No P3, o professor seleciona "Cadastrar nova competência"

#### A1.2. O sistema exibe o formulário com campos: nome da competência, descrição, área de conhecimento e nível (ex.: básico, intermediário, avançado)

#### A1.3. O professor preenche os dados e confirma

#### A1.4. O sistema valida e registra a nova competência

#### A1.5. O fluxo retorna ao P7

### A2. Professor associa competências a questões

#### A2.1. No P3, o professor seleciona "Associar competências a questões"

#### A2.2. O sistema exibe a listagem de questões com filtros de busca

#### A2.3. O professor seleciona uma ou mais questões

#### A2.4. O sistema exibe as competências disponíveis para seleção

#### A2.5. O professor seleciona as competências e confirma a associação

#### A2.6. O sistema registra o vínculo entre as questões e as competências selecionadas

#### A2.7. O fluxo retorna ao P7

### A3. Professor edita uma competência existente

#### A3.1. No P3, o professor seleciona "Editar" na competência desejada

#### A3.2. O sistema exibe o formulário com os dados atuais da competência

#### A3.3. O professor realiza as alterações e confirma

#### A3.4. O sistema atualiza o registro da competência e propaga a alteração para todas as questões vinculadas

#### A3.5. O fluxo retorna ao P7

---

## 8. Fluxos de Exceção

### E1. Nome da competência já cadastrado

#### E1.1. No P6 (fluxo A1), o sistema identifica que já existe uma competência com o mesmo nome na mesma área

#### E1.2. O sistema exibe mensagem: "Já existe uma competência com este nome para esta área de conhecimento"

#### E1.3. O fluxo retorna ao A1.2

### E2. Tentativa de remoção de competência vinculada a questões

#### E2.1. No P3, o professor seleciona "Remover" para uma competência que possui questões associadas

#### E2.2. O sistema exibe alerta informando a quantidade de questões vinculadas

#### E2.3. O professor decide entre prosseguir com a remoção (desvinculando as questões) ou cancelar

### E3. Campos obrigatórios não preenchidos

#### E3.1. No P6, o sistema identifica campos obrigatórios em branco

#### E3.2. O sistema destaca os campos e exibe mensagem de validação

#### E3.3. O fluxo retorna ao passo de preenchimento correspondente

---

## 9. Pós-condições

- A competência é criada, atualizada, associada ou removida conforme a ação executada.
- As questões vinculadas refletem imediatamente as competências atualizadas nos filtros do banco de questões.

---

## 10. Requisitos Não Funcionais

- As operações de gestão de competências devem ser concluídas em até 2 segundos.
- A associação em lote de competências a múltiplas questões deve ser processada em até 5 segundos para lotes de até 100 questões.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Baixa — realizado principalmente após sincronização com o INEP ou revisão pedagógica das questões.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar a adoção de uma taxonomia padronizada de competências (ex.: Taxonomia de Bloom) para orientar o cadastro.
- Considerar a criação de relatórios de cobertura de competências por curso para suporte pedagógico.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE (versão atualizada, jun/2026)
- CDU-07: Sincronizar Questões do INEP
- CDU-09: Gerenciar Cursos
- CDU-11: Cadastrar Questões
- CDU-02: Filtrar Banco de Dados

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
