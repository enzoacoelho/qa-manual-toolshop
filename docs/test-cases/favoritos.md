# Casos de Teste - Módulo de Favoritos

**Aplicação:** Practice Software Testing  
**Módulo:** Gestão de Favoritos (`/account/favorites`)  

---

### TC01 — Adicionar produto aos favoritos com sucesso
* **ID:** QA-T93
* **Prioridade:** Normal
* **Objetivo:** Confirmar que ao favoritar um produto, o botão altera seu estado visual, a mensagem de confirmação é exibida e o item é salvo na lista.
* **Pré-condições:**
  * Usuário autenticado na aplicação.
* **Passos:**
  1. Localizar um produto no catálogo e clicar no botão/ícone de favoritar (**Add to favorites**).
  2. Acessar a página de Favoritos (`https://practicesoftwaretesting.com/account/favorites`).
* **Resultado Esperado:**
  * O botão altera visualmente seu estado E a mensagem de confirmação de adição é exibida na tela.
  * O produto favoritado é exibido na lista da página de favoritos.

---

### TC02 — Remover produto dos favoritos
* **ID:** QA-T94
* **Prioridade:** Normal
* **Objetivo:** Confirmar que o usuário consegue remover um item previamente favoritado através da tela de favoritos.
* **Pré-condições:**
  * Usuário autenticado e com ao menos 1 produto previamente favoritado.
* **Passos:**
  1. Acessar a página de Favoritos (`https://practicesoftwaretesting.com/account/favorites`).
  2. Clicar no botão de remover/excluir o produto (Ícone de Lixeira / Delete).
* **Resultado Esperado:**
  * O produto é removido da tela e não consta mais na lista de favoritos do usuário.

---

### TC03 — Persistência da lista de favoritos após logout e login
* **ID:** QA-T95
* **Prioridade:** Normal
* **Objetivo:** Garantir que um produto adicionado aos favoritos permaneça salvo na conta do usuário após ele encerrar a sessão e realizar login novamente.
* **Pré-condições:**
  * Usuário autenticado na aplicação.
* **Passos:**
  1. Clicar em um produto na tela inicial para exibir os detalhes.
  2. Clicar em **Add to favorites**.
  3. Realizar o logout da aplicação.
  4. Efetuar o login novamente com a mesma conta.
  5. Acessar a página de Favoritos (`https://practicesoftwaretesting.com/account/favorites`).
* **Resultado Esperado:**
  * O botão altera seu estado e a mensagem de confirmação é exibida ao favoritar.
  * O produto adicionado antes do logout continua sendo exibido na lista de favoritos após o re-login.

---

### TC04 — Adicionar múltiplos produtos aos favoritos
* **ID:** QA-T96
* **Prioridade:** Baixa
* **Objetivo:** Confirmar que o sistema suporta múltiplos produtos adicionados à lista de favoritos, alterando o estado de cada botão, exibindo as mensagens e sem sobresscrever itens.
* **Pré-condições:**
  * Usuário autenticado na aplicação.
* **Passos:**
  1. Na tela inicial, clicar no Produto A exibido.
  2. Clicar em **Add to favorites** no Produto A.
  3. Voltar para a tela inicial/produtos.
  4. Clicar no Produto B.
  5. Clicar em **Add to favorites** no Produto B.
  6. Acessar a página de Favoritos (`https://practicesoftwaretesting.com/account/favorites`).
* **Resultado Esperado:**
  * Para cada produto, o botão **Add to favorites** muda de estado e a mensagem de confirmação aparece.
  * A lista de favoritos exibe tanto o Produto A quanto o Produto B simultaneamente.

---

### TC05 — Ver lista de favoritos vazia
* **ID:** QA-T97
* **Prioridade:** Baixa
* **Objetivo:** Validar o estado da tela de favoritos quando o usuário não possui nenhum item favoritado.
* **Pré-condições:**
  * Usuário autenticado sem nenhum produto favoritado na conta.
* **Passos:**
  1. Acessar a página de Favoritos (`https://practicesoftwaretesting.com/account/favorites`).
* **Resultado Esperado:**
  * A página exibe a mensagem amigável de estado vazio (ex: *"There are no favorites yet"*).

---

### TC06 — Impedir alteração indevida de estado e duplicidade para produto já favoritado
* **ID:** QA-T98
* **Prioridade:** Normal
* **Objetivo:** Validar que se um produto já está favoritado, o botão permanece no estado "favoritado" (ou desabilitado), impedindo nova adição e duplicidade na lista.
* **Pré-condições:**
  * Usuário autenticado e com o Produto A já adicionado aos favoritos.
* **Passos:**
  1. Acessar a página de Favoritos (`https://practicesoftwaretesting.com/account/favorites`).
  2. Clicar no produto que está na lista de favoritos para abrir os detalhes.
  3. Clicar no botão **Add to favorites** do produto já favoritado.
* **Resultado Esperado:**
  * O produto é exibido corretamente na lista de favoritos.
  * Na página do produto, o botão reflete o estado de favoritado (desabilitado ou destacado).
  * Ao interagir com o botão, o estado do produto altera para não-favoritado, mantendo apenas 1 registro do item na lista.

---

### TC07 — Bloqueio de favoritamento para usuário não autenticado (Negativo)
* **ID:** QA-T99
* **Prioridade:** Baixa
* **Objetivo:** Garantir que usuários deslogados não consigam favoritar produtos, alterar estado de botão ou receber confirmação de adição.
* **Pré-condições:**
  * Usuário **NÃO** autenticado no sistema (deslogado).
* **Passos:**
  1. Acessar a tela inicial/produtos (`https://practicesoftwaretesting.com/`).
  2. Clicar em um produto para abrir a tela de detalhes.
  3. Tentar clicar no botão **Add to favorites**.
* **Resultado Esperado:**
  * A ação é bloqueada, sem mudança no estado do botão e sem mensagem de sucesso.
  * O sistema redireciona para a tela de login ou exibe uma mensagem informando que o usuário deve estar logado para realizar a ação.
