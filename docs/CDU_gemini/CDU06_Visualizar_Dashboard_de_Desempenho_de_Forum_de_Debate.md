# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU06: Visualizar dashboard de desempenho de fórum de debate

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Visualizar dashboard de desempenho de fórum de debate

## 2. Objetivo
Apresentar estatísticas gráficas, indicadores de engajamento, número de postagens e acertos analíticos das discussões para os estudantes e professores.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Estudante ou Professor.

### 4.2 Secundário
Não se aplica.

## 5. Precondições
O usuário deve possuir dados ou interações históricas armazenadas no fórum de debates.

## 6. Fluxo Principal
### P1. Solicitar Painel Analítico
O ator acessa o menu do perfil e clica em "Dashboard do Fórum".

### P2. Consolidar Métricas
O sistema contabiliza as interações (posts criados, respostas enviadas, curtidas recebidas e tópicos resolvidos).

### P3. Exibir Gráficos
O sistema renderiza os indicadores em formato de painel interativo com gráficos de engajamento e barras de desempenho por disciplina.

## 7. Fluxos Alternativos
Não se aplica.

## 8. Fluxos de Exceção
### E1. Ausência de Dados de Interação
#### E1.1. No passo P2, se o usuário for novo e não possuir nenhuma atividade registrada no fórum.
#### E1.2. O sistema renderiza o layout do dashboard zerado com a mensagem informativa: "Você ainda não participou das discussões. Interaja nos fóruns para gerar métricas de desempenho!".

## 9. Pós-condições
As alterações ou consultas do caso de uso são persistidas/efetivadas com sucesso e o estado do sistema é atualizado de forma consistente.

## 10. Requisitos Não Funcionais
Não se aplica.

## 11. Ponto de Extensão
Não se aplica.

## 12. Frequência de Utilização
Média

## 13. Interface Visual
Não se aplica.

## 14. Observações
Não se aplica.

## 15. Referências
* Diagrama_Caso_de_uso.png

## 16. Checklist de Validação do Artefato (CDU)

### 16.1 Estrutura mínima
* [ ] Nome do caso de uso iniciado com verbo no infinitivo.
* [ ] Objetivo claro, direto e com foco em um objetivo principal.
* [ ] Tipo do caso de uso informado (concreto/abstrato), quando aplicável.
* [ ] Atores primário e secundários identificados corretamente.
* [ ] Precondições registradas (ou seção marcada como "Não se aplica").
* [ ] Fluxo principal completo e coerente com o objetivo.
* [ ] Fluxos alternativos e de exceção definidos quando necessários.
* [ ] Pós-condições registradas (ou seção marcada como "Não se aplica").
* [ ] Requisitos não funcionais específicos do CDU registrados, quando existirem.
* [ ] Pontos de extensão identificados corretamente, quando existirem.
* [ ] Frequência de utilização estimada.

### 16.2 Qualidade da especificação
* [ ] Passos escritos com linguagem simples e objetiva.
* [ ] Ações descritas com verbos no presente do indicativo (3ª pessoa).
* [ ] Alternância entre ação do ator e ação da solução está clara.
* [ ] Não há ambiguidade (termos vagos sem detalhe técnico).
* [ ] Regras de negócio e mensagens estão referenciadas quando necessário.

### 16.3 Consistência e rastreabilidade
* [ ] Pontos de entrada e saída dos fluxos alternativos estão explícitos.
* [ ] Fluxos de exceção estão vinculados aos passos corretos da solução.
* [ ] Referências internas entre passos (retorna/segue para) estão corretas.
* [ ] Interface visual (IV1 etc.) está coerente com o fluxo descrito.
* [ ] Referências para visão da demanda, glossário e RNF estão atualizadas.

### 16.4 Revisão final
* [ ] Não há contradições entre seções do artefato.
* [ ] Links internos e externos foram validados.
* [ ] Documento revisado por pares.
* [ ] Artefato pronto para uso em desenvolvimento e testes.
