# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU03: Visualizar resolução via mapa mental

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Visualizar resolução via mapa mental

## 2. Objetivo
Fornecer ao estudante uma alternativa pedagógica visual (diagrama ou mapa mental) para entender a resolução de uma determinada questão.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Estudante

### 4.2 Secundário
Não se aplica.

## 5. Precondições
O estudante deve ter selecionado ou respondido uma questão que possua uma resolução gráfica mapeada.

## 6. Fluxo Principal
### P1. Solicitar Resolução Gráfica
O estudante, ao visualizar o gabarito ou o detalhe de uma questão específica, clica na opção "Visualizar Mapa Mental".

### P2. Renderizar Mapa
O sistema busca o arquivo ou estrutura de dados correspondente ao mapa conceitual daquela questão.

### P3. Exibir Conteúdo Interativo
O sistema renderiza a interface visual do mapa mental na tela, permitindo que o estudante expanda os nós explicativos e compreenda a relação entre as competências avaliadas.

## 7. Fluxos Alternativos
Não se aplica.

## 8. Fluxos de Exceção
### E1. Mapa Mental Indisponível
#### E1.1. No passo P2, se o sistema identificar que aquela questão específica ainda não possui um mapa mental associado.
#### E1.2. O sistema exibe a mensagem: "Mapa mental indisponível para esta questão. Exibindo apenas a resolução textual tradicional".

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
