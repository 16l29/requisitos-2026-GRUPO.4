# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - CDU01: Efetuar cadastro e login

## Histórico de Versões

<!-- markdownlint-disable MD060 -->

| Data       | Versão | Descrição                                                                    | Autor      |
| ---------- | ------- | ------------------------------------------------------------------------------ | ---------- |
| 28/05/2026 | 1.0     | Especificação inicial do caso de uso extraído do diagrama do Sistema ENADE. | Kayo Gomes |

<!-- markdownlint-enable MD060 -->

## 1. Nome do Caso de Uso

Efetuar cadastro e login

## 2. Objetivo

Permitir que o estudante se registre no Sistema ENADE criando suas credenciais de acesso e realize a autenticação segura para acessar as demais funcionalidades.

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário

Estudante

### 4.2 Secundário

Sistema Acadêmico (utilizado para validar o vínculo e matrícula do estudante de forma integrada).

## 5. Precondições

O estudante deve possuir vínculo acadêmico ativo e o Sistema Acadêmico deve estar disponível para integração.

## 6. Fluxo Principal

### P1. Acessar a Plataforma

O estudante acessa a página inicial do Sistema ENADE e clica em "Cadastrar-se".

### P2. Preencher Formulário

O sistema exibe o formulário de cadastro. O estudante preenche os campos obrigatórios (Nome, CPF, Matrícula, Curso, E-mail e Senha) e confirma.

### P3. Validar Matrícula

O sistema se comunica de forma integrada com o Sistema Acadêmico para verificar a validade dos dados informados.

### P4. Confirmar Cadastro e Realizar Login

O sistema cria a conta, envia uma mensagem de confirmação e exibe a tela de login. O estudante insere as credenciais cadastradas e o sistema libera o acesso ao dashboard.

## 7. Fluxos Alternativos

### A1. Login Direto por Conta Integrada

#### A1.1. No passo P1, o estudante escolhe "Entrar com Credenciais Acadêmicas".

#### A1.2. O sistema redireciona o fluxo de autenticação para o provedor externo do Sistema Acadêmico.

#### A1.3. Após a confirmação, o usuário é logado diretamente no Sistema ENADE.

## 8. Fluxos de Exceção

### E1. Matrícula Não Encontrada ou Inválida

#### E1.1. No passo P3, se o Sistema Acadêmico retornar que os dados não conferem, o sistema bloqueia o cadastro.

#### E1.2. O sistema exibe a mensagem: "Matrícula não localizada no Sistema Acadêmico. Verifique os dados e tente novamente".

### E2. Usuário Já Cadastrado

#### E2.1. No passo P3, se o e-mail ou CPF já possuir registro ativo, o sistema interrompe o fluxo.

#### E2.2. O sistema exibe a mensagem: "Usuário já cadastrado. Utilize a recuperação de senha se necessário".

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
