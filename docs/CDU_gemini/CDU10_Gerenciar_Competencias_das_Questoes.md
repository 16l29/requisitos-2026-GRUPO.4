# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU10: Gerenciar competências das questões

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Gerenciar competências das questões

## 2. Objetivo
Permitir à Coordenação mapear as diretrizes pedagógicas e competências oficiais do ENADE para cada questão individual do banco de dados, habilitando a inteligência analítica do sistema.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Coordenação

### 4.2 Secundário
Não se aplica.

## 5. Precondições
Existirem questões já cadastradas na base sem o devido mapeamento pedagógico associado.

## 6. Fluxo Principal
### P1. Abrir Matriz de Mapeamento
A Coordenação acessa a área de "Mapeamento de Competências das Questões" no painel de controle.

### P2. Selecionar Questões Pendentes
O sistema exibe uma lista de questões que necessitam de categorização de competência. A Coordenação escolhe uma questão para editar.

### P3. Associar Habilidades Pedagógicas
O sistema abre o detalhe da questão ao lado de uma lista com as competências institucionais cadastradas. A coordenação checa os marcadores (checkboxes) corretos correspondentes àquela questão.

### P4. Persistir Associação
A Coordenação clica no comando "Vincular Competências". O sistema processa os relacionamentos e atualiza as chaves na tabela de junção correspondente.

## 7. Fluxos Alternativos
Não se aplica.

## 8. Fluxos de Exceção
### E1. Ausência de Seleção de Competência
#### E1.1. No passo P4, se a Coordenação clicar em salvar sem marcar nenhuma competência para a questão.
#### E1.2. O sistema bloqueia o envio e solicita: "Selecione pelo menos uma competência ou habilidade para salvar o vínculo pedagógico da questão".

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
