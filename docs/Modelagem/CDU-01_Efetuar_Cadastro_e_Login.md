# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |
| 06/06/2026 | 1.1     | Atualização do fluxo para OAuth 2.0 e adição de referências | Karlos Eduardo |

---

## 1. Nome do Caso de Uso

Efetuar Cadastro e Login

---

## 2. Objetivo

Permitir que o estudante crie uma conta no Sistema ENADE e realize o acesso autenticado à plataforma.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Estudante** — ator que inicia o processo de cadastro ou login para acessar o sistema.

### 4.2 Secundário

**Sistema Acadêmico** — sistema externo incluído para validação ou integração de dados do estudante.

---

## 5. Precondições

- O estudante deve ter acesso à internet e ao endereço do Sistema ENADE.
- Para login, o estudante deve possuir cadastro prévio no sistema.

---

## 6. Fluxo Principal

### P1. O estudante acessa a página inicial do Sistema ENADE

### P2. O sistema exibe as opções de autenticação (ex.: "Entrar com Google" e "Acesso por E-mail/Senha")

### P3. O estudante seleciona a opção "Entrar com Google"

### P4. O sistema redireciona o estudante para a interface de autorização do provedor (Google OAuth)

### P5. O estudante seleciona sua conta institucional e autoriza o acesso

### P6. O sistema valida o domínio do e-mail recebido para garantir o acesso institucional

### P7. O sistema autentica o estudante, atribui o perfil correspondente e redireciona para a tela principal

---

## 7. Fluxos Alternativos

### A1. Estudante realiza cadastro pela primeira vez

#### A1.1. No P2, o estudante seleciona a opção "Cadastrar"

#### A1.2. O sistema exibe o formulário de cadastro

#### A1.3. O estudante preenche os campos obrigatórios (nome, e-mail, senha, curso, instituição)

#### A1.4. O estudante confirma o cadastro

#### A1.5. O sistema valida os dados e cria a conta do estudante

#### A1.6. O sistema exibe mensagem de confirmação e redireciona para a tela de login

#### A1.7. O fluxo retorna ao P2

### A2. Estudante acessa via E-mail e Senha

#### A2.1. No P3, o estudante seleciona a opção "Acesso por E-mail/Senha"

#### A2.2. O sistema exibe o formulário de login com campos de e-mail e senha

#### A2.3. O estudante preenche o e-mail e a senha e confirma o acesso

#### A2.4. O sistema valida as credenciais informadas

#### A2.5. O fluxo retorna ao P7

---

## 8. Fluxos de Exceção

### E1. Credenciais inválidas (Fluxo de E-mail/Senha)

#### E1.1. No A2.4, o sistema identifica que o e-mail ou a senha estão incorretos

#### E1.2. O sistema exibe mensagem de erro: "E-mail ou senha inválidos"

#### E1.3. O fluxo retorna ao A2.2

### E2. E-mail já cadastrado

#### E2.1. No A1.5, o sistema identifica que o e-mail informado já está em uso

#### E2.2. O sistema exibe mensagem de erro: "E-mail já cadastrado. Utilize outro e-mail ou recupere sua senha"

#### E2.3. O fluxo retorna ao A1.2

### E3. Campos obrigatórios não preenchidos

#### E3.1. O estudante tenta confirmar o formulário de cadastro ou login sem preencher os campos

#### E3.2. O sistema destaca os campos em branco e exibe mensagem de validação

#### E3.3. O fluxo retorna ao passo correspondente

### E4. Domínio de e-mail inválido (Google OAuth)

#### E4.1. No P6, o sistema identifica que o e-mail selecionado não pertence à instituição

#### E4.2. O sistema bloqueia o login e exibe alerta: "Acesso restrito a e-mails institucionais."

#### E4.3. O fluxo retorna ao P2

---

## 9. Pós-condições

- O estudante está autenticado no sistema e tem acesso às funcionalidades disponíveis para seu perfil.
- Uma sessão ativa é criada para o estudante.

---

## 10. Requisitos Não Funcionais

- O processo de autenticação deve ser concluído em até 3 segundos.
- As senhas (quando usadas no fluxo alternativo) devem ser armazenadas com criptografia (ex.: bcrypt).
- O sistema deve suportar autenticação simultânea de múltiplos usuários.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Alta — acionado a cada acesso ao sistema por parte dos estudantes.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar implementação de recuperação de senha via e-mail para o fluxo A2.
- Considerar integração com login via Sistema Acadêmico para aproveitamento de credenciais.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- Especificação do Sistema Acadêmico (sistema externo)
- **RN01** — Restrição de Domínio Institucional
- **RNF05** — Delegação de autenticação via OAuth 2.0 (sem senhas locais)

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
