# Casos de Teste - Módulo de Login

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Autenticação e Sessão (`/auth/login`)  

---

### TC01 — Login com sucesso
* **ID:** QA-T6
* **Prioridade:** Alta
* **Objetivo:** Autenticar um usuário cadastrado com credenciais válidas e redirecionar para a área logada.
* **Pré-condições:**
  * Existe conta válida previamente cadastrada (`customer@practicesoftwaretesting.com`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Preencher os campos de credenciais. | **E-mail:** `customer@practicesoftwaretesting.com`<br>**Senha:** `welcome01` | Campos preenchidos com os dados informados. |
| **3** | Clicar no botão **Login**. | Botão: `Login` | Login concluído com sucesso e redirecionamento para a tela da conta (`/account`). |

---

### TC02 — Login com campos vazios
* **ID:** QA-T9
* **Prioridade:** Média
* **Objetivo:** Submeter o formulário de login com e-mail e senha em branco.
* **Pré-condições:**
  * Página de login acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Deixar os campos em branco e submeter. | *Nenhum* | Envio bloqueado sem realização de redirecionamento. Mensagens `"Email is required"` e `"Password is required"` exibidas abaixo de cada respectivo campo. |

---

### TC03 — Login com campos preenchidos apenas com espaços
* **ID:** QA-T43
* **Prioridade:** Média
* **Objetivo:** Inserir apenas espaços em branco nos campos de login e tentar submeter.
* **Pré-condições:**
  * Nenhuma.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Preencher os campos apenas com espaços. | **E-mail:** `   `<br>**Senha:** `   ` | Campos preenchidos com espaços em branco. |
| **3** | Clicar no botão **Login**. | Botão: `Login` | O sistema trata os espaços como campo vazio, bloqueia a ação, não redireciona e exibe a mensagem `"invalid email or password"` na tela. |

---

### TC04 — Login com espaços antes/depois de credenciais válidas
* **ID:** QA-T44
* **Prioridade:** Média
* **Objetivo:** Inserir credenciais válidas contendo espaços no início ou fim e validar a regra de tratamento (trim).
* **Pré-condições:**
  * Existe conta válida previamente cadastrada.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Preencher credenciais com espaços extras. | **E-mail:** ` customer@practicesoftwaretesting.com `<br>**Senha:** ` welcome01 ` | Campos preenchidos com espaços nas extremidades. |
| **3** | Clicar no botão **Login**. | Botão: `Login` | O sistema deve aplicar o *trim* (aparar os espaços) e efetuar o login normalmente. Caso rejeite, documentar como bug ou regra de negócio. |

---

### TC05 — Login com senha incorreta
* **ID:** QA-T7
* **Prioridade:** Média
* **Objetivo:** Tentar autenticação com e-mail válido e senha errada, garantindo a exibição da mensagem de erro genérica por segurança.
* **Pré-condições:**
  * Existe conta válida previamente cadastrada.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Informar e-mail válido e senha incorreta. | **E-mail:** `customer@practicesoftwaretesting.com`<br>**Senha:** `errada123` | Campos preenchidos. |
| **3** | Clicar no botão **Login**. | Botão: `Login` | Acesso negado, sem redirecionamento. Mensagem `"invalid email or password"` visível na tela. |

---

### TC06 — Login com e-mail não cadastrado
* **ID:** QA-T8
* **Prioridade:** Média
* **Objetivo:** Tentar login utilizando um e-mail que não existe na base de dados.
* **Pré-condições:**
  * Página de login acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Informar e-mail inexistente e senha válida. | **E-mail:** `emailnaoexistente@gmail.com`<br>**Senha:** `welcome01` | Campos preenchidos. |
| **3** | Clicar no botão **Login**. | Botão: `Login` | Login não realizado, usuário permanece na tela. Mensagem `"Invalid email or password"` visível. |

---

### TC07 — Login com e-mail em formato inválido
* **ID:** QA-T45
* **Prioridade:** Média
* **Objetivo:** Inserir e-mail fora da sintaxe padrão e tentar submeter a autenticação.
* **Pré-condições:**
  * Página de login acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Informar e-mail sem sintaxe correta e senha. | **E-mail:** `customerpracticesoftwaretesting.com`<br>**Senha:** `welcome01` | Campos preenchidos. |
| **3** | Clicar no botão **Login**. | Botão: `Login` | Validação de formato impede o envio ou servidor recusa. Usuário permanece na tela e mensagem `"Invalid email or password"` é exibida. |

---

### TC08 — Acessar link "Cadastre-se" a partir do login
* **ID:** QA-T46
* **Prioridade:** Baixa
* **Objetivo:** Validar o direcionamento do link de registro de conta a partir da tela de login.
* **Pré-condições:**
  * Página de login acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Clicar no link de registro. | Link: `"Register your account"` | Redirecionamento correto para a tela de cadastro (`/auth/register`). |

---

### TC09 — Acessar link "Esqueceu a senha" a partir do login
* **ID:** QA-T47
* **Prioridade:** Baixa
* **Objetivo:** Validar o direcionamento do link de recuperação de senha.
* **Pré-condições:**
  * Página de login acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login. | URL: `https://practicesoftwaretesting.com/auth/login` | Página de login carregada corretamente. |
| **2** | Clicar no link de recuperação. | Link: `"Forgot your Password?"` | Redirecionamento correto para a tela de recuperação de senha (`/auth/forgot-password`). |

---

### TC10 — Ícone de mostrar/esconder senha
* **ID:** QA-T48
* **Prioridade:** Baixa
* **Objetivo:** Alternar a visibilidade da senha entre caracteres mascarados e texto plano.
* **Pré-condições:**
  * Página de login acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de login e digitar uma senha. | **Senha:** `welcome01` | Texto aparece oculto (bolinhas/asteriscos). |
| **2** | Clicar no ícone de olho (primeira vez). | Ícone: Olho | A senha é exibida em texto plano. |
| **3** | Clicar novamente no ícone de olho. | Ícone: Olho | A senha volta a ser mascarada. |

---

### TC11 — Logout
* **ID:** QA-T181
* **Prioridade:** Alta
* **Objetivo:** Encerrar a sessão do usuário e garantir o bloqueio de navegação para áreas privadas.
* **Pré-condições:**
  * Usuário deve estar autenticado no sistema.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Estando logado, acionar a opção de saída. | Opção: `"Sign out"` no menu da conta | Sessão encerrada e redirecionamento para a tela de login. |
| **2** | Tentar acessar a URL protegida diretamente. | URL: `https://practicesoftwaretesting.com/account` | Acesso bloqueado e sistema força o redirecionamento para a tela de login. |
