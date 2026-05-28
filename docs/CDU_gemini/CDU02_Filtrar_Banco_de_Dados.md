# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU02: Filtrar banco de dados

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Filtrar banco de dados

## 2. Objetivo
Permitir ao estudante realizar buscas refinadas no banco de dados de questões do ENADE utilizando critérios específicos para otimizar os estudos por temas.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Estudante

### 4.2 Secundário
Não se aplica.

## 5. Precondições
O estudante deve estar autenticado no sistema e o banco de dados deve conter questões cadastradas.

## 6. Fluxo Principal
### P1. Acessar Módulo de Questões
O estudante acessa a seção de "Banco de Questões" no menu principal.

### P2. Selecionar Filtros
O sistema exibe as opções de filtragem (Ano da Prova, Área de Conhecimento, Componente Curricular, Competência e Dificuldade). O estudante escolhe os parâmetros desejados.

### P3. Executar Filtragem
O estudante clica no botão "Aplicar Filtros".

### P4. Exibir Resultados
O sistema consulta o banco de dados e renderiza a listagem de questões que atendem exatamente aos critérios estabelecidos.

## 7. Fluxos Alternativos
### A1. Limpar Filtros Aplicados
#### A1.1. Após o passo P4, o estudante decide remover os filtros clicando em "Limpar Filtros".
#### A1.2. O sistema redefine os parâmetros e exibe a lista completa original de questões.

## 8. Fluxos de Exceção
### E1. Nenhuma Questão Encontrada
#### E1.1. No passo P4, se a combinação de filtros não retornar nenhum registro no banco de dados.
#### E1.2. O sistema exibe a mensagem: "Nenhuma questão atende aos filtros selecionados. Tente refinar sua busca".

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
