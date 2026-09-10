# Casos de Teste - Módulo de Contato

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Formulário de Contato (`/contact`)  

---

### TC01 — Enviar mensagem de contato com sucesso
* **ID:** QA-T100
* **Prioridade:** Normal
* **Objetivo:** Validar o envio com sucesso do formulário de contato com dados válidos.
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Preencher todos os campos obrigatórios. | Nome, Sobrenome, E-mail, Assunto e Mensagem válidos | Campos preenchidos corretamente. |
| **2** | Clicar no botão **Send**. | Botão: `Send` | Mensagem enviada com sucesso e toast/alerta de confirmação exibido na tela (ex: *"Thanks for your message..."*). |

---

### TC02 — Bloqueio de envio com Assunto e Mensagem vazios
* **ID:** QA-T101
* **Prioridade:** Normal
* **Objetivo:** Validar o bloqueio de envio ao manter os campos obrigatórios do formulário limpos.
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Deixar os campos Assunto e Mensagem em branco. | Assunto: `[Selecione]`<br>Mensagem: `[Vazio]` | Campos obrigatórios não preenchidos. |
| **2** | Clicar no botão **Send**. | Botão: `Send` | O formulário não é enviado. Envio bloqueado e mensagens de erro de campos obrigatórios exibidas na tela. |

---

### TC03 — Rejeição de anexo em formato inválido
* **ID:** QA-T105
* **Prioridade:** Normal
* **Objetivo:** Validar a restrição de extensões de arquivos no anexo do formulário de contato.
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Tentar anexar um arquivo em formato inválido. | Anexo: `documento.pdf` ou `imagem.jpg` | O sistema exibe mensagem de erro (ex: *"File format not supported"*) e não aceita o anexo. |

---

### TC06 — Rejeição de arquivo .txt acima do limite de tamanho
* **ID:** QA-T182
* **Prioridade:** Normal
* **Objetivo:** Validar o bloqueio de envio ao anexar arquivo `.txt` que ultrapasse o limite máximo permitido (regra da aplicação: limite de 0KB / arquivo com conteúdo).
* **Pré-condições:**
  * Estar na página de Contato (`/contact`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Anexar um arquivo `.txt` contendo texto. | Anexo: `arquivo_com_texto.txt` (> 0 KB, ex: 1 KB) | O sistema indica que o tamanho do arquivo excede o limite permitido (0 KB) e impede o envio. |
