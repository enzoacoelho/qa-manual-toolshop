# Casos de Teste - Módulo de Checkout

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Finalização de Pedido e Pagamento (`/checkout`)  

---

### TC01 — Finalizar pedido com Cartão de Crédito com sucesso
* **ID:** QA-T24
* **Prioridade:** Alta
* **Objetivo:** Concluir uma compra no checkout utilizando o método Credit Card com dados válidos e confirmar se o pedido gerado consta na área "My Orders".
* **Pré-condições:**
  * Usuário autenticado e com ao menos 1 item no carrinho.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página do carrinho de compras. | URL: `https://practicesoftwaretesting.com/checkout` | Página do carrinho carregada. |
| **2** | Clicar no botão **Proceed to checkout**. | Botão: `Proceed to checkout` | Avanço para a etapa de endereço. |
| **3** | Preencher endereço e prosseguir. | Informações de endereço válidas | Avanço para a etapa de pagamento. |
| **4** | Selecionar a opção de pagamento **Credit Card**. | Opção: `Credit Card` | Formulário de cartão exibido. |
| **5** | Preencher campos do cartão com dados válidos. | Card Number, Expiration Date, CVV, Name | Campos preenchidos. |
| **6** | Clicar em confirmar/finalizar pagamento. | Botão de finalização | Pagamento processado, exibe confirmação e gera número do pedido (ex: `ORD-12345`). |
| **7** | Acessar a página "My Orders". | URL: `https://practicesoftwaretesting.com/account/invoices` | Listagem de pedidos aberta. |
| **8** | Localizar o pedido na listagem. | Número do pedido gerado no passo 6 | Pedido exibido com número, data, status e valor correspondentes. |

---

### TC02 — Tentativa de pagamento com Cartão de Crédito com campos vazios
* **ID:** QA-T63
* **Prioridade:** Média
* **Objetivo:** Submeter a opção Credit Card sem preencher o formulário.
* **Pré-condições:**
  * Estar logado, adicionar item ao carrinho e estar na etapa de Pagamento do checkout.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar a opção de pagamento **Credit Card**. | Opção: `Credit Card` | Formulário exibido. |
| **2** | Manter os campos do formulário em branco. | *Nenhum* | Campos vazios. |
| **3** | Clicar em confirmar/finalizar pagamento. | Botão de finalização | Envio bloqueado e alertas de obrigatoriedade em cada campo. |

---

### TC03 — Tentativa de pagamento com Cartão de Crédito com dados inválidos
* **ID:** QA-T26
* **Prioridade:** Média
* **Objetivo:** Inserir dados sintaticamente incorretos no formulário do cartão de crédito.
* **Pré-condições:**
  * Usuário logado e na etapa de Pagamento do checkout.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar a opção de pagamento **Credit Card**. | Opção: `Credit Card` | Formulário exibido. |
| **2** | Inserir número de cartão inválido. | Card Number: `1234` | Campo preenchido com dados incorretos. |
| **3** | Inserir data de expiração no passado. | Expiration: `01/1990` | Campo preenchido com data expirada. |
| **4** | Inserir código CVV inválido. | CVV: `1` | Campo preenchido com dado incorreto. |
| **5** | Clicar em confirmar/finalizar pagamento. | Botão de finalização | Mensagens de erro de validação exibidas, pagamento recusado e pedido não gerado. |

---

### TC04 — Finalizar pedido via Transferência Bancária (Bank Transfer) com sucesso
* **ID:** QA-T64
* **Prioridade:** Alta
* **Objetivo:** Concluir uma compra selecionando Bank Transfer com dados bancários válidos e confirmar a exibição na área "My Orders".
* **Pré-condições:**
  * Estar logado e na etapa de Pagamento do checkout com itens no carrinho.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar a opção de pagamento **Bank Transfer**. | Opção: `Bank Transfer` | Formulário bancário exibido. |
| **2** | Preencher campos bancários com dados válidos. | Account Name, Account Number válidos | Campos preenchidos. |
| **3** | Clicar em confirmar/finalizar pagamento. | Botão de finalização | Pedido processado com sucesso, confirmação exibida e número gerado. |
| **4** | Acessar a página "My Orders". | URL: `https://practicesoftwaretesting.com/account/my-orders` | Listagem de pedidos aberta. |
| **5** | Localizar o pedido gerado. | Número do pedido do passo 3 | Pedido exibido com número, data, status e valor. |

---

### TC05 — Tentativa de pagamento via Bank Transfer com campos vazios
* **ID:** QA-T65
* **Prioridade:** Média
* **Objetivo:** Confirmar o pagamento via Bank Transfer sem preencher os dados exigidos.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Pagamento do checkout.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar a opção **Bank Transfer**. | Opção: `Bank Transfer` | Formulário exibido. |
| **2** | Manter os campos em branco. | *Nenhum* | Campos vazios. |
| **3** | Clicar em confirmar/finalizar pagamento. | Botão de finalização | Envio bloqueado com mensagens de alerta de campos obrigatórios. |

