# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                        | Autor         |
| ---------- | ------- | ---------------------------------- | ------------- |
| 01/06/2026 | 1.0     | Criação do artefato              | nome do autor |

---

## 1. Nome do Caso de Uso

Cadastrar Questões

---

## 2. Objetivo

Permitir que a equipe de professores cadastre manualmente novas questões no banco de dados do Sistema ENADE, podendo aproveitá-las a partir do acervo sincronizado do INEP ou criá-las de forma original, garantindo a ampliação e curadoria do banco de questões disponível para estudantes.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Equipe de Professores** — ator responsável por cadastrar e revisar questões no sistema.

### 4.2 Secundário

**Sistema INEP** — sistema externo incluído (`«include»` via CDU-07) que fornece questões oficiais como base de referência ou importação para o cadastro.

---

## 5. Precondições

- A equipe de professores deve estar autenticada no Sistema ENADE com perfil de professor.
- O caso de uso **CDU-07 (Sincronizar Questões do INEP)** deve ter sido executado ao menos uma vez, de modo que o banco do INEP esteja disponível como referência para importação.

---

## 6. Fluxo Principal

### P1. O professor acessa o painel de gestão pedagógica e seleciona "Cadastrar Questões"

### P2. O sistema exibe as opções de origem da questão: "Criar questão original" ou "Importar do banco INEP"

### P3. O professor seleciona "Importar do banco INEP"

### P4. O sistema executa o include do CDU-07 (Sincronizar Questões do INEP) para garantir que o acervo do INEP esteja atualizado

### P5. O sistema exibe o acervo de questões sincronizadas do INEP com filtros por área, ano e competência

### P6. O professor seleciona uma ou mais questões do acervo do INEP

### P7. O sistema pré-preenche o formulário de cadastro com os dados da questão importada (enunciado, alternativas, gabarito, área, ano, competências)

### P8. O professor revisa e complementa os dados exibidos (ex.: adiciona comentários pedagógicos, ajusta competências)

### P9. O professor confirma o cadastro da questão

### P10. O sistema valida os dados e registra a questão no banco de questões do Sistema ENADE

### P11. O sistema exibe mensagem de confirmação: "Questão cadastrada com sucesso"

---

## 7. Fluxos Alternativos

### A1. Professor cadastra questão original (sem importação do INEP)

#### A1.1. No P2, o professor seleciona "Criar questão original"

#### A1.2. O sistema exibe o formulário de cadastro em branco com os campos: enunciado, alternativas (mínimo de 4), gabarito, área de conhecimento, nível de dificuldade, competências associadas e referências bibliográficas

#### A1.3. O professor preenche todos os campos obrigatórios

#### A1.4. O professor adiciona opcionalmente imagens, fórmulas ou gráficos ao enunciado

#### A1.5. O professor confirma o cadastro

#### A1.6. O fluxo retorna ao P10

### A2. Professor cadastra múltiplas questões em lote a partir do INEP

#### A2.1. No P6, o professor seleciona múltiplas questões do acervo do INEP

#### A2.2. O sistema exibe um resumo das questões selecionadas para confirmação

#### A2.3. O professor confirma a importação em lote

#### A2.4. O sistema processa e registra todas as questões selecionadas, aplicando os metadados do INEP

#### A2.5. O sistema exibe relatório com a quantidade de questões importadas com sucesso e eventuais erros

#### A2.6. O fluxo retorna ao P11

### A3. Professor edita uma questão recém-cadastrada antes de finalizar

#### A3.1. Após o P10, o professor seleciona "Editar questão cadastrada"

#### A3.2. O sistema abre o formulário de edição com os dados registrados

#### A3.3. O professor realiza os ajustes e confirma

#### A3.4. O sistema atualiza o registro e exibe confirmação

---

## 8. Fluxos de Exceção

### E1. Banco do INEP indisponível no momento do include

#### E1.1. No P4, o sistema identifica que a sincronização com o INEP não pode ser executada (serviço fora do ar ou sem conectividade)

#### E1.2. O sistema exibe mensagem: "Não foi possível acessar o banco do INEP no momento. Você pode criar uma questão original ou tentar novamente mais tarde"

#### E1.3. O fluxo segue para A1 (questão original) ou encerra conforme escolha do professor

### E2. Questão do INEP já existente no banco local

#### E2.1. No P10, o sistema identifica que a questão importada já foi previamente cadastrada (por código ou conteúdo duplicado)

#### E2.2. O sistema exibe alerta: "Esta questão já consta no banco de questões do sistema"

#### E2.3. O professor decide entre manter o registro existente ou sobrescrever com os dados importados

### E3. Campos obrigatórios não preenchidos

#### E3.1. No P9 ou A1.5, o professor tenta confirmar o cadastro sem preencher todos os campos obrigatórios

#### E3.2. O sistema destaca os campos em branco e exibe mensagem de validação

#### E3.3. O fluxo retorna ao passo de preenchimento correspondente

### E4. Gabarito não informado

#### E4.1. No P9, o sistema identifica que nenhuma alternativa foi marcada como gabarito

#### E4.2. O sistema exibe mensagem: "É obrigatório indicar a alternativa correta antes de salvar a questão"

#### E4.3. O fluxo retorna ao P8 ou A1.3

---

## 9. Pós-condições

- A questão é registrada no banco de questões do Sistema ENADE e fica disponível para uso nos casos de uso CDU-02 (Filtrar Banco de Dados), CDU-03 (Visualizar Resolução via Mapa Mental) e CDU-04 (Realizar Simulado Cronometrado).
- As competências associadas à questão são vinculadas conforme o CDU-10 (Gerenciar Competências das Questões).
- O log de cadastro registra o professor responsável, a origem da questão (INEP ou original) e a data/hora do cadastro.

---

## 10. Requisitos Não Funcionais

- O cadastro de uma questão individual deve ser concluído em até 3 segundos.
- O cadastro em lote de até 50 questões deve ser processado em até 15 segundos.
- Questões com imagens ou fórmulas devem suportar formatos PNG, JPEG e LaTeX.
- O sistema deve garantir unicidade das questões por código INEP para evitar duplicidades.

---

## 11. Ponto de Extensão

### PE1. Sincronizar Questões do INEP (CDU-07)

O presente caso de uso inclui obrigatoriamente o CDU-07 no passo P4, quando o professor opta por importar questões do banco do INEP. A sincronização é acionada para garantir que o acervo disponível para seleção esteja atualizado antes da importação.

---

## 12. Frequência de Utilização

Média — acionado pela equipe de professores periodicamente, especialmente após atualizações do banco do INEP ou no início de novos semestres letivos.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar mecanismo de revisão e aprovação de questões originais cadastradas pelos professores antes de sua publicação no banco (ex.: fluxo de aprovação pela coordenação).
- Considerar versionamento de questões para rastrear alterações ao longo do tempo.
- Verificar necessidade de suporte a fórmulas matemáticas no enunciado (LaTeX ou MathML).

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE (versão atualizada, jun/2026)
- CDU-07: Sincronizar Questões do INEP (`«include»`)
- CDU-10: Gerenciar Competências das Questões
- CDU-02: Filtrar Banco de Dados
- CDU-03: Visualizar Resolução via Mapa Mental
- CDU-04: Realizar Simulado Cronometrado

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
