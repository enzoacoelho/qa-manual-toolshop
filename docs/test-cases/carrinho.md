# Casos de Teste - Módulo de Carrinho

**Aplicação:** Practice Software Testing  
**Módulo:** Carrinho de Compras e Checkout (`/checkout`)  

---

### TC01 — Adição de produtos ao carrinho
* **ID:** QA-T183
* **Prioridade:** Alta
* **Objetivo:** Adicionar um produto ao carrinho a partir da página de detalhes e verificar a atualização do contador no ícone do cabeçalho.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve estar vazio no início do teste.
* **Passos:**
  1. Acessar a página de produtos (`https://practicesoftwaretesting.com/`).
  2. Clicar em um produto com estoque para abrir a página de detalhes.
  3. Clicar no botão **Add to cart**.
  4. Acessar a página do carrinho de compras (`https://practicesoftwaretesting.com/checkout`).
* **Resultado Esperado:**
  * Mensagem de sucesso exibida ao clicar em "Add to cart".
  * O contador do ícone do carrinho no cabeçalho atualiza para **1**.
  * A página do carrinho exibe o produto adicionado com quantidade e valor unitário corretos.

---

### TC02 — Adição de produto com quantidade inicial customizada
* **ID:** QA-T59
* **Prioridade:** Média
* **Objetivo:** Alterar o seletor de quantidade na página do produto antes de adicioná-lo ao carrinho.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve estar vazio.
* **Passos:**
  1. Acessar a página de produtos (`https://practicesoftwaretesting.com/`).
  2. Escolher um produto com estoque e clicar para abrir os detalhes.
  3. Alterar o campo/seletor de quantidade para o valor **3**.
  4. Clicar no botão **Add to cart**.
  5. Acessar a página do carrinho de compras (`https://practicesoftwaretesting.com/checkout`).
* **Resultado Esperado:**
  * Mensagem de sucesso exibida.
  * O produto é exibido na lista do carrinho com quantidade **3**.
  * O subtotal é calculado proporcionalmente (**3x o preço unitário**).

---

### TC03 — Alteração e recálculo de quantidade de item no carrinho
* **ID:** QA-T60
* **Prioridade:** Média
* **Objetivo:** Alterar a quantidade de um item diretamente na página do carrinho e validar se os subtotais e o total geral são recalculados instantaneamente.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve conter ao menos 1 item adicionado (quantidade inicial: 1).
* **Passos:**
  1. Acessar a página do carrinho de compras (`https://practicesoftwaretesting.com/checkout`).
  2. Alterar a quantidade do item para **2** (via digitação ou botão **+**).
  3. Validar o recálculo dos valores em tela.
  4. Alterar a quantidade do item para **1** (via digitação ou botão **-**).
  5. Validar o recálculo dos valores em tela.
* **Resultado Esperado:**
  * Ao alterar para **2**: O campo passa a exibir **2**, o subtotal do item atualiza para **2x o preço unitário** e o valor total geral reflete a mudança.
  * Ao alterar para **1**: O subtotal e o total geral retornam ao valor unitário original.

---

### TC04 — Remoção de item do carrinho
* **ID:** QA-T11
* **Prioridade:** Alta
* **Objetivo:** Acionar a exclusão de um item diretamente na tela do carrinho e confirmar a transição para o estado de carrinho vazio.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve conter exatamente 1 item adicionado.
* **Passos:**
  1. Acessar a página do carrinho de compras (`https://practicesoftwaretesting.com/checkout`).
  2. Clicar no botão de remover/excluir (ícone de lixeira ou botão **Remove**).
  3. Validar a exibição da tela pós-remoção.
  4. Validar o contador do carrinho no menu superior (cabeçalho).
* **Resultado Esperado:**
  * O item é removido imediatamente da listagem.
  * Exibição da mensagem de carrinho vazio (ex: `"Your cart is empty"`).
  * O ícone do carrinho no cabeçalho exibe a quantidade **0** ou fica sem numeração.

---

### TC05 — Análise do Valor Limite da quantidade de produto (Página do Produto)
* **ID:** QA-T12
* **Prioridade:** Média
* **Objetivo:** Testar os limites de quantidade (0, 99 e 100) na página de detalhes do produto.
* **Pré-condições:**
  * Estar na página de um produto com estoque (`https://practicesoftwaretesting.com/`).
