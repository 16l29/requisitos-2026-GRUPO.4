# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU04: Realizar simulado cronometrado

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Realizar simulado cronometrado

## 2. Objetivo
Permitir que o estudante responda a um conjunto estruturado de questões simulando o ambiente real do exame ENADE, com tempo máximo controlado.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Estudante

### 4.2 Secundário
Não se aplica.

## 5. Precondições
O estudante deve estar autenticado e a base de dados deve conter questões suficientes para compor o simulado.

## 6. Fluxo Principal
### P1. Iniciar Simulado
O estudante acessa "Simulados" e seleciona a opção "Novo Simulado Cronometrado".

### P2. Configurar Parâmetros
O estudante escolhe a quantidade de questões ou seleciona o modelo oficial (padrão ENADE) e clica em "Iniciar".

### P3. Exibir Caderno e Disparar Cronômetro
O sistema monta o simulado, dispara a contagem regressiva do tempo regulamentar em tela e exibe a primeira questão.

### P4. Responder Questões
O estudante navega pelas questões inserindo suas respostas. O progresso é salvo automaticamente a cada passo.

### P5. Concluir Simulado
O estudante responde a todas as questões e clica em "Finalizar e Enviar".

### P6. Apresentar Desempenho
O sistema encerra o cronômetro, processa os acertos e erros e direciona o estudante para a tela de feedback do simulado.

## 7. Fluxos Alternativos
### A1. Pausar Simulado (Modo de Treino)
#### A1.1. No passo P4, se a configuração permitir, o estudante pode clicar em "Pausar".
#### A1.2. O sistema congela o cronômetro e salva o estado atual do progresso para retomada futura.

## 8. Fluxos de Exceção
### E1. Tempo Limite Esgotado
#### E1.1. No passo P4, se o cronômetro chegar a zero antes do estudante realizar a submissão manual.
#### E1.2. O sistema interrompe as interações imediatamente, salva as respostas preenchidas e submete o simulado de forma compulsória, exibindo a mensagem: "Tempo esgotado! Seu simulado foi enviado automaticamente".

## 9. Pós-condições
As alterações ou consultas do caso de uso são persistidas/efetivadas com sucesso e o estado do sistema é atualizado de forma consistente.

## 10. Requisitos Não Funcionais
Não se aplica.

## 11. Ponto de Extensão
Não se aplica.

## 12. Frequência de Utilização
Alta

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
