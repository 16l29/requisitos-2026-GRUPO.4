# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                        | Autor         |
| ---------- | ------- | ---------------------------------- | ------------- |
| dd/mm/aaaa | 1.0     | Criação do artefato              | nome do autor |

---

## 1. Nome do Caso de Uso

Realizar Simulado Cronometrado

---

## 2. Objetivo

Permitir que o estudante realize um simulado com questões do banco de dados do ENADE sob controle de tempo, simulando as condições reais do exame.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Estudante** — ator que configura, inicia e responde ao simulado cronometrado.

### 4.2 Secundário

Não se aplica.

---

## 5. Precondições

- O estudante deve estar autenticado no Sistema ENADE.
- O banco de questões deve estar populado com ao menos uma questão disponível.

---

## 6. Fluxo Principal

### P1. O estudante acessa a funcionalidade "Simulado Cronometrado"

### P2. O sistema exibe as opções de configuração do simulado (número de questões, área, tempo)

### P3. O estudante define as configurações e inicia o simulado

### P4. O sistema monta a lista de questões conforme as configurações e inicia o cronômetro

### P5. O sistema exibe a primeira questão com o cronômetro em execução

### P6. O estudante lê o enunciado e seleciona uma alternativa de resposta

### P7. O estudante avança para a próxima questão

### P8. Os passos P6 e P7 se repetem até o estudante responder todas as questões ou o tempo se esgotar

### P9. O estudante finaliza o simulado ou o sistema encerra ao término do tempo

### P10. O sistema calcula e exibe o resultado do simulado com o percentual de acertos e gabarito

---

## 7. Fluxos Alternativos

### A1. Estudante pula uma questão sem respondê-la

#### A1.1. No P6, o estudante seleciona "Pular questão" sem marcar alternativa

#### A1.2. O sistema registra a questão como não respondida e avança para a próxima

#### A1.3. O fluxo retorna ao P6 com a próxima questão

### A2. Estudante revisa questões antes de finalizar

#### A2.1. No P9, antes de finalizar, o estudante seleciona "Revisar questões"

#### A2.2. O sistema exibe o painel de navegação com indicação de questões respondidas e não respondidas

#### A2.3. O estudante navega para a questão desejada e altera ou confirma a resposta

#### A2.4. O estudante retorna ao P9 e finaliza o simulado

---

## 8. Fluxos de Exceção

### E1. Tempo esgotado antes da conclusão

#### E1.1. No P8, o cronômetro chega a zero antes de o estudante finalizar

#### E1.2. O sistema encerra automaticamente o simulado e registra as respostas até aquele momento

#### E1.3. O fluxo segue para o P10

### E2. Perda de conexão durante o simulado

#### E2.1. Durante qualquer passo entre P5 e P9, o sistema detecta perda de conectividade

#### E2.2. O sistema salva o estado atual do simulado localmente ou em cache

#### E2.3. Ao restabelecer a conexão, o sistema oferece a opção de retomar o simulado do ponto salvo

### E3. Questões insuficientes para o número solicitado

#### E3.1. No P3, o sistema identifica que o número de questões disponíveis é inferior ao solicitado

#### E3.2. O sistema exibe mensagem informando a quantidade disponível e solicita confirmação para prosseguir

---

## 9. Pós-condições

- O resultado do simulado é registrado no histórico de desempenho do estudante.
- As questões respondidas e os erros são disponibilizados para revisão posterior.

---

## 10. Requisitos Não Funcionais

- O cronômetro deve ser preciso e não deve ser afetado por ações do usuário na interface.
- O sistema deve salvar automaticamente as respostas a cada questão respondida para evitar perda de dados.
- O tempo máximo padrão do simulado deve ser configurável pela coordenação.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Alta — utilizado regularmente pelos estudantes como ferramenta de preparação para o ENADE.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar a exibição de estatísticas comparativas de desempenho ao final do simulado (média da turma, média geral).
- Considerar notificação de aviso quando restar 10% do tempo.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- CDU-02: Filtrar Banco de Dados
- CDU-06: Visualizar Dashboard de Desempenho

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
