# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU08: Gerenciar usuários

## Histórico de Versões

<!-- markdownlint-disable MD060 -->
| Data       | Versão | Descrição                                                                                        | Autor         |
| ---------- | ------- | -------------------------------------------------------------------------------------------------- | ------------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE.                       | Engenheiro de Requisitos |
<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso
Gerenciar usuários

## 2. Objetivo
Permitir que a Coordenação do curso tenha controle total sobre os perfis cadastrados (Estudantes e Professores), podendo editar permissões, inativar contas ou criar novos acessos.

## 3. Tipo de Caso de Uso
Concreto

## 4. Atores

### 4.1 Primário
Coordenação

### 4.2 Secundário
Não se aplica.

## 5. Precondições
O usuário logado deve possuir privilégios administrativos de Coordenação.

## 6. Fluxo Principal
### P1. Acessar Painel Administrativo
A Coordenação clica na opção de menu "Gerenciamento de Usuários".

### P2. Listagem Geral
O sistema apresenta uma tabela estruturada contendo todos os usuários cadastrados, exibindo Nome, Tipo de Perfil (Estudante/Professor), E-mail, Status (Ativo/Inativo) e ações de edição.

### P3. Selecionar Operação (CRUD)
A Coordenação busca um usuário específico através do filtro de pesquisa e seleciona a opção "Editar Perfil".

### P4. Modificar Informações e Salvar
A Coordenação altera as informações administrativas necessárias (ex: alterar status para Inativo) e clica em "Salvar Alterações".

### P5. Confirmar Operação
O sistema realiza as consistências no banco de dados e emite um pop-up de sucesso.

## 7. Fluxos Alternativos
### A1. Importação em Massa de Alunos
#### A1.1. No passo P2, a coordenação seleciona a opção "Importar Planilha".
#### A1.2. O sistema solicita um arquivo em formato CSV contendo os dados dos novos estudantes.
#### A1.3. O sistema processa a planilha e realiza o cadastro de todos os registros válidos automaticamente.

## 8. Fluxos de Exceção
### E1. Tentativa de Exclusão de Conta com Dependências Ativas
#### E1.1. No passo P4, se a coordenação tentar remover fisicamente a conta de um Professor que possui fóruns de debate ativos.
#### E1.2. O sistema impede a exclusão física e orienta o fluxo a realizar a inativação lógica da conta para preservar o histórico.

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
