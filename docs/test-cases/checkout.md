# Casos de Teste - Módulo de Checkout

**Aplicação:** Practice Software Testing  
**Módulo:** Finalização de Pedido e Pagamento (`/checkout`)  

---

### TC01 — Finalizar pedido com Cartão de Crédito com sucesso
* **ID:** QA-T24
* **Prioridade:** Alta
* **Objetivo:** Concluir uma compra no checkout utilizando o método Credit Card com dados válidos e confirmar se o pedido gerado consta na área "My Orders".
* **Pré-condições:**
  * Usuário autenticado e com ao menos 1 item no carrinho.
* **Passos:**
  1. Acessar a página do carrinho de compras (`https://practicesoftwaretesting.com/checkout`).
  2. Clicar no botão **Proceed to checkout**.
  3. Preencher as informações válidas de endereço e clicar em **Proceed to checkout**.
  4. Selecionar a opção de pagamento **Credit Card**.
  5. Preencher todos os campos do cartão com dados válidos (Card Number, Expiration Date, CVV e Name).
  6. Clicar no botão de confirmar/finalizar pagamento.
  7. Acessar a página "My Orders" (`https://practicesoftwaretesting.com/account/invoices`).
  8. Localizar o pedido na listagem pelo número gerado no passo 6.
* **Resultado Esperado:**
  * O pagamento é processado, exibe a confirmação e gera o número do pedido (ex: `ORD-12345`).
  * Na página de pedidos, o item é exibido com número, data, status e valor correspondentes ao checkout.

---

### TC02 — Tentativa de pagamento com Cartão de Crédito com campos vazios
* **ID:** QA-T63
* **Prioridade:** Média
* **Objetivo:** Submeter a opção Credit Card sem preencher o formulário.
* **Pré-condições:**
  * Estar logado, adicionar item ao carrinho e estar na etapa de Pagamento do checkout.
* **Passos:**
  1. Selecionar a opção de pagamento **Credit Card**.
  2. Manter todos os campos do formulário do cartão em branco.
  3. Clicar no botão de confirmar/finalizar pagamento.
* **Resultado Esperado:**
  * O envio é bloqueado e alertas de obrigatoriedade aparecem em cada campo do formulário.

---

### TC03 — Tentativa de pagamento com Cartão de Crédito com dados inválidos
* **ID:** QA-T26
* **Prioridade:** Média
* **Objetivo:** Inserir dados sintaticamente incorretos no formulário do cartão de crédito.
* **Pré-condições:**
  * Usuário logado e na etapa de Pagamento do checkout.
* **Passos:**
  1. Selecionar a opção de pagamento **Credit Card**.
  2. Inserir um número de cartão inválido (Card Number: `1234`).
  3. Inserir uma data de expiração no passado (Expiration: `01/1990`).
  4. Inserir um código CVV inválido (CVV: `1`).
  5. Clicar no botão de confirmar/finalizar pagamento.
* **Resultado Esperado:**
  * Exibição de mensagens de erro de validação para número de cartão inválido, data expirada e CVV incorreto.
  * O pagamento é recusado e o pedido não é gerado.

---

### TC04 — Finalizar pedido via Transferência Bancária (Bank Transfer) com sucesso
* **ID:** QA-T64
* **Prioridade:** Alta
* **Objetivo:** Concluir uma compra selecionando Bank Transfer com dados bancários válidos e confirmar a exibição na área "My Orders".
* **Pré-condições:**
  * Estar logado e na etapa de Pagamento do checkout com itens no carrinho.
* **Passos:**
  1. Selecionar a opção de pagamento **Bank Transfer**.
  2. Preencher todos os campos bancários solicitados com dados válidos (Account Name e Account Number).
  3. Clicar no botão de confirmar/finalizar pagamento.
  4. Acessar a página "My Orders" (`https://practicesoftwaretesting.com/account/my-orders`).
  5. Localizar o pedido na listagem pelo número gerado no passo 3.
* **Resultado Esperado:**
  * O pedido é processado com sucesso, exibe a confirmação e gera o número do pedido.
  * O pedido é exibido na listagem com número, data, status e valor correspondentes.

---

### TC05 — Tentativa de pagamento via Bank Transfer com campos vazios
* **ID:** QA-T65
* **Prioridade:** Média
* **Objetivo:** Confirmar o pagamento via Bank Transfer sem preencher os dados exigidos.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Pagamento do checkout.
* **Passos:**
  1. Selecionar a opção **Bank Transfer**.
  2. Manter os campos em branco.
  3. Clicar no botão de confirmar/finalizar pagamento.
