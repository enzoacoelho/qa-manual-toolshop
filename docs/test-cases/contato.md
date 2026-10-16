# Casos de Teste - Módulo de Contato

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Formulário de Contato (`/contact`)  

---

### QA-CON-01 — Enviar mensagem de contato com sucesso
* **ID:** QA-CON-01
* **Prioridade:** Normal
* **Objetivo:** Validar o envio com sucesso do formulário de contato com dados válidos.
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Preencher todos os campos obrigatórios. | Nome, Sobrenome, E-mail, Assunto e Mensagem válidos | Campos preenchidos corretamente. |
| **2** | Clicar no botão **Send**. | Botão: `Send` | Mensagem enviada com sucesso e toast/alerta de confirmação exibido na tela (ex: *"Thanks for your message..."*). |

---

### QA-CON-02 — Bloqueio de envio com campos obrigatórios vazios
* **ID:** QA-CON-02
* **Prioridade:** Normal
* **Objetivo:** Validar o bloqueio de envio ao manter os campos obrigatórios do formulário limpos.
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Deixar os campos Assunto e Mensagem em branco. | Assunto: `[Selecione]`<br>Mensagem: `[Vazio]` | Campos obrigatórios não preenchidos. |
| **2** | Clicar no botão **Send**. | Botão: `Send` | O formulário não é enviado. Envio bloqueado e mensagens de erro de campos obrigatórios exibidas na tela. |

---

### QA-CON-03 — Rejeição de anexo em formato inválido
* **ID:** QA-CON-03
* **Prioridade:** Normal
* **Objetivo:** Validar a restrição de extensões de arquivos no anexo do formulário de contato.
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Tentar anexar um arquivo em formato inválido. | Anexo: `documento.pdf` ou `imagem.jpg` | O sistema exibe mensagem de erro (ex: *"File format not supported"*) e não aceita o anexo. |

---

### QA-CON-04 — Rejeição de anexo válido mas acima do limite de tamanho
* **ID:** QA-CON-04
* **Prioridade:** Normal
* **Objetivo:** Validar o bloqueio de envio ao anexar arquivo `.txt` que ultrapasse o limite máximo permitido (regra da aplicação: limite de 0KB / arquivo com conteúdo).
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Anexar um arquivo `.txt` contendo texto. | Anexo: `arquivo_com_texto.txt` (> 0 KB, ex: 1 KB) | O sistema indica que o tamanho do arquivo excede o limite permitido (0 KB) e impede o envio. |


### QA-CON-05 — Bloqueio de envio com mensagem abaixo do limite mínimo de caracteres
- **ID:** QA-CON-05
- **Prioridade:** Normal
- **Objetivo:** Validar o bloqueio de envio quando o campo de mensagem contém menos caracteres do que o mínimo exigido pela regra de validação.
- **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Preencher o formulário informando uma mensagem com quantidade de caracteres abaixo do mínimo. | Mensagem: Texto curto (< limite mínimo) | Campo preenchido com tamanho insuficiente. |
| **2** | Clicar no botão **Send**. | Botão: `Send` | O envio é bloqueado e a aplicação exibe a mensagem de validação correspondente ao tamanho mínimo. |

---

### QA-CON-06 — Bloqueio de envio com mensagem acima do limite máximo de caracteres
- **ID:** QA-CON-06
- **Prioridade:** Normal
- **Objetivo:** Validar o bloqueio de envio quando o campo de mensagem excede o limite máximo de caracteres permitido pela regra de validação.
- **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Preencher o formulário informando uma mensagem com quantidade de caracteres acima do limite máximo. | Mensagem: Texto longo (> limite máximo) | Campo preenchido excedendo o tamanho permitido. |
| **2** | Clicar no botão **Send**. | Botão: `Send` | O envio é bloqueado e a aplicação exibe a mensagem de validação correspondente ao tamanho máximo. |
