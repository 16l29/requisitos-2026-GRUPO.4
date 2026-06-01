# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |

---

## 1. Nome do Caso de Uso

Gerenciar Usuários

---

## 2. Objetivo

Permitir que a coordenação cadastre, edite, ative, desative e exclua usuários do Sistema ENADE, controlando os perfis de acesso de estudantes, professores e outros coordenadores.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Coordenação** — ator responsável por administrar os usuários do sistema.

### 4.2 Secundário

Não se aplica.

---

## 5. Precondições

- A coordenação deve estar autenticada no Sistema ENADE com perfil de administrador.

---

## 6. Fluxo Principal

### P1. A coordenação acessa o painel de administração e seleciona "Gerenciar Usuários"

### P2. O sistema exibe a listagem de usuários cadastrados com filtros de busca disponíveis

### P3. A coordenação localiza o usuário desejado por meio de busca ou navegação na lista

### P4. A coordenação seleciona a ação desejada: cadastrar, editar, ativar/desativar ou excluir

### P5. O sistema exibe o formulário ou a confirmação correspondente à ação selecionada

### P6. A coordenação preenche ou confirma as informações solicitadas

### P7. O sistema valida os dados e executa a operação

### P8. O sistema exibe mensagem de confirmação do resultado da operação

---

## 7. Fluxos Alternativos

### A1. Coordenação cadastra novo usuário

#### A1.1. No P4, a coordenação seleciona "Cadastrar novo usuário"

#### A1.2. O sistema exibe o formulário de cadastro com campos: nome, e-mail, perfil (estudante/professor/coordenação), curso e instituição

#### A1.3. A coordenação preenche os dados e confirma

#### A1.4. O sistema valida os dados, cria o usuário e envia as credenciais de acesso por e-mail

#### A1.5. O fluxo retorna ao P8

### A2. Coordenação edita dados de um usuário

#### A2.1. No P4, a coordenação seleciona "Editar" no registro do usuário

#### A2.2. O sistema exibe o formulário com os dados atuais do usuário

#### A2.3. A coordenação altera os campos necessários e confirma

#### A2.4. O sistema atualiza o cadastro do usuário

#### A2.5. O fluxo retorna ao P8

### A3. Coordenação ativa ou desativa um usuário

#### A3.1. No P4, a coordenação seleciona "Ativar" ou "Desativar" no registro do usuário

#### A3.2. O sistema solicita confirmação da ação

#### A3.3. A coordenação confirma

#### A3.4. O sistema altera o status do usuário e impede ou restaura seu acesso ao sistema

#### A3.5. O fluxo retorna ao P8

---

## 8. Fluxos de Exceção

### E1. E-mail já cadastrado para outro usuário

#### E1.1. No P7 (fluxo A1), o sistema identifica que o e-mail informado já está em uso

#### E1.2. O sistema exibe mensagem: "Este e-mail já está cadastrado para outro usuário"

#### E1.3. O fluxo retorna ao A1.2

### E2. Tentativa de exclusão de usuário com vínculos ativos

#### E2.1. No P4, a coordenação seleciona "Excluir" para um usuário que possui participações em fóruns, simulados ou outros registros

#### E2.2. O sistema alerta que o usuário possui dados vinculados e sugere a desativação como alternativa

#### E2.3. A coordenação decide entre prosseguir com a exclusão ou optar pela desativação

### E3. Campos obrigatórios não preenchidos

#### E3.1. No P7, o sistema identifica campos obrigatórios em branco

#### E3.2. O sistema destaca os campos e exibe mensagem de validação

#### E3.3. O fluxo retorna ao passo de preenchimento correspondente

---

## 9. Pós-condições

- O usuário é criado, atualizado, ativado, desativado ou excluído conforme a ação executada.
- O log de auditoria registra a operação realizada, o ator responsável e a data/hora.

---

## 10. Requisitos Não Funcionais

- As operações de gestão de usuários devem ser concluídas em até 2 segundos.
- O envio automático de credenciais deve utilizar e-mail seguro com link de primeiro acesso com validade de 48 horas.
- Somente usuários com perfil de coordenação devem ter acesso a esta funcionalidade.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Baixa a média — acionado principalmente no início de semestres ou quando há movimentação de estudantes e professores.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar importação em lote de usuários via planilha CSV integrada ao Sistema Acadêmico.
- Considerar fluxo de redefinição de senha iniciado pelo próprio usuário.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- CDU-09: Gerenciar Cursos
- CDU-01: Efetuar Cadastro e Login

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