* **Passos:**
  1. Tentar diminuir ou digitar a quantidade **0** no campo correspondente.
  2. Digitar o valor **100** no campo de quantidade.
  3. Digitar o valor **99** no campo de quantidade.
  4. Clicar no botão **Add to cart**.
  5. Abrir a tela do carrinho (`https://practicesoftwaretesting.com/checkout`).
* **Resultado Esperado:**
  * No passo 1: O sistema impede a alteração, mantendo o valor mínimo de **1**.
  * No passo 2: O campo limita a digitação em **99** e exibe alerta de limite máximo.
  * No passo 3: O valor **99** é mantido sem alertas de erro.
  * No passo 5: O produto é adicionado em apenas uma linha no carrinho, exibindo quantidade **99** e valor total equivalente a **99x o preço unitário**.

---

### TC06 — Análise do Valor Limite da quantidade de produto já dentro do carrinho
* **ID:** QA-T185
* **Prioridade:** Média
* **Objetivo:** Validar o comportamento do sistema ao tentar alterar a quantidade para valores inválidos (vazio, 0, 100) ou válidos (99) dentro do carrinho.
* **Pré-condições:**
  * Estar com um produto (quantidade: 1) no carrinho e com estoque disponível.
* **Passos:**
  1. Acessar a lista do carrinho (`https://practicesoftwaretesting.com/checkout`).
  2. Apagar o valor do campo de quantidade, deixando-o em branco.
  3. Clicar no campo de quantidade e digitar **00**.
  4. Clicar no campo de quantidade e digitar **100**.
  5. Clicar no campo de quantidade e digitar **99**.
* **Resultado Esperado:**
  * Ao apagar o valor: O campo não fica em branco e retorna para a quantidade anterior (**1**).
  * Ao digitar **00**: Exibe alerta de quantidade não permitida e reverte o valor para **1**.
  * Ao digitar **100**: Exibe alerta informando que o limite é **99** e reverte o valor para **1**.
  * Ao digitar **99**: Nenhum erro é exibido, o campo aceita o valor **99** e o total a pagar atualiza para **99x o valor unitário**.

---

### TC07 — Persistência dos itens do carrinho pós-autenticação (Logout/Login)
* **ID:** QA-T22
* **Prioridade:** Média
* **Objetivo:** Garantir que os itens adicionados ao carrinho continuem salvos após o encerramento e novo acesso à sessão.
* **Pré-condições:**
  * O usuário deve possuir credenciais válidas (`customer@practicesoftwaretesting.com`).
* **Passos:**
  1. Acessar a tela de login (`https://practicesoftwaretesting.com/auth/login`) e autenticar-se.
  2. Ir para a página de produtos, escolher um item e clicar em **Add to cart**.
  3. Clicar no botão de **Logout** na barra de navegação.
  4. Realizar novo login com as mesmas credenciais.
  5. Acessar a página do carrinho de compras (`https://practicesoftwaretesting.com/checkout`).
* **Resultado Esperado:**
  * O produto adicionado antes do logout permanece presente no carrinho com os dados mantidos.

---

### TC08 — Validação de agrupamento/soma de itens no carrinho
* **ID:** QA-T10
* **Prioridade:** Média
* **Objetivo:** Confirmar que itens idênticos agrupam na mesma linha incrementando a quantidade e que itens distintos criam novas linhas com recálculo do total.
* **Pré-condições:**
  * Estar logado na aplicação.
  * Carrinho deve estar vazio no início do teste.
* **Passos:**
  1. Acessar a página de produtos (`https://practicesoftwaretesting.com/`).
  2. Selecionar o Produto A e clicar em **Add to cart**.
  3. Clicar novamente em **Add to cart** no mesmo Produto A.
  4. Acessar a página do carrinho (`https://practicesoftwaretesting.com/checkout`).
  5. Voltar para a vitrine, selecionar o Produto B e clicar em **Add to cart**.
  6. Acessar a página do carrinho novamente.
* **Resultado Esperado:**
  * No passo 4: O carrinho exibe o Produto A em uma única linha com **quantidade 2**.
  * No passo 6: O carrinho exibe **2 linhas distintas** (Produto A e Produto B), com subtotais individuais e o total geral recalculado corretamente.
