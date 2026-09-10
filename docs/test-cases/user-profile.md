# Casos de Teste - Módulo de Perfil de Usuário

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Perfil de Usuário (`/account/profile`)  

---

### TC01 — Alterar dados básicos do perfil com sucesso
* **ID:** QA-T106
* **Prioridade:** Normal
* **Objetivo:** Confirmar que o usuário autenticado consegue atualizar suas informações pessoais básicas (ex: Nome, Sobrenome, Telefone, Endereço).
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Alterar os campos de dados básicos do formulário de perfil. | First Name: `John`<br>Last Name: `Doe Updated`<br>Phone: `1234567890`<br>Address: `New Street 123` | Os novos valores são digitados nos respectivos campos. |
| **2** | Clicar no botão de salvar alterações dos dados do perfil. | Botão: `Save / Update Profile` | O perfil é atualizado e o sistema exibe uma mensagem de confirmação/sucesso na tela (ex: *"Profile updated successfully"*). |

---

### TC02 — Alterar senha do usuário com sucesso
* **ID:** QA-T107
* **Prioridade:** Alta
* **Objetivo:** Confirmar que o usuário consegue alterar sua senha informando a senha atual válida e uma nova senha forte que atenda aos requisitos de segurança.
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Preencher os campos do formulário de alteração de senha. | Current Password: `{senha_atual}`<br>New Password: `StrongPass123!`<br>Confirm Password: `StrongPass123!` | Os campos de senha são preenchidos corretamente. |
| **2** | Clicar no botão de salvar/alterar senha. | Botão: `Change Password / Update` | A senha é alterada com sucesso, sendo exibida uma mensagem de confirmação de sucesso. |

---

### TC03 — Tentativa de salvar dados básicos do perfil em branco
* **ID:** QA-T108
* **Prioridade:** Normal
* **Objetivo:** Validar que o sistema impede a atualização do perfil caso campos obrigatórios (ex: Nome, Sobrenome) sejam apagados e deixados em branco.
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Limpar todo o conteúdo dos campos obrigatórios do perfil. | First Name: `[Vazio]`<br>Last Name: `[Vazio]` | Campos obrigatórios esvaziados. |
| **2** | Clicar no botão de salvar alterações dos dados do perfil. | Botão: `Save / Update Profile` | A alteração é bloqueada e são exibidas mensagens de erro indicando a obrigatoriedade dos campos abaixo dos inputs correspondentes. |

---

### TC04 — Tentativa de alterar a senha para uma senha fraca
* **ID:** QA-T109
* **Prioridade:** Normal
* **Objetivo:** Validar o bloqueio ao tentar cadastrar uma nova senha que não atenda aos critérios mínimos de segurança exigidos pela aplicação (ex: comprimento curto ou ausência de caracteres especiais/números).
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Preencher a senha atual e informar uma nova senha fraca. | Current Password: `{senha_atual}`<br>New Password: `123`<br>Confirm Password: `123` | Campos preenchidos com senha fraca. |
| **2** | Clicar no botão de salvar/alterar senha. | Botão: `Change Password / Update` | O sistema recusa a nova senha e a alteração é bloqueada, exibindo uma mensagem de validação/erro informando os critérios de segurança não atendidos. |

---

### TC05 — Tentativa de alterar a senha para a mesma senha atual
* **ID:** QA-T110
* **Prioridade:** Normal
* **Objetivo:** Validar se o sistema impede que o usuário defina uma nova senha exatamente igual à senha atual já em uso.
* **Pré-condições:**
  * Usuário autenticado e na página de Perfil (`https://practicesoftwaretesting.com/account/profile`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Informar nos campos de "Nova Senha" exatamente o mesmo valor da "Senha Atual". | Current Password: `{senha_atual}`<br>New Password: `{senha_atual}`<br>Confirm Password: `{senha_atual}` | Campos preenchidos com a mesma senha. |
| **2** | Clicar no botão de salvar/alterar senha. | Botão: `Change Password / Update` | O sistema identifica a duplicidade, impede a alteração e exibe uma mensagem de erro informando que a nova senha deve ser diferente da senha atual. |
