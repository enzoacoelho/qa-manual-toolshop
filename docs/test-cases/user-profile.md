# Casos de Teste - Módulo de Perfil de Usuário

**Aplicação:** Practice Software Testing  
**Módulo:** Perfil de Usuário (`/account/profile`)  

---

### TC01 — Alterar dados básicos do perfil com sucesso
* **ID:** QA-T106
* **Prioridade:** Normal
* **Objetivo:** Confirmar que o usuário autenticado consegue atualizar suas informações pessoais básicas (ex: Nome, Sobrenome, Telefone, Endereço).
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).
* **Passos:**
  1. Alterar os campos de dados básicos do formulário de perfil (First Name: `John` / Last Name: `Doe Updated` / Phone: `1234567890` / Address: `New Street 123`).
  2. Clicar no botão de salvar alterações dos dados do perfil (**Save / Update Profile**).
* **Resultado Esperado:**
  * Os novos valores são digitados nos respectivos campos.
  * O perfil é atualizado e o sistema exibe uma mensagem de confirmação/sucesso na tela (ex: *"Profile updated successfully"*).

---

### TC02 — Alterar senha do usuário com sucesso
* **ID:** QA-T107
* **Prioridade:** Alta
* **Objetivo:** Confirmar que o usuário consegue alterar sua senha informando a senha atual válida e uma nova senha forte que atenda aos requisitos de segurança.
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).
* **Passos:**
  1. Preencher os campos do formulário de alteração de senha (Current Password: `{senha_atual}` / New Password: `StrongPass123!` / Confirm Password: `StrongPass123!`).
  2. Clicar no botão de salvar/alterar senha (**Change Password / Update**).
* **Resultado Esperado:**
  * Os campos de senha são preenchidos corretamente.
  * A senha é alterada com sucesso, sendo exibida uma mensagem de confirmação de sucesso.

---

### TC03 — Tentativa de salvar dados básicos do perfil em branco
* **ID:** QA-T108
* **Prioridade:** Normal
* **Objetivo:** Validar que o sistema impede a atualização do perfil caso campos obrigatórios (ex: Nome, Sobrenome) sejam apagados e deixados em branco.
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).
* **Passos:**
  1. Limpar todo o conteúdo dos campos obrigatórios do perfil (First Name: `[Vazio]` / Last Name: `[Vazio]`).
  2. Clicar no botão de salvar alterações dos dados do perfil (**Save / Update Profile**).
* **Resultado Esperado:**
  * A alteração é bloqueada e são exibidas mensagens de erro indicando a obrigatoriedade dos campos abaixo dos inputs correspondentes.

---

### TC04 — Tentativa de alterar a senha para uma senha fraca
* **ID:** QA-T109
* **Prioridade:** Normal
* **Objetivo:** Validar o bloqueio ao tentar cadastrar uma nova senha que não atenda aos critérios mínimos de segurança exigidos pela aplicação (ex: comprimento curto ou ausência de caracteres especiais/números).
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).
* **Passos:**
  1. Preencher a senha atual e informar uma nova senha fraca (Current Password: `{senha_atual}` / New Password: `123` / Confirm Password: `123`).
  2. Clicar no botão de salvar/alterar senha (**Change Password / Update**).
* **Resultado Esperado:**
  * O sistema recusa a nova senha e a alteração é bloqueada, exibindo uma mensagem de validação/erro informando os critérios de segurança não atendidos.

---

### TC05 — Tentativa de alterar a senha para a mesma senha atual
* **ID:** QA-T110
* **Prioridade:** Normal
* **Objetivo:** Validar se o sistema impede que o usuário defina uma nova senha exatamente igual à senha atual já em uso.
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).
* **Passos:**
  1. Informar nos campos de "Nova Senha" exatamente o mesmo valor da "Senha Atual" (Current Password: `{senha_atual}` / New Password: `{senha_atual}` / Confirm Password: `{senha_atual}`).
  2. Clicar no botão de salvar/alterar senha (**Change Password / Update**).
* **Resultado Esperado:**
  * O sistema identifica a duplicidade, impede a alteração e exibe uma mensagem de erro informando que a nova senha deve ser diferente da senha atual.
