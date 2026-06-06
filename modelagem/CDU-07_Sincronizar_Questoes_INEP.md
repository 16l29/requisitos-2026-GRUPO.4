# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |
| 06/06/2026 | 1.1     | Adição de referências | Karlos Eduardo |

---

## 1. Nome do Caso de Uso

Sincronizar Questões do INEP

---

## 2. Objetivo

Permitir que o Sistema ENADE obtenha e atualize automaticamente o banco de questões a partir do Sistema INEP, mantendo o acervo de questões atualizado para uso pelos estudantes.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Sistema INEP** — sistema externo que provê as questões oficiais do ENADE por meio de integração (include).

### 4.2 Secundário

**Coordenação** — ator que pode acionar manualmente a sincronização ou monitorar seu status.

---

## 5. Precondições

- O Sistema ENADE deve possuir configuração de integração ativa com o Sistema INEP.
- As credenciais de acesso ao Sistema INEP devem estar válidas e configuradas.

---

## 6. Fluxo Principal

### P1. O sistema dispara a sincronização automaticamente conforme agendamento configurado

### P2. O sistema realiza a autenticação junto ao Sistema INEP

### P3. O Sistema INEP confirma a autenticação e disponibiliza o endpoint de questões

### P4. O sistema solicita as questões novas ou atualizadas desde a última sincronização

### P5. O Sistema INEP retorna o conjunto de questões conforme solicitado

### P6. O sistema valida e processa os dados recebidos

### P7. O sistema insere as questões novas e atualiza as questões existentes no banco de dados local

### P8. O sistema registra o log da sincronização com data, hora e quantidade de questões processadas

---

## 7. Fluxos Alternativos

### A1. Coordenação aciona a sincronização manualmente

#### A1.1. A coordenação acessa o painel de administração e seleciona "Sincronizar questões do INEP"

#### A1.2. O sistema exibe confirmação solicitando autorização para iniciar a sincronização

#### A1.3. A coordenação confirma a ação

#### A1.4. O fluxo segue a partir do P2

### A2. Sincronização parcial — apenas questões de um período específico

#### A2.1. No A1.3, a coordenação informa um intervalo de datas para a sincronização

#### A2.2. O sistema filtra a solicitação ao Sistema INEP conforme o período informado

#### A2.3. O fluxo segue a partir do P4

---

## 8. Fluxos de Exceção

### E1. Falha na autenticação com o Sistema INEP

#### E1.1. No P2, o Sistema INEP rejeita as credenciais enviadas

#### E1.2. O sistema registra o erro no log e notifica a coordenação

#### E1.3. O sistema encerra a tentativa de sincronização

### E2. Timeout ou indisponibilidade do Sistema INEP

#### E2.1. No P3 ou P5, o Sistema INEP não responde dentro do tempo limite

#### E2.2. O sistema registra a falha no log com o motivo e data/hora

#### E2.3. O sistema agenda uma nova tentativa automaticamente conforme política de retry

### E3. Dados recebidos com formato inválido

#### E3.1. No P6, o sistema identifica questões com estrutura de dados incompatível

#### E3.2. O sistema descarta as questões inválidas, registra no log e prossegue com as demais

#### E3.3. O sistema notifica a coordenação sobre os itens rejeitados

---

## 9. Pós-condições

- O banco de questões do Sistema ENADE está atualizado com os dados recebidos do Sistema INEP.
- Um registro de log da sincronização é armazenado para auditoria.

---

## 10. Requisitos Não Funcionais

- A sincronização deve ser concluída em até 10 minutos para lotes de até 1.000 questões.
- O processo não deve impactar a disponibilidade do sistema para os usuários durante a sincronização.
- Toda comunicação com o Sistema INEP deve utilizar protocolo seguro (HTTPS/TLS).

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Baixa — acionada automaticamente por agendamento periódico (ex.: diário ou semanal) ou manualmente pela coordenação após publicações do INEP.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Verificar junto ao INEP a disponibilidade e documentação da API de integração.
- Definir política de versionamento das questões para controle de alterações retroativas.
- Avaliar estratégia de rollback em caso de sincronização com dados corrompidos.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- Documentação da API do Sistema INEP
- CDU-02: Filtrar Banco de Dados
- **RN03** — Imutabilidade das Questões Oficiais

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
