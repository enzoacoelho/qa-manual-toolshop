# Casos de Teste - Módulo de Busca e Filtro

**Aplicação:** Practice Software Testing - Tool Shop  
**Módulo:** Busca, Filtros e Ordenação (`/`)  

---

### TC01 — Ordenação e Filtro Combinado de Produtos
* **ID:** QA-T85
* **Prioridade:** Normal
* **Objetivo:** Validar a aplicação simultânea de busca por palavra-chave, faixa de preço e alteração de ordenação (A-Z, Z-A, Menor Preço, Maior Preço).
* **Pré-condições:**
  * Estar na página inicial (`/`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Digitar termo e definir intervalo de preço. | Termo: `hammer`<br>Preço: `$1 a $100` | Produtos filtrados por palavra-chave e faixa de preço. |
| **2** | Selecionar ordenação por Nome (A-Z). | Ordenação: `Name (A-Z)` | Listagem reordenada em ordem alfabética crescente. |
| **3** | Selecionar ordenação por Nome (Z-A). | Ordenação: `Name (Z-A)` | Listagem reordenada em ordem alfabética decrescente. |
| **4** | Selecionar ordenação por Menor Preço. | Ordenação: `Price (Low-High)` | Listagem reordenada do menor para o maior valor. |
| **5** | Selecionar ordenação por Maior Preço. | Ordenação: `Price (High-Low)` | Listagem reordenada do maior para o menor valor. |

---

### TC02 — Busca por produto inexistente no catálogo
* **ID:** QA-T86
* **Prioridade:** Baixa
* **Objetivo:** Validar o comportamento do sistema ao pesquisar por um produto que não existe na base de dados.
* **Pré-condições:**
  * Estar na página inicial (`/`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Digitar um termo inexistente e pesquisar. | Termo: `xyzxyz123` | Retorno de lista vazia e mensagem clara ao usuário indicando que nenhum resultado foi encontrado (ex: *"There are no products found"*), sem exibir itens na grade. |

---

### TC03 — Tratamento de Caracteres Especiais na Busca (Segurança)
* **ID:** QA-T87
* **Prioridade:** Normal
* **Objetivo:** Garantir que o campo de busca sanitize entradas maliciosas (XSS e SQL Injection) sem quebrar a aplicação ou expor erros de banco de dados.
* **Pré-condições:**
  * Estar na página inicial (`/`).

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Inserir payload XSS no campo de busca. | Termo: `<script>alert(1)</script>` | Entrada renderizada de forma segura (sanitizada), sem execução de alerta JavaScript. |
| **2** | Inserir payload SQL Injection no campo de busca. | Termo: `' OR 1=1 --` | Sistema lida de forma graciosa, sem exceções técnicas ou brechas, exibindo 0 resultados. |

---

### TC04 — Restauração do Catálogo via Limpeza de Filtros
* **ID:** QA-T88
* **Prioridade:** Baixa
* **Objetivo:** Confirmar que acionar a opção de limpar filtros remove todas as restrições (busca, faixa de preço, ordenação e categorias) e restaura a listagem completa de produtos.
* **Pré-condições:**
  * Estar na página inicial (`/`) com ao menos um filtro ativo.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Aplicar filtros na página de catálogo. | Termo: `hammer`<br>Sort: `Price (High-Low)` | Filtros aplicados na listagem de produtos. |
| **2** | Acionar a opção de limpeza de filtros. | Botão: **Clear** / **Reset filters** | Seletores e inputs resetados para o estado padrão. Catálogo recarregado com a listagem integral de produtos. |

---

### TC05 — Filtragem por Categorias
* **ID:** QA-T184
* **Prioridade:** Normal
* **Objetivo:** Confirmar que a seleção de cada uma das categorias disponíveis no menu filtra a listagem de produtos no catálogo, exibindo apenas os itens correspondentes.
* **Pré-condições:**
  * Acessar a tela inicial em `https://practicesoftwaretesting.com`.

| Passo | Descrição da Ação | Massa de Dados / Parâmetros | Resultado Esperado |
| :---: | :--- | :--- | :--- |
| **1** | Clicar na categoria **Hand Tools**. | Categoria: Hand Tools | Catálogo atualiza exibindo exclusivamente produtos de ferramentas manuais. |
| **2** | Clicar na categoria **Power Tools**. | Categoria: Power Tools | Catálogo atualiza exibindo exclusivamente produtos de ferramentas elétricas. |
| **3** | Clicar na categoria **Other**. | Categoria: Other | Catálogo atualiza exibindo exclusivamente produtos da categoria Outros. |
| **4** | Clicar na categoria **Special Tools**. | Categoria: Special Tools | Catálogo atualiza exibindo exclusivamente produtos de ferramentas especiais. |
| **5** | Clicar na categoria **Rentals**. | Categoria: Rentals | Catálogo atualiza exibindo exclusivamente itens disponíveis para aluguel. |
