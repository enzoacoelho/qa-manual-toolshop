# Casos de Teste - Módulo de Favoritos

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Gestão de Favoritos (`/account/favorites`)  

---

### TC01 — Adicionar produto aos favoritos com sucesso
* **ID:** QA-T93
* **Prioridade:** Normal
* **Objetivo:** Confirmar que ao favoritar um produto, o botão altera seu estado visual, a mensagem de confirmação é exibida e o item é salvo na lista.
* **Pré-condições:**
  * Usuário autenticado na aplicação.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Localizar produto e clicar em favoritar. | Botão/Ícone: `Add to favorites` | O botão altera visualmente seu estado e a mensagem de confirmação de adição é exibida na tela. |
| **2** | Acessar a página de Favoritos. | URL: `https://practicesoftwaretesting.com/account/favorites` | O produto favoritado é exibido na lista da página de favoritos. |

---

### TC02 — Remover produto dos favoritos
* **ID:** QA-T94
* **Prioridade:** Normal
* **Objetivo:** Confirmar que o usuário consegue remover um item previamente favoritado através da tela de favoritos.
* **Pré-condições:**
  * Usuário autenticado e com ao menos 1 produto previamente favoritado.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página de Favoritos. | URL: `https://practicesoftwaretesting.com/account/favorites` | Página de favoritos aberta. |
| **2** | Clicar no botão de remover/excluir o produto. | Ícone: Lixeira / `Delete` | O produto é removido da tela e não consta mais na lista de favoritos do usuário. |

---

### TC03 — Persistência da lista de favoritos após logout e login
* **ID:** QA-T95
* **Prioridade:** Normal
* **Objetivo:** Garantir que um produto adicionado aos favoritos permaneça salvo na conta do usuário após ele encerrar a sessão e realizar login novamente.
* **Pré-condições:**
  * Usuário autenticado na aplicação.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Clicar em um produto e favoritar. | Detalhes do produto -> `Add to favorites` | O botão altera o estado e a mensagem de confirmação é exibida. |
| **2** | Realizar o logout da aplicação. | Opção: `Logout` | Sessão encerrada. |
| **3** | Efetuar o login novamente com a mesma conta. | Credenciais válidas | Login efetuado com sucesso. |
| **4** | Acessar a página de Favoritos. | URL: `https://practicesoftwaretesting.com/account/favorites` | O produto adicionado antes do logout continua sendo exibido na lista de favoritos. |

---

### TC04 — Adicionar múltiplos produtos aos favoritos
* **ID:** QA-T96
* **Prioridade:** Baixa
* **Objetivo:** Confirmar que o sistema suporta múltiplos produtos adicionados à lista de favoritos, alterando o estado de cada botão, exibindo as mensagens e sem sobresscrever itens.
* **Pré-condições:**
  * Usuário autenticado na aplicação.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Selecionar o Produto A e favoritar. | Produto A -> `Add to favorites` | Botão muda de estado e confirmação aparece. |
| **2** | Selecionar o Produto B e favoritar. | Produto B -> `Add to favorites` | Botão muda de estado e confirmação aparece. |
| **3** | Acessar a página de Favoritos. | URL: `https://practicesoftwaretesting.com/account/favorites` | A lista de favoritos exibe tanto o Produto A quanto o Produto B simultaneamente. |

---

### TC05 — Ver lista de favoritos vazia
* **ID:** QA-T97
* **Prioridade:** Baixa
* **Objetivo:** Validar o estado da tela de favoritos quando o usuário não possui nenhum item favoritado.
* **Pré-condições:**
  * Usuário autenticado sem nenhum produto favoritado na conta.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página de Favoritos. | URL: `https://practicesoftwaretesting.com/account/favorites` | A página exibe a mensagem amigável de estado vazio (ex: *"There are no favorites yet"*). |

---

### TC06 — Impedir alteração indevida de estado e duplicidade para produto já favoritado
* **ID:** QA-T98
* **Prioridade:** Normal
* **Objetivo:** Validar que se um produto já está favoritado, o botão permanece no estado "favoritado" (ou desabilitado), impedindo nova adição e duplicidade na lista.
* **Pré-condições:**
  * Usuário autenticado e com o Produto A já adicionado aos favoritos.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a página de Favoritos e abrir detalhes do produto. | URL de Favoritos -> Clique no produto | O produto é exibido corretamente na lista de favoritos; detalhes abertos. |
| **2** | Clicar no botão **Add to favorites** do produto já favoritado. | Botão: `Add to favorites` | O botão reflete o estado de favoritado. Ao interagir, o estado altera para não-favoritado, mantendo apenas 1 registro do item na lista (sem duplicidade). |

---

### TC07 — Bloqueio de favoritamento para usuário não autenticado (Negativo)
* **ID:** QA-T99
* **Prioridade:** Baixa
* **Objetivo:** Garantir que usuários deslogados não consigam favoritar produtos, alterar estado de botão ou receber confirmação de adição.
* **Pré-condições:**
  * Usuário **NÃO** autenticado no sistema (deslogado).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Acessar a tela inicial e abrir detalhes de um produto. | URL: `https://practicesoftwaretesting.com/` | Página de detalhes aberta. |
| **2** | Tentar clicar no botão **Add to favorites**. | Botão: `Add to favorites` | A ação é bloqueada, sem mudança no estado do botão e sem mensagem de sucesso. O sistema redireciona para a tela de login ou exibe alerta de autenticação. |
