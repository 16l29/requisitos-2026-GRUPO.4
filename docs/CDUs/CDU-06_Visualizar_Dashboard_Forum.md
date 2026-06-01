# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                        | Autor         |
| ---------- | ------- | ---------------------------------- | ------------- |
| dd/mm/aaaa | 1.0     | Criação do artefato              | nome do autor |

---

## 1. Nome do Caso de Uso

Visualizar Dashboard de Desempenho de Fórum de Debate

---

## 2. Objetivo

Permitir que estudantes e professores acompanhem métricas de engajamento e desempenho relacionadas à participação nos fóruns de debate do Sistema ENADE.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Estudante** — ator que acessa o dashboard para acompanhar seu próprio desempenho no fórum.

### 4.2 Secundário

**Professor** — ator que acessa o dashboard para monitorar o engajamento coletivo da turma nos fóruns.

---

## 5. Precondições

- O ator (estudante ou professor) deve estar autenticado no Sistema ENADE.
- Deve haver ao menos um registro de participação em fórum de debate para o ator ou para a turma.

---

## 6. Fluxo Principal

### P1. O estudante acessa a seção "Dashboard de Desempenho do Fórum" no sistema

### P2. O sistema coleta e processa os dados de participação do estudante nos fóruns

### P3. O sistema exibe o dashboard com as métricas de engajamento do estudante

### P3.1. O dashboard apresenta indicadores como: número de postagens, tópicos iniciados, respostas recebidas e curtidas

### P4. O estudante navega pelas métricas exibidas

### P5. O estudante seleciona um filtro de período ou tópico para refinar a visualização

### P6. O sistema atualiza o dashboard de acordo com os filtros selecionados

---

## 7. Fluxos Alternativos

### A1. Professor visualiza dashboard coletivo da turma

#### A1.1. No P1, o professor acessa a seção "Dashboard de Desempenho do Fórum"

#### A1.2. O sistema exibe opção de visualização individual e coletiva

#### A1.3. O professor seleciona "Visualizar turma"

#### A1.4. O sistema exibe métricas agregadas de participação de todos os estudantes vinculados ao professor

#### A1.5. O professor pode selecionar um estudante específico para visualizar seu desempenho individual

### A2. Estudante exporta o relatório de desempenho

#### A2.1. No P3, o estudante seleciona a opção "Exportar relatório"

#### A2.2. O sistema gera o relatório no formato selecionado (PDF ou CSV)

#### A2.3. O sistema disponibiliza o arquivo para download

---

## 8. Fluxos de Exceção

### E1. Sem dados de participação disponíveis

#### E1.1. No P2, o sistema não localiza registros de participação para o ator

#### E1.2. O sistema exibe mensagem informativa: "Você ainda não possui participações registradas no fórum"

#### E1.3. O sistema exibe sugestão de acesso ao CDU-05 para iniciar a participação

### E2. Falha no carregamento dos dados do dashboard

#### E2.1. No P2, ocorre falha ao consultar os dados de participação

#### E2.2. O sistema exibe mensagem de erro e oferece a opção de recarregar

---

## 9. Pós-condições

- O ator visualizou as métricas de desempenho de sua participação ou da turma no fórum.
- Os dados exibidos refletem o estado mais recente registrado no sistema.

---

## 10. Requisitos Não Funcionais

- O dashboard deve ser carregado em até 3 segundos.
- Os dados devem ser atualizados em tempo real ou com intervalo máximo de 5 minutos.
- A visualização deve ser responsiva para diferentes dispositivos.

---

## 11. Ponto de Extensão

- **PE1. Participar de Fórum de Debate** — o dashboard referencia o CDU-05, permitindo acesso direto ao fórum a partir da visualização de métricas.

---

## 12. Frequência de Utilização

Média — consultado periodicamente por estudantes e professores para acompanhar evolução no engajamento.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar inclusão de ranking de participação entre estudantes do mesmo curso ou turma.
- Considerar alertas automáticos para estudantes com baixo engajamento no fórum.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- CDU-05: Participar de Fórum de Debate

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
