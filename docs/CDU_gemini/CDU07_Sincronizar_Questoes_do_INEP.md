# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU07: Sincronizar Questões do INEP

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Sincronizar Questões do INEP

## 2. Objetivo
Realizar a integração e importação automática das provas e gabaritos diretamente das bases ou dados oficiais do INEP para atualização contínua do sistema.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Coordenação (Caso o processo seja manual/startado por ela) ou rotina automatizada interna do sistema.

### 4.2 Secundário
Sistema INEP (repositório externo ou API de dados de onde as questões são consumidas).

## 5. Precondições
O endpoint de dados ou servidor do INEP deve estar acessível e conectado à rede corporativa.

## 6. Fluxo Principal
### P1. Disparar Comando de Sincronização
A Coordenação acessa o módulo avançado de dados e clica em "Sincronizar Banco com o INEP".

### P2. Autenticar e Conectar ao Provedor
O sistema estabelece conexão segura via protocolo HTTP/API com os servidores de dados públicos do INEP.

### P3. Identificar e Baixar Novas Provas
O sistema verifica se há novas edições do ENADE publicadas que não constam na base local e realiza o download dos metadados, questões e gabaritos oficiais.

### P4. Parsear e Registrar Dados
O sistema trata os textos, associa as imagens explicativas e persiste as novas questões no banco de dados, categorizando por ano e curso.

### P5. Emitir Relatório de Sucesso
O sistema encerra a conexão externa e exibe para a Coordenação a lista de questões inseridas.

## 7. Fluxos Alternativos
Não se aplica.

## 8. Fluxos de Exceção
### E1. Instabilidade do Servidor Externo do INEP
#### E1.1. No passo P2, se o servidor do INEP não responder ou retornar erro de timeout.
#### E1.2. O sistema realiza 3 tentativas automáticas de reconexão. Se persistir, o caso de uso é abortado com o alerta: "Erro de comunicação com o Sistema INEP. Tente novamente mais tarde".

## 9. Pós-condições
As alterações ou consultas do caso de uso são persistidas/efetivadas com sucesso e o estado do sistema é atualizado de forma consistente.

## 10. Requisitos Não Funcionais
Não se aplica.

## 11. Ponto de Extensão
Não se aplica.

## 12. Frequência de Utilização
Baixa

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
