# Casos de Teste - Módulo de Carrinho

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Carrinho de Compras e Checkout (`/checkout`)  

---

### TC01 — Adição de produtos ao carrinho
* **ID:** QA-T183
* **Prioridade:** Alta
* **Objetivo:** Adicionar um produto ao carrinho a partir da página de detalhes e verificar a atualização do contador no ícone do cabeçalho.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve estar vazio no início do teste.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página de produtos. | URL: `https://practicesoftwaretesting.com/` | Página inicial carregada. |
| **2** | Clicar em um produto com estoque. | *Nenhum* | Página de detalhes do produto aberta. |
| **3** | Clicar no botão **Add to cart**. | Botão: `Add to cart` | Mensagem de sucesso exibida. |
| **4** | Acessar a página do carrinho de compras. | URL: `https://practicesoftwaretesting.com/checkout` | Contador do ícone do cabeçalho atualiza para **1**. Página do carrinho exibe o produto com quantidade e valor corretos. |

---

### TC02 — Adição de produto com quantidade inicial customizada
* **ID:** QA-T59
* **Prioridade:** Média
* **Objetivo:** Alterar o seletor de quantidade na página do produto antes de adicioná-lo ao carrinho.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve estar vazio.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página de produtos. | URL: `https://practicesoftwaretesting.com/` | Página inicial carregada. |
| **2** | Escolher um produto com estoque. | *Nenhum* | Página de detalhes aberta. |
| **3** | Alterar o campo de quantidade. | Quantidade: `3` | Campo atualizado para 3. |
| **4** | Clicar no botão **Add to cart**. | Botão: `Add to cart` | Mensagem de sucesso exibida. |
| **5** | Acessar a página do carrinho. | URL: `https://practicesoftwaretesting.com/checkout` | Produto listado com quantidade **3** e subtotal calculado proporcionalmente (3x o preço unitário). |

---

### TC03 — Alteração e recálculo de quantidade de item no carrinho
* **ID:** QA-T60
* **Prioridade:** Média
* **Objetivo:** Alterar a quantidade de um item diretamente na página do carrinho e validar se os subtotais e o total geral são recalculados instantaneamente.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve conter ao menos 1 item adicionado (quantidade inicial: 1).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página do carrinho de compras. | URL: `https://practicesoftwaretesting.com/checkout` | Carrinho carregado com o item. |
| **2** | Alterar a quantidade do item para **2**. | Quantidade: `2` (via input ou botão **+**) | Campo exibe **2**, subtotal do item atualiza para 2x o preço unitário e o total geral reflete a mudança. |
| **3** | Alterar a quantidade do item para **1**. | Quantidade: `1` (via input ou botão **-**) | Subtotal e total geral retornam ao valor unitário original. |

---

### TC04 — Remoção de item do carrinho
* **ID:** QA-T11
* **Prioridade:** Alta
* **Objetivo:** Acionar a exclusão de um item diretamente na tela do carrinho e confirmar a transição para o estado de carrinho vazio.
* **Pré-condições:**
  * Estar logado na aplicação.
  * O carrinho deve conter exatamente 1 item adicionado.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página do carrinho de compras. | URL: `https://practicesoftwaretesting.com/checkout` | Carrinho carregado com o item. |
| **2** | Clicar no botão de remover/excluir. | Botão/Ícone: `Remove` / Lixeira | Item é removido imediatamente da listagem. |
| **3** | Validar tela pós-remoção e menu superior. | *Nenhum* | Mensagem de carrinho vazio (`"Your cart is empty"`) exibida. Ícone do carrinho no cabeçalho exibe quantidade **0** ou fica sem numeração. |

---

