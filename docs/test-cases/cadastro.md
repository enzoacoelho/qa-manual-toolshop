# Casos de Teste - Módulo de Cadastro (Registro)

**Aplicação:** Practice Software Testing  
**Módulo:** Cadastro de Usuário (`/auth/register`)  

---

### TC01 — Cadastro válido com sucesso
* **ID:** QA-T1
* **Prioridade:** Alta
* **Objetivo:** Preencher todos os campos obrigatórios com dados válidos, validar o autocompletar do endereço e confirmar a criação da conta.
* **Pré-condições:**
  * E-mail utilizado não deve existir na base de dados.
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Preencher dados pessoais e selecionar o país:
     * **First Name**, **Last Name**, **DOB** (`YYYY-MM-DD`), **Country**: `United States`.
  3. Inserir **Postal Code** e **House Number** válidos.
  4. Confirmar se os campos **Street**, **City** e **State** foram autocompletados pelo sistema.
  5. Preencher **Phone**, **E-mail novo** e **Password** (`Abc123!@`).
  6. Clicar no botão **Register**.
  7. Preencher os campos de login com o e-mail e a senha recém-cadastrados.
* **Resultado Esperado:**
  * Endereço autocompletado ao inserir o CEP/Postal Code.
  * Registro concluído com sucesso e redirecionamento para `/auth/register` -> `/auth/login`.
  * Login efetuado com sucesso usando as novas credenciais e redirecionamento para a tela inicial.

---

### TC02 — Cadastro com e-mail já existente
* **ID:** QA-T2
* **Prioridade:** Média
* **Objetivo:** Tentar criar uma conta utilizando um e-mail previamente cadastrado no banco de dados.
* **Pré-condições:**
  * O e-mail informado já deve existir no banco de dados (ex: `customer@practicesoftwaretesting.com`).
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Preencher todos os campos com dados válidos, mas informando um e-mail já cadastrado no sistema.
  3. Clicar no botão **Register**.
* **Resultado Esperado:**
  * O sistema bloqueia a criação da conta e não realiza o redirecionamento.
  * Mensagem indicando que o e-mail já está em uso ou é inválido é exibida em tela.

---

### TC03 — Validação de campos obrigatórios vazios ou contendo apenas espaços
* **ID:** QA-T3
* **Prioridade:** Média
* **Objetivo:** Tentar submeter o formulário sem preencher dados ou informando apenas espaços em branco nos campos obrigatórios.
* **Pré-condições:**
  * Tela de cadastro acessível.
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Clicar diretamente no botão **Register** sem preencher nenhum campo.
  3. Digitar apenas espaços em branco no campo **First Name** e preencher os demais campos com dados válidos.
  4. Clicar no botão **Register**.
* **Resultado Esperado:**
  * No passo 2: Envio bloqueado imediatamente com exibição de alertas para todos os campos obrigatórios.
  * No passo 4: O sistema trata os espaços em branco como valor vazio e mantém o bloqueio do envio.

---

### TC04 — Validação de formato de campos (E-mail, Data, Telefone e CEP)
* **ID:** QA-T4
* **Prioridade:** Média
* **Objetivo:** Inserir dados sintaticamente inválidos nos campos estruturados e validar o bloqueio do envio.
* **Pré-condições:**
  * Tela de cadastro acessível.
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Preencher o campo **Email** com formato inválido (ex: `emailinvalido`).
  3. Preencher o campo **DOB (Data de Nascimento)** no futuro ou inexistente (ex: `2099-01-01`).
  4. Preencher o campo **Phone** com letras (ex: `abc123`) e **Postcode** inválido (ex: `XYZ-000`).
  5. Clicar no botão **Register**.
* **Resultado Esperado:**
  * Exibição de alertas de validação nos campos correspondentes (e-mail incorreto, data inválida e parâmetros incorretos para telefone/postcode).
  * O formulário recusa a submissão até que todas as sintaxes sejam corrigidas.

---

### TC05 — Validação de bloqueio de cadastro ao utilizar senha com nível de força Weak
* **ID:** QA-T5
* **Prioridade:** Média
* **Objetivo:** Validar se o indicador de força atualiza para *Weak* e bloqueia a submissão ao informar uma combinação fraca.
* **Pré-condições:**
  * Estar na tela de registro com dados pessoais e e-mail válidos preenchidos.
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Preencher o campo **Password** digitando uma senha fraca contendo apenas números (ex: `123456`).
  3. Clicar no botão **Register**.
* **Resultado Esperado:**
  * A barra de força da senha indica o nível **Weak**.
  * Os requisitos de letras maiúsculas/minúsculas, caractere especial e mínimo de 8 caracteres permanecem pendentes.
  * O envio é bloqueado pelo sistema e um alerta indica quais regras da senha não foram atendidas.

---

### TC06 — Validação de bloqueio de cadastro ao utilizar senha com nível de força Moderate
* **ID:** QA-T186
* **Prioridade:** Média
* **Objetivo:** Validar se o indicador de força atualiza para *Moderate* e se o envio permanece bloqueado caso faltem símbolos ou números.
* **Pré-condições:**
  * Estar na tela de registro com dados pessoais e e-mail válidos preenchidos.
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Preencher o campo **Password** com pelo menos 8 caracteres e letra maiúscula, mas sem números ou caracteres especiais (ex: `Abcdefgh`).
  3. Clicar no botão **Register**.
* **Resultado Esperado:**
  * A barra de força atualiza para **Moderate**.
  * Os requisitos *"Include at least one number"* e *"Have at least one special symbol"* permanecem marcados como pendentes.
  * O envio é bloqueado pelo sistema com alertas informando sobre os requisitos pendentes.

---

### TC07 — Validação de limite mínimo de caracteres no campo Password
* **ID:** QA-T187
* **Prioridade:** Média
* **Objetivo:** Validar a regra de negócio do limite mínimo de 8 caracteres na senha, garantindo o bloqueio ao digitar 7 caracteres.
* **Pré-condições:**
  * Estar na tela de registro com dados pessoais e e-mail válidos preenchidos.
* **Passos:**
  1. Acessar a tela de cadastro (`https://practicesoftwaretesting.com/auth/register`).
  2. Preencher o campo **Password** inserindo apenas 7 caracteres com símbolos e maiúsculas (ex: `U!Doi@1`).
  3. Clicar no botão **Register**.
* **Resultado Esperado:**
  * O requisito *"Be at least 8 characters long"* permanece pendente, mesmo que a barra exiba *Strong* ou *Very Strong*.
  * O envio é bloqueado e um alerta referente ao mínimo de 8 caracteres na senha é exibido.
