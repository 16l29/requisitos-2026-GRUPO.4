# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                        | Autor         |
| ---------- | ------- | ---------------------------------- | ------------- |
| dd/mm/aaaa | 1.0     | Criação do artefato              | nome do autor |

---

## 1. Nome do Caso de Uso

Visualizar Resolução via Mapa Mental

---

## 2. Objetivo

Permitir que o estudante visualize a resolução de uma questão do banco de dados apresentada em formato de mapa mental, facilitando a compreensão dos conceitos e conexões envolvidos na resposta.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Estudante** — ator que solicita e consome a visualização da resolução em formato de mapa mental.

### 4.2 Secundário

Não se aplica.

---

## 5. Precondições

- O estudante deve estar autenticado no Sistema ENADE.
- A questão selecionada deve possuir resolução associada em formato de mapa mental.

---

## 6. Fluxo Principal

### P1. O estudante acessa o banco de questões e seleciona uma questão

### P2. O sistema exibe o enunciado completo da questão e as opções de resposta

### P3. O estudante seleciona a opção "Visualizar resolução via mapa mental"

### P4. O sistema carrega e exibe o mapa mental associado à resolução da questão

### P5. O estudante navega pelo mapa mental, expandindo e contraindo os nós de conteúdo

### P6. O estudante conclui a visualização

---

## 7. Fluxos Alternativos

### A1. Estudante alterna entre visualização em mapa mental e resolução textual

#### A1.1. No P4, o estudante seleciona a opção "Ver resolução em texto"

#### A1.2. O sistema exibe a resolução em formato textual convencional

#### A1.3. O estudante pode retornar à visualização em mapa mental selecionando "Ver mapa mental"

#### A1.4. O fluxo retorna ao P4

### A2. Estudante expande um nó específico do mapa mental

#### A2.1. No P5, o estudante clica em um nó do mapa mental

#### A2.2. O sistema exibe detalhes, explicações ou referências associadas ao nó selecionado

---

## 8. Fluxos de Exceção

### E1. Resolução em mapa mental não disponível para a questão

#### E1.1. No P3, o sistema identifica que a questão não possui mapa mental cadastrado

#### E1.2. O sistema exibe mensagem: "Resolução em mapa mental não disponível para esta questão"

#### E1.3. O sistema oferece a opção de visualizar a resolução em formato textual

#### E1.4. O fluxo encerra ou segue para A1.2 conforme escolha do estudante

### E2. Erro ao carregar o mapa mental

#### E2.1. No P4, ocorre falha no carregamento do recurso visual

#### E2.2. O sistema exibe mensagem de erro e oferece a opção de tentar novamente

---

## 9. Pós-condições

- O estudante visualizou a resolução da questão por meio de mapa mental.
- O acesso à resolução é registrado no histórico de atividades do estudante.

---

## 10. Requisitos Não Funcionais

- O mapa mental deve ser renderizado em até 3 segundos.
- A interface deve ser responsiva para diferentes tamanhos de tela.
- O mapa mental deve permitir zoom e navegação por arrastar.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Média — utilizado após a resolução ou tentativa de resolução de questões pelo estudante.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar o uso de bibliotecas de visualização de grafos (ex.: D3.js, MindMeister) para renderização do mapa mental.
- Considerar a possibilidade de o estudante exportar o mapa mental em formato de imagem.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
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