---

### TC06 — Tentativa de pagamento via Bank Transfer com dados inválidos
* **ID:** QA-T66
* **Prioridade:** Média
* **Objetivo:** Inserir informações com formato inválido nos campos do Bank Transfer.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Pagamento do checkout.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar a opção **Bank Transfer**. | Opção: `Bank Transfer` | Formulário exibido. |
| **2** | Digitar caracteres alfabéticos no número da conta. | Account Number: `ABC-TEST` | Campo preenchido com letras. |
| **3** | Clicar em confirmar/finalizar pagamento. | Botão de finalização | Sistema indica formato inválido para o campo de conta e o pedido não é concluído. |

---

### TC07 — Tentativa de finalizar o checkout sem escolher forma de pagamento
* **ID:** QA-T67
* **Prioridade:** Média
* **Objetivo:** Clicar no botão de confirmação sem selecionar nenhum método de pagamento.
* **Pré-condições:**
  * Usuário autenticado e com ao menos 1 item no carrinho.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página de checkout. | URL: `https://practicesoftwaretesting.com/checkout` | Carrinho/Checkout aberto. |
| **2** | Preencher o formulário de endereço. | Dados de endereço válidos | Endereço preenchido. |
| **3** | Clicar em **Proceed to checkout**. | Botão: `Proceed to checkout` | Avanço para a etapa de pagamento. |
| **4** | Garantir nenhuma opção de pagamento selecionada. | *Nenhum* | Nenhuma forma de pagamento marcada. |
| **5** | Clicar em confirmar/finalizar pedido. | Botão de finalização | Bloqueio do envio e exibição do alerta `"Please select a payment method"`. |

---

### TC08 — Validação de campos obrigatórios no formulário de endereço
* **ID:** QA-T68
* **Prioridade:** Média
* **Objetivo:** Tentar avançar da etapa de endereço deixando todos os campos limpos.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Endereço do checkout.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a etapa de Endereço no checkout. | URL: `https://practicesoftwaretesting.com/checkout` | Etapa de endereço exibida. |
| **2** | Manter formulário em branco. | *Nenhum* | Campos sem preenchimento. |
| **3** | Clicar em **Proceed to checkout**. | Botão: `Proceed to checkout` | Navegação bloqueada e alertas de obrigatoriedade exibidos para os campos. |

---

### TC09 — Validação de formatos inválidos no formulário de endereço (CEP e Número da Casa)
* **ID:** QA-T69
* **Prioridade:** Média
* **Objetivo:** Inserir CEP em formato incorreto e letras no campo de número da casa.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Endereço do checkout.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a etapa de Endereço no checkout. | URL: `https://practicesoftwaretesting.com/checkout` | Etapa de endereço exibida. |
| **2** | Preencher campos e inserir CEP inválido. | Postal Code: `ABCD-123` | Campo de CEP incorreto. |
| **3** | Preencher número da casa com letras. | House Number: `XYZ` | Campo de número incorreto. |
| **4** | Clicar em **Proceed to checkout**. | Botão: `Proceed to checkout` | Alertas de formato para CEP e Número da Casa são exibidos, bloqueando o avanço. |

---

### TC10 — Checkout com carrinho de compras vazio
* **ID:** QA-T70
* **Prioridade:** Média
* **Objetivo:** Acessar a página do carrinho sem nenhum item adicionado e verificar se o botão de prosseguir para o checkout está desabilitado.
* **Pré-condições:**
  * Usuário autenticado e com o carrinho zerado (0 itens).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página do carrinho. | URL: `https://practicesoftwaretesting.com/checkout` | Carrinho vazio aberto. |
| **2** | Verificar interatividade do botão de prosseguir. | Botão: `Proceed to checkout` | O botão encontra-se desabilitado (não clicável), impedindo o prosseguimento do fluxo. |

---

### TC11 — Acesso ao checkout para usuário não autenticado
* **ID:** QA-T71
* **Prioridade:** Alta
* **Objetivo:** Tentar acessar a URL do checkout sem possuir sessão ativa.
* **Pré-condições:**
  * Nenhuma sessão ativa no navegador (usuário deslogado).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Digitar URL do checkout no navegador. | URL: `https://practicesoftwaretesting.com/checkout` | Tentativa de acesso direto. |
| **2** | Pressionar Enter. | Tecla: `Enter` | Acesso negado e redirecionamento obrigatório para a página de login (`https://practicesoftwaretesting.com/auth/login`). |
