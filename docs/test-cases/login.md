# Casos de Teste - Módulo de Login

**Aplicação:** Practice Software Testing  - Tool Shop
**Módulo:** Autenticação e Sessão (`/auth/login`)  

---

### TC01 — Login com sucesso
* **ID:** QA-T6
* **Prioridade:** Alta
* **Objetivo:** Autenticar um usuário cadastrado com credenciais válidas e redirecionar para a área logada.
* **Pré-condições:**
  * Existe conta válida previamente cadastrada (`customer@practicesoftwaretesting.com`).
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Preencher os campos com e-mail e senha válidos:
     * **E-mail:** `customer@practicesoftwaretesting.com`
     * **Senha:** `welcome01`
  3. Clicar no botão **Login**.
* **Resultado Esperado:**
  * Login concluído com sucesso.
  * Redirecionamento para a tela da conta (`https://practicesoftwaretesting.com/account`).

---

### TC05 — Login com senha incorreta
* **ID:** QA-T7
* **Prioridade:** Média
* **Objetivo:** Tentar autenticação com e-mail válido e senha errada, garantindo a exibição da mensagem de erro genérica por segurança.
* **Pré-condições:**
  * Existe conta válida previamente cadastrada.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Informar e-mail válido (`customer@practicesoftwaretesting.com`) e senha incorreta (`errada123`).
  3. Clicar no botão **Login**.
* **Resultado Esperado:**
  * O acesso é negado e o usuário não é redirecionado para outra tela.
  * Mensagem `"invalid email or password"` visível na tela de login.

---

### TC06 — Login com e-mail não cadastrado
* **ID:** QA-T8
* **Prioridade:** Média
* **Objetivo:** Tentar login utilizando um e-mail que não existe na base de dados.
* **Pré-condições:**
  * Página de login acessível.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Informar e-mail inexistente (`emailnaoexistente@gmail.com`).
  3. Preencher o campo de senha (`welcome01`).
  4. Clicar no botão **Login**.
* **Resultado Esperado:**
  * O login não é realizado.
  * O usuário permanece na tela de login.
  * Mensagem `"Invalid email or password"` visível na tela.

---

### TC02 — Login com campos vazios
* **ID:** QA-T9
* **Prioridade:** Média
* **Objetivo:** Submeter o formulário de login com e-mail e senha em branco.
* **Pré-condições:**
  * Página de login acessível.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Não preencher os campos de e-mail e senha.
  3. Clicar no botão **Login**.
* **Resultado Esperado:**
  * Envio bloqueado sem realização de redirecionamento.
  * Mensagens `"Email is required"` e `"Password is required"` exibidas abaixo de cada respectivo campo.

---

### TC03 — Login com campos preenchidos apenas com espaços
* **ID:** QA-T43
* **Prioridade:** Média
* **Objetivo:** Inserir apenas espaços em branco nos campos de login e tentar submeter.
* **Pré-condições:**
  * Nenhuma.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Preencher e-mail e senha inserindo apenas espaços em branco (` `).
  3. Clicar no botão **Login**.
* **Resultado Esperado:**
  * O sistema trata os espaços como campo vazio e bloqueia a ação.
  * Não redireciona o usuário e exibe a mensagem `"invalid email or password"` na tela de login.

---

### TC04 — Login com espaços antes/depois de credenciais válidas
* **ID:** QA-T44
* **Prioridade:** Média
* **Objetivo:** Inserir credenciais válidas contendo espaços no início ou fim e validar a regra de tratamento (trim).
* **Pré-condições:**
  * Existe conta válida previamente cadastrada.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Preencher e-mail e senha válidos contendo espaços extras no início/fim (` customer@practicesoftwaretesting.com ` / ` welcome01 `).
  3. Clicar no botão **Login**.
* **Resultado Esperado:**
  * A validar: O sistema deve aplicar o trim (aparar os espaços) e efetuar o login normalmente — caso rejeite, o comportamento deve ser documentado como bug ou regra de negócio.

---

### TC07 — Login com e-mail em formato inválido
* **ID:** QA-T45
* **Prioridade:** Média
* **Objetivo:** Inserir e-mail fora da sintaxe padrão e tentar submeter a autenticação.
* **Pré-condições:**
  * Página de login acessível.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Informar e-mail sem `@` ou domínio (`customerpracticesoftwaretesting.com`).
  3. Preencher o campo de senha (`welcome01`).
  4. Clicar no botão **Login**.
* **Resultado Esperado:**
  * A validação de formato impede o envio ou o servidor recusa a requisição.
  * Usuário permanece na tela de login e a mensagem `"Invalid email or password"` é exibida.

---

### TC08 — Acessar link "Cadastre-se" a partir do login
* **ID:** QA-T46
* **Prioridade:** Baixa
* **Objetivo:** Validar o direcionamento do link de registro de conta a partir da tela de login.
* **Pré-condições:**
  * Página de login acessível.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Na tela de login, clicar no link `"Register your account"`.
* **Resultado Esperado:**
  * Redirecionamento correto para a tela de cadastro com a URL `https://practicesoftwaretesting.com/auth/register`.

---

### TC09 — Acessar link "Esqueceu a senha" a partir do login
* **ID:** QA-T47
* **Prioridade:** Baixa
* **Objetivo:** Validar o direcionamento do link de recuperação de senha.
* **Pré-condições:**
  * Página de login acessível.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Na tela de login, clicar em `"Forgot your Password?"`.
* **Resultado Esperado:**
  * Redirecionamento correto para a tela de recuperação de senha com a URL `https://practicesoftwaretesting.com/auth/forgot-password`.

---

### TC10 — Ícone de mostrar/esconder senha
* **ID:** QA-T48
* **Prioridade:** Baixa
* **Objetivo:** Alternar a visibilidade da senha entre caracteres mascarados e texto plano.
* **Pré-condições:**
  * Página de login acessível.
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`).
  2. Digitar qualquer senha no campo correspondente.
  3. Confirmar que o texto aparece oculto (bolinhas/asteriscos).
  4. Clicar no ícone de olho.
  5. Clicar novamente no ícone de olho.
* **Resultado Esperado:**
  * Ao clicar no olho pela primeira vez, a senha é exibida em texto plano.
  * Ao clicar novamente, a senha volta a ser mascarada.

---

### TC11 — Logout
* **ID:** QA-T181
* **Prioridade:** Alta
* **Objetivo:** Encerrar a sessão do usuário e garantir o bloqueio de navegação para áreas privadas.
* **Pré-condições:**
  * Usuário deve estar autenticado no sistema.
* **Passos:**
  1. Estando logado, clicar na opção `"Sign out"` no menu da conta.
  2. Tentar acessar a URL da conta diretamente via navegador (`https://practicesoftwaretesting.com/account`).
* **Resultado Esperado:**
  * A sessão é encerrada e o usuário é redirecionado para a tela de login.
  * Ao tentar acessar a URL privada diretamente, o acesso é bloqueado e o sistema força o redirecionamento para a tela de login.