### TC05 — Análise do Valor Limite da quantidade de produto (Página do Produto)
* **ID:** QA-T12
* **Prioridade:** Média
* **Objetivo:** Testar os limites de quantidade (0, 99 e 100) na página de detalhes do produto.
* **Pré-condições:**
  * Estar na página de um produto com estoque (`https://practicesoftwaretesting.com/`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Tentar diminuir ou digitar a quantidade **0**. | Quantidade: `0` | Sistema impede a alteração, mantendo o valor mínimo de **1**. |
| **2** | Digitar o valor **100** no campo. | Quantidade: `100` | O campo limita a digitação em **99** e exibe alerta de limite máximo. |
| **3** | Digitar o valor **99** e adicionar ao carrinho. | Quantidade: `99` / Botão: `Add to cart` | Valor **99** mantido sem alertas de erro. |
| **4** | Abrir a tela do carrinho. | URL: `https://practicesoftwaretesting.com/checkout` | Produto adicionado em apenas uma linha com quantidade **99** e valor total equivalente a 99x o preço unitário. |

---

### TC06 — Análise do Valor Limite da quantidade de produto já dentro do carrinho
* **ID:** QA-T185
* **Prioridade:** Média
* **Objetivo:** Validar o comportamento do sistema ao tentar alterar a quantidade para valores inválidos (vazio, 0, 100) ou válidos (99) dentro do carrinho.
* **Pré-condições:**
  * Estar com um produto (quantidade: 1) no carrinho e com estoque disponível.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a lista do carrinho. | URL: `https://practicesoftwaretesting.com/checkout` | Carrinho carregado. |
| **2** | Apagar o valor do campo de quantidade. | Valor: `[vazio]` | O campo não fica em branco e retorna para a quantidade anterior (**1**). |
| **3** | Digitar **00** no campo de quantidade. | Valor: `00` | Exibe alerta de quantidade não permitida e reverte para **1**. |
| **4** | Digitar **100** no campo de quantidade. | Valor: `100` | Exibe alerta informando limite de **99** e reverte para **1**. |
| **5** | Digitar **99** no campo de quantidade. | Valor: `99` | Nenhum erro exibido, aceita o valor **99** e o total a pagar atualiza para 99x o valor unitário. |

---

### TC07 — Persistência dos itens do carrinho pós-autenticação (Logout/Login)
* **ID:** QA-T22
* **Prioridade:** Média
* **Objetivo:** Garantir que os itens adicionados ao carrinho continuem salvos após o encerramento e novo acesso à sessão.
* **Pré-condições:**
  * O usuário deve possuir credenciais válidas (`customer@practicesoftwaretesting.com`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar tela de login e autenticar-se. | URL: `https://practicesoftwaretesting.com/auth/login`<br>Credenciais válidas | Usuário logado com sucesso. |
| **2** | Adicionar um item ao carrinho. | Vitrine de produtos -> **Add to cart** | Produto adicionado. |
| **3** | Clicar no botão de **Logout**. | Opção: `Logout` no menu | Sessão encerrada. |
| **4** | Realizar novo login com as mesmas credenciais. | Credenciais válidas | Login efetuado. |
| **5** | Acessar a página do carrinho de compras. | URL: `https://practicesoftwaretesting.com/checkout` | O produto adicionado antes do logout permanece presente no carrinho com os dados mantidos. |

---

### TC08 — Validação de agrupamento/soma de itens no carrinho
* **ID:** QA-T10
* **Prioridade:** Média
* **Objetivo:** Confirmar que itens idênticos agrupam na mesma linha incrementando a quantidade e que itens distintos criam novas linhas com recálculo do total.
* **Pré-condições:**
  * Estar logado na aplicação.
  * Carrinho deve estar vazio no início do teste.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar o Produto A e adicionar ao carrinho. | Produto A -> **Add to cart** (2 vezes) | Produto A adicionado duas vezes. |
| **2** | Acessar a página do carrinho. | URL: `https://practicesoftwaretesting.com/checkout` | Carrinho exibe o Produto A em uma única linha com **quantidade 2**. |
| **3** | Retornar à vitrine, selecionar o Produto B e adicionar. | Produto B -> **Add to cart** | Produto B adicionado. |
| **4** | Acessar a página do carrinho novamente. | URL: `https://practicesoftwaretesting.com/checkout` | O carrinho exibe **2 linhas distintas** (Produto A e Produto B), com subtotais individuais e o total geral recalculado corretamente. |
