# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição           | Autor      |
| ---------- | ------- | --------------------- | ---------- |
| 28/05/2026 | 1.0     | Criação do artefato | Kayo Gomes |

---

## 1. Nome do Caso de Uso

Gerenciar Cursos

---

## 2. Objetivo

Permitir que a coordenação cadastre, edite, ative e desative cursos no Sistema ENADE, associando-os aos usuários e às questões do banco de dados por área de conhecimento.

---

## 3. Tipo de Caso de Uso

Concreto

---

## 4. Atores

### 4.1 Primário

**Coordenação** — ator que administra os cursos cadastrados no sistema.

### 4.2 Secundário

Não se aplica.

---

## 5. Precondições

- A coordenação deve estar autenticada no Sistema ENADE com perfil de administrador.

---

## 6. Fluxo Principal

### P1. A coordenação acessa o painel de administração e seleciona "Gerenciar Cursos"

### P2. O sistema exibe a listagem de cursos cadastrados com opções de busca e filtro

### P3. A coordenação localiza o curso desejado ou opta por criar um novo

### P4. A coordenação seleciona a ação desejada: cadastrar, editar, ativar ou desativar

### P5. O sistema exibe o formulário ou a confirmação correspondente à ação selecionada

### P6. A coordenação preenche ou confirma as informações solicitadas

### P7. O sistema valida os dados e executa a operação

### P8. O sistema exibe mensagem de confirmação do resultado da operação

---

## 7. Fluxos Alternativos

### A1. Coordenação cadastra novo curso

#### A1.1. No P4, a coordenação seleciona "Cadastrar novo curso"

#### A1.2. O sistema exibe o formulário com campos: nome do curso, código MEC, área de conhecimento, instituição e status

#### A1.3. A coordenação preenche os dados e confirma

#### A1.4. O sistema valida e registra o novo curso

#### A1.5. O fluxo retorna ao P8

### A2. Coordenação edita dados de um curso

#### A2.1. No P4, a coordenação seleciona "Editar" no registro do curso

#### A2.2. O sistema exibe o formulário com os dados atuais do curso

#### A2.3. A coordenação altera os campos necessários e confirma

#### A2.4. O sistema atualiza o cadastro do curso

#### A2.5. O fluxo retorna ao P8

### A3. Coordenação vincula professores e estudantes ao curso

#### A3.1. No P4, a coordenação seleciona "Gerenciar membros" no registro do curso

#### A3.2. O sistema exibe a lista de usuários disponíveis para vínculo

#### A3.3. A coordenação seleciona os usuários e confirma o vínculo

#### A3.4. O sistema associa os usuários selecionados ao curso

---

## 8. Fluxos de Exceção

### E1. Nome do curso já cadastrado

#### E1.1. No P7 (fluxo A1), o sistema identifica que já existe um curso com o mesmo nome e instituição

#### E1.2. O sistema exibe mensagem: "Já existe um curso com este nome para esta instituição"

#### E1.3. O fluxo retorna ao A1.2

### E2. Tentativa de desativação de curso com usuários ativos vinculados

#### E2.1. No P4, a coordenação tenta desativar um curso que possui estudantes ou professores ativos

#### E2.2. O sistema exibe alerta informando a existência de vínculos ativos

#### E2.3. A coordenação decide entre prosseguir ou cancelar a desativação

### E3. Campos obrigatórios não preenchidos

#### E3.1. No P7, o sistema identifica campos obrigatórios em branco

#### E3.2. O sistema destaca os campos e exibe mensagem de validação

#### E3.3. O fluxo retorna ao passo de preenchimento correspondente

---

## 9. Pós-condições

- O curso é criado, atualizado, ativado ou desativado conforme a ação executada.
- As questões do banco são associadas automaticamente ao curso com base na área de conhecimento cadastrada.

---

## 10. Requisitos Não Funcionais

- As operações de gestão de cursos devem ser concluídas em até 2 segundos.
- A associação entre cursos e questões deve ser atualizada automaticamente após alteração da área de conhecimento.

---

## 11. Ponto de Extensão

Não se aplica.

---

## 12. Frequência de Utilização

Baixa — realizado principalmente no início de semestres letivos ou quando há criação ou encerramento de cursos.

---

## 13. Interface Visual

Não se aplica.

---

## 14. Observações

- Avaliar integração com o Sistema Acadêmico para importação automática de cursos.
- Considerar a criação de turmas dentro de cada curso para segmentação de estudantes.

---

## 15. Referências

- Diagrama de Caso de Uso — Sistema ENADE
- CDU-08: Gerenciar Usuários
- CDU-10: Gerenciar Competências das Questões

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
