# Casos de Teste - Módulo de Busca e Filtro

**Aplicação:** Practice Software Testing  
**Módulo:** Busca, Filtros e Ordenação (`/`)  

---

### TC01 — Ordenação e Filtro Combinado de Produtos
* **ID:** QA-T85
* **Prioridade:** Normal
* **Objetivo:** Validar a aplicação simultânea de busca por palavra-chave, faixa de preço e alteração de ordenação (A-Z, Z-A, Menor Preço, Maior Preço).
* **Pré-condições:**
  * Estar na página inicial (`/`).
* **Passos:**
  1. Digitar um termo no campo de busca e definir um intervalo de preço (Termo: `hammer` / Preço: $1 a $100).
  2. Selecionar a ordenação por Nome (A-Z) (`Name (A-Z)`).
  3. Selecionar a ordenação por Nome (Z-A) (`Name (Z-A)`).
  4. Selecionar a ordenação por Menor Preço (`Price (Low-High)`).
  5. Selecionar a ordenação por Maior Preço (`Price (High-Low)`).
* **Resultado Esperado:**
  * A lista exibe apenas produtos contendo "hammer" dentro da faixa de preço selecionada.
  * A listagem é reordenada corretamente a cada alteração de filtro: em ordem alfabética crescente (A-Z), alfabética decrescente (Z-A), do menor para o maior valor (Low-High) e do maior para o menor valor (High-Low).

---

### TC02 — Busca por produto inexistente no catálogo
* **ID:** QA-T86
* **Prioridade:** Baixa
* **Objetivo:** Validar o comportamento do sistema ao pesquisar por um produto que não existe na base de dados.
* **Pré-condições:**
  * Estar na página inicial (`/`).
* **Passos:**
  1. Digitar um termo inexistente na barra de busca e acionar a pesquisa (Termo: `xyzxyz123`).
* **Resultado Esperado:**
  * Retorno de lista vazia acompanhado de uma mensagem clara ao usuário indicando que nenhum resultado foi encontrado (ex: *"There are no products found"*), sem exibir produtos na grade.

---

### TC03 — Tratamento de Caracteres Especiais na Busca (Segurança)
* **ID:** QA-T87
* **Prioridade:** Normal
* **Objetivo:** Garantir que o campo de busca sanitize entradas maliciosas (XSS e SQL Injection) sem quebrar a aplicação ou expor erros de banco de dados.
* **Pré-condições:**
  * Estar na página inicial (`/`).
* **Passos:**
  1. Inserir payload XSS no campo de busca e pesquisar (Termo: `<script>alert(1)</script>`).
  2. Inserir payload SQL Injection no campo de busca e pesquisar (Termo: `' OR 1=1 --`).
* **Resultado Esperado:**
  * Para o payload XSS: a entrada é renderizada de forma segura (sanitizada), sem execução do alerta JavaScript.
  * Para o payload SQL Injection: o sistema lida de forma graciosa, sem retornar exceções técnicas ou brechas de banco de dados, exibindo 0 resultados.

---

### TC04 — Restauração do Catálogo via Limpeza de Filtros
* **ID:** QA-T88
* **Prioridade:** Baixa
* **Objetivo:** Confirmar que acionar a opção de limpar filtros remove todas as restrições (busca, faixa de preço, ordenação e categorias) e restaura a listagem completa de produtos.
* **Pré-condições:**
  * Estar na página inicial (`/`) com ao menos um filtro ativo.
* **Passos:**
  1. Aplicar filtros na página (Termo: `hammer` / Sort: `Price (High-Low)`).
  2. Clicar no botão **Clear** / **Reset filters**.
* **Resultado Esperado:**
  * Todos os seletores e inputs de filtro são resetados para o estado padrão.
  * O catálogo recarrega a exibição padrão contendo a listagem integral de produtos.

---

### TC05 — Filtragem por Categorias
* **ID:** QA-T184
* **Prioridade:** Normal
* **Objetivo:** Confirmar que a seleção de cada uma das categorias disponíveis no menu filtra a listagem de produtos no catálogo, exibindo apenas os itens correspondentes.
* **Pré-condições:**
  * Acessar a tela inicial em `https://practicesoftwaretesting.com`.
* **Passos:**
  1. Clicar na categoria **Hand Tools**.
  2. Clicar na categoria **Power Tools**.
  3. Clicar na categoria **Other**.
  4. Clicar na categoria **Special Tools**.
  5. Clicar na categoria **Rentals**.
* **Resultado Esperado:**
  * A cada clique, o catálogo atualiza imediatamente exibindo exclusivamente os produtos vinculados à categoria selecionada (**Hand Tools**, **Power Tools**, **Other**, **Special Tools** e **Rentals**, respectivamente).