* **Resultado Esperado:**
  * O envio é bloqueado com mensagens de alerta de campos obrigatórios.

---

### TC06 — Tentativa de pagamento via Bank Transfer com dados inválidos
* **ID:** QA-T66
* **Prioridade:** Média
* **Objetivo:** Inserir informações com formato inválido nos campos do Bank Transfer.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Pagamento do checkout.
* **Passos:**
  1. Selecionar a opção **Bank Transfer**.
  2. Digitar caracteres alfabéticos no campo de número da conta (Account Number: `ABC-TEST`).
  3. Clicar no botão de confirmar/finalizar pagamento.
* **Resultado Esperado:**
  * O sistema indica formato inválido para o campo de conta.
  * O pedido não é concluído.

---

### TC07 — Tentativa de finalizar o checkout sem escolher forma de pagamento
* **ID:** QA-T67
* **Prioridade:** Média
* **Objetivo:** Clicar no botão de confirmação sem selecionar nenhum método de pagamento.
* **Pré-condições:**
  * Usuário autenticado e com ao menos 1 item no carrinho.
* **Passos:**
  1. Acessar a página de checkout (`https://practicesoftwaretesting.com/checkout`).
  2. Preencher o formulário de endereço com dados válidos.
  3. Clicar no botão **Proceed to checkout** para avançar para a etapa de pagamento.
  4. Garantir que nenhuma opção de pagamento esteja selecionada.
  5. Clicar no botão de confirmar/finalizar pedido.
* **Resultado Esperado:**
  * Bloqueio do envio e exibição do alerta `"Please select a payment method"`.

---

### TC08 — Validação de campos obrigatórios no formulário de endereço
* **ID:** QA-T68
* **Prioridade:** Média
* **Objetivo:** Tentar avançar da etapa de endereço deixando todos os campos limpos.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Endereço do checkout.
* **Passos:**
  1. Acessar a etapa de Endereço no checkout (`https://practicesoftwaretesting.com/checkout`).
  2. Não preencher nenhum campo (manter formulário em branco).
  3. Clicar no botão **Proceed to checkout**.
* **Resultado Esperado:**
  * Navegação bloqueada e alertas de obrigatoriedade exibidos para os campos em branco.

---

### TC09 — Validação de formatos inválidos no formulário de endereço (CEP e Número da Casa)
* **ID:** QA-T69
* **Prioridade:** Média
* **Objetivo:** Inserir CEP em formato incorreto e letras no campo de número da casa.
* **Pré-condições:**
  * Estar logado com itens no carrinho e na etapa de Endereço do checkout.
* **Passos:**
  1. Acessar a etapa de Endereço no checkout (`https://practicesoftwaretesting.com/checkout`).
  2. Preencher demais campos válidos e inserir CEP inválido (Postal Code: `ABCD-123`).
  3. Preencher o campo House Number com letras (House Number: `XYZ`).
  4. Clicar no botão **Proceed to checkout**.
* **Resultado Esperado:**
  * Alertas de formato para CEP e Número da Casa são exibidos, bloqueando o avanço do checkout.

---

### TC10 — Checkout com carrinho de compras vazio
* **ID:** QA-T70
* **Prioridade:** Média
* **Objetivo:** Acessar a página do carrinho sem nenhum item adicionado e verificar se o botão de prosseguir para o checkout está desabilitado.
* **Pré-condições:**
  * Usuário autenticado e com o carrinho zerado (0 itens).
* **Passos:**
  1. Acessar a página do carrinho (`https://practicesoftwaretesting.com/checkout`).
  2. Verificar a interatividade do botão **Proceed to checkout**.
* **Resultado Esperado:**
  * O botão **Proceed to checkout** encontra-se desabilitado (não clicável), impedindo o prosseguimento do fluxo.

---

### TC11 — Acesso ao checkout para usuário não autenticado
* **ID:** QA-T71
* **Prioridade:** Alta
* **Objetivo:** Tentar acessar a URL do checkout sem possuir sessão ativa.
* **Pré-condições:**
  * Nenhuma sessão ativa no navegador (usuário deslogado).
* **Passos:**
  1. Digitar a URL do checkout (`https://practicesoftwaretesting.com/checkout`) na barra de endereço do navegador e pressionar Enter.
* **Resultado Esperado:**
  * Acesso negado e redirecionamento obrigatório para a página de login (`https://practicesoftwaretesting.com/auth/login`).
