# Casos de Teste - Módulo de Cadastro (Registro)

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Cadastro de Usuário (`/auth/register`)  

---

### TC01 — Cadastro válido com sucesso
* **ID:** QA-T1
* **Prioridade:** Alta
* **Objetivo:** Preencher todos os campos obrigatórios com dados válidos, validar o autocompletar do endereço e confirmar a criação da conta.
* **Pré-condições:**
  * E-mail utilizado não deve existir na base de dados.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Preencher dados pessoais e selecionar o país. | **First Name**, **Last Name**, **DOB** (`YYYY-MM-DD`), **Country**: `United States` | Campos preenchidos corretamente. |
| **3** | Inserir CEP e número da residência. | **Postal Code** e **House Number** válidos | Dados informados nos inputs. |
| **4** | Verificar autocompletar do endereço. | *Nenhum* | Campos **Street**, **City** e **State** autocompletados pelo sistema. |
| **5** | Preencher dados de contato e credenciais. | **Phone**, **E-mail novo**, **Password**: `Abc123!@` | Campos preenchidos. |
| **6** | Clicar no botão **Register**. | Botão: `Register` | Registro concluído com sucesso e redirecionamento para o login (`/auth/login`). |
| **7** | Realizar login com as novas credenciais. | E-mail e senha recém-cadastrados | Login efetuado com sucesso e redirecionamento para a tela inicial. |

---

### TC02 — Cadastro com e-mail já existente
* **ID:** QA-T2
* **Prioridade:** Média
* **Objetivo:** Tentar criar uma conta utilizando um e-mail previamente cadastrado no banco de dados.
* **Pré-condições:**
  * O e-mail informado já deve existir no banco de dados (ex: `customer@practicesoftwaretesting.com`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Preencher formulário com e-mail existente. | **E-mail:** `customer@practicesoftwaretesting.com` + demais dados válidos | Formulário preenchido. |
| **3** | Clicar no botão **Register**. | Botão: `Register` | O sistema bloqueia a criação da conta, sem redirecionamento, e exibe mensagem indicando que o e-mail já está em uso ou é inválido. |

---

### TC03 — Validação de campos obrigatórios vazios ou contendo apenas espaços
* **ID:** QA-T3
* **Prioridade:** Média
* **Objetivo:** Tentar submeter o formulário sem preencher dados ou informando apenas espaços em branco nos campos obrigatórios.
* **Pré-condições:**
  * Tela de cadastro acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Tentar submeter sem preencher nada. | *Nenhum* | Envio bloqueado imediatamente com exibição de alertas para todos os campos obrigatórios. |
| **3** | Inserir apenas espaços no campo **First Name**. | **First Name:** `   ` + demais campos válidos | Campo preenchido com espaços. |
| **4** | Clicar no botão **Register**. | Botão: `Register` | O sistema trata os espaços em branco como valor vazio e mantém o bloqueio do envio. |

---

### TC04 — Validação de formato de campos (E-mail, Data, Telefone e CEP)
* **ID:** QA-T4
* **Prioridade:** Média
* **Objetivo:** Inserir dados sintaticamente inválidos nos campos estruturados e validar o bloqueio do envio.
* **Pré-condições:**
  * Tela de cadastro acessível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Preencher campos com formatos inválidos. | **Email:** `emailinvalido`<br>**DOB:** `2099-01-01`<br>**Phone:** `abc123`<br>**Postcode:** `XYZ-000` | Campos preenchidos com dados incorretos. |
| **3** | Clicar no botão **Register**. | Botão: `Register` | Exibição de alertas de validação nos campos correspondentes. O formulário recusa a submissão até que todas as sintaxes sejam corrigidas. |

---

### TC05 — Validação de bloqueio de cadastro ao utilizar senha com nível de força Weak
* **ID:** QA-T5
* **Prioridade:** Média
* **Objetivo:** Validar se o indicador de força atualiza para *Weak* e bloqueia a submissão ao informar uma combinação fraca.
* **Pré-condições:**
  * Estar na tela de registro com dados pessoais e e-mail válidos preenchidos.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Preencher o campo de senha fraca. | **Password:** `123456` | Campo preenchido apenas com números. |
| **3** | Clicar no botão **Register**. | Botão: `Register` | A barra de força indica **Weak**. Requisitos pendentes (maiúsculas, especiais, tamanho). Envio bloqueado com alerta indicando regras não atendidas. |

---

### TC06 — Validação de bloqueio de cadastro ao utilizar senha com nível de força Moderate
* **ID:** QA-T186
* **Prioridade:** Média
* **Objetivo:** Validar se o indicador de força atualiza para *Moderate* e se o envio permanece bloqueado caso faltem símbolos ou números.
* **Pré-condições:**
  * Estar na tela de registro com dados pessoais e e-mail válidos preenchidos.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Preencher o campo de senha moderada. | **Password:** `Abcdefgh` | Senha com 8 caracteres e maiúscula, sem números/especiais. |
| **3** | Clicar no botão **Register**. | Botão: `Register` | Barra atualiza para **Moderate**. Requisitos de números e símbolos pendentes. Envio bloqueado com alertas informativos. |

---

### TC07 — Validação de limite mínimo de caracteres no campo Password
* **ID:** QA-T187
* **Prioridade:** Média
* **Objetivo:** Validar a regra de negócio do limite mínimo de 8 caracteres na senha, garantindo o bloqueio ao digitar 7 caracteres.
* **Pré-condições:**
  * Estar na tela de registro com dados pessoais e e-mail válidos preenchidos.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela de cadastro. | URL: `https://practicesoftwaretesting.com/auth/register` | Página de cadastro carregada corretamente. |
| **2** | Preencher o campo com senha abaixo do limite. | **Password:** `U!Doi@1` | Senha com 7 caracteres. |
| **3** | Clicar no botão **Register**. | Botão: `Register` | Requisito de mínimo de 8 caracteres permanece pendente. Envio bloqueado com alerta correspondente exibido. |
