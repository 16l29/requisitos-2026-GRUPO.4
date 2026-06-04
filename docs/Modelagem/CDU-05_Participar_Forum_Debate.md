# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |

---

## 1. Nome do Caso de Uso

Participar de Fórum de Debate

---

## 2. Objetivo

Permitir que estudantes e professores interajam em fóruns de debate vinculados a questões ou temas do ENADE, trocando argumentos, esclarecendo dúvidas e enriquecendo o aprendizado coletivo.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Estudante** — ator que inicia a interação ao acessar e publicar no fórum de debate.

### 4.2 Secundário

**Professor** — ator que também participa do fórum, podendo responder, moderar e orientar discussões.

---

## 5. Precondições

- O ator (estudante ou professor) deve estar autenticado no Sistema ENADE.
- Deve existir ao menos um fórum de debate criado e ativo no sistema.

---

## 6. Fluxo Principal

### P1. O estudante acessa a seção "Fórum de Debate" no sistema

### P2. O sistema exibe a lista de tópicos de debate disponíveis

### P3. O estudante seleciona um tópico de interesse

### P4. O sistema exibe o tópico com todas as postagens existentes

### P5. O estudante redige uma nova postagem ou resposta no campo de texto disponível

### P6. O estudante publica a postagem

### P7. O sistema valida o conteúdo e registra a postagem no tópico

### P8. O sistema exibe a postagem publicada para todos os participantes do fórum

---

## 7. Fluxos Alternativos

### A1. Professor responde a uma postagem de estudante

#### A1.1. No P4, o professor visualiza uma postagem de estudante

#### A1.2. O professor seleciona a opção "Responder"

#### A1.3. O professor redige e publica sua resposta

#### A1.4. O sistema registra a resposta associada à postagem original

#### A1.5. O fluxo retorna ao P8

### A2. Ator cria um novo tópico de debate

#### A2.1. No P2, o ator seleciona a opção "Novo tópico"

#### A2.2. O sistema exibe o formulário de criação de tópico

#### A2.3. O ator preenche o título, a descrição e opcionalmente vincula uma questão do banco

#### A2.4. O ator publica o novo tópico

#### A2.5. O sistema registra o tópico e o exibe na listagem

#### A2.6. O fluxo retorna ao P2

### A3. Ator edita uma postagem própria

#### A3.1. No P4, o ator seleciona a opção "Editar" em uma postagem de sua autoria

#### A3.2. O sistema habilita o campo de edição com o conteúdo original

#### A3.3. O ator realiza as alterações e confirma

#### A3.4. O sistema atualiza a postagem e registra o histórico de edição

---

## 8. Fluxos de Exceção

### E1. Postagem com conteúdo vazio

#### E1.1. No P6, o ator tenta publicar sem preencher o campo de texto

#### E1.2. O sistema exibe mensagem de validação: "O conteúdo da postagem não pode estar vazio"

#### E1.3. O fluxo retorna ao P5

### E2. Tópico encerrado ou arquivado

#### E2.1. No P3, o ator seleciona um tópico marcado como encerrado

#### E2.2. O sistema exibe o tópico em modo somente leitura, sem a opção de publicar

#### E2.3. O sistema informa que novas postagens não são permitidas neste tópico

### E3. Postagem excede o limite de caracteres

#### E3.1. No P6, o sistema identifica que o texto supera o limite permitido

#### E3.2. O sistema exibe mensagem indicando o limite e a quantidade excedida

#### E3.3. O fluxo retorna ao P5

---

## 9. Pós-condições

- A postagem é registrada no fórum e visível a todos os participantes autorizados.
- A participação do ator é contabilizada para o dashboard de desempenho do fórum.

---

## 10. Requisitos Não Funcionais

- O fórum deve suportar postagens simultâneas sem perda de dados.
- A publicação deve ser processada e exibida em até 2 segundos.
- O histórico de edições deve ser preservado para fins de auditoria.

---

## 11. Ponto de Extensão

- **PE1. Visualizar Dashboard de Desempenho do Fórum** — ao participar do fórum, o ator pode consultar seu desempenho e engajamento via o CDU-06.

---

## 12. Frequência de Utilização

Média — utilizado regularmente durante períodos de preparação para o ENADE, com maior intensidade antes do exame.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar mecanismo de denúncia de postagens inadequadas.
- Considerar notificações para o ator quando sua postagem receber respostas.
- Verificar necessidade de moderação prévia para publicação de novos tópicos.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- CDU-06: Visualizar Dashboard de Desempenho de Fórum de Debate

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
