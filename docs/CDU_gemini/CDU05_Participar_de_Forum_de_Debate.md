# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU05: Participar de fórum de debate

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Participar de fórum de debate

## 2. Objetivo
Fornecer um ambiente colaborativo onde estudantes e professores interagem criando tópicos, tirando dúvidas e debatendo resoluções de questões.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Estudante ou Professor (ambos iniciam de forma idêntica).

### 4.2 Secundário
Não se aplica.

## 5. Precondições
O usuário deve estar autenticado na plataforma.

## 6. Fluxo Principal
### P1. Acessar Fórum
O ator acessa a aba "Fórum de Debate" associada a uma disciplina ou a uma questão específica.

### P2. Visualizar e Selecionar Discussão
O sistema lista as discussões existentes. O ator seleciona um tópico ou opta por "Criar Novo Tópico".

### P3. Publicar Mensagem
O ator digita sua dúvida, argumento ou resolução no campo de texto e clica em "Publicar Mensagem".

### P4. Atualizar Feed
O sistema salva a postagem no banco de dados e atualiza a linha do tempo do fórum para que os demais participantes visualizem.

## 7. Fluxos Alternativos
### A1. Exclusão/Edição de Comentário
#### A1.1. Após o passo P4, o autor do comentário clica em "Editar" ou "Excluir".
#### A1.2. O sistema atualiza ou remove logicamente a postagem do banco de dados.

## 8. Fluxos de Exceção
### E1. Violação de Regras ou Conteúdo Vazio
#### E1.1. No passo P3, se o ator tentar publicar sem texto ou contendo caracteres inválidos/palavras proibidas.
#### E1.2. O sistema impede a publicação e apresenta o alerta correspondente.

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
