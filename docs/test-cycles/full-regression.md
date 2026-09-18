# Ciclo de Testes: Regressão Total (Full Regression)

**Aplicação:** Practice Software Testing - Tool Shop  
**Objetivo:** Execução completa da suíte de testes cobrindo todos os módulos validados (Autenticação, Carrinho, Checkout, Favoritos, Busca/Filtros, Perfil e Contato) para assegurar a integridade geral do sistema.  

---

| ID | Chave | Versão | Componente/Tela | Nome do Caso de Teste |
| :---: | :---: | :---: | :--- | :--- |
| 1 | **QA-LOG-01** | 1.0 | Login | Login com credenciais válidas com sucesso |
| 2 | **QA-LOG-02** | 1.0 | Login | Login com campos vazios |
| 3 | **QA-LOG-03** | 1.0 | Login | Login com campos preenchidos apenas com espaços colados |
| 4 | **QA-LOG-05** | 1.0 | Login | Login com espaços antes/depois de credenciais válidas |
| 5 | **QA-LOG-06** | 1.0 | Login | Login com senha incorreta |
| 6 | **QA-LOG-07** | 1.0 | Login | Login com e-mail não cadastrado |
| 7 | **QA-LOG-08** | 1.0 | Login | Login com e-mail em formato inválido |
| 8 | **QA-LOG-09** | 1.0 | Login | Acessar link "Cadastre-se" a partir do login |
| 9 | **QA-LOG-10** | 1.0 | Login | Acessar link "Esqueceu a senha" a partir do login |
| 10 | **QA-LOG-11** | 1.0 | Login | Ícone de mostrar/esconder senha |
| 11 | **QA-LOG-12** | 1.0 | Login | Encerramento de sessão (Logout) com sucesso |
| 12 | **QA-CAD-01** | 1.0 | Cadastro | Cadastro válido com sucesso |
| 13 | **QA-CAD-02** | 1.0 | Cadastro | Cadastro com e-mail já existente |
| 14 | **QA-CAD-03** | 1.0 | Cadastro | Validação de campos obrigatórios vazios ou contendo apenas espaços |
| 15 | **QA-CAD-04** | 1.0 | Cadastro | Validação de formato de campos (E-mail, Data, Telefone e CEP) |
| 16 | **QA-CAD-05** | 1.0 | Cadastro | Validação de bloqueio de cadastro ao utilizar senha com nível de força Weak |
| 17 | **QA-CAD-06** | 1.0 | Cadastro | Validação de bloqueio de cadastro ao utilizar senha com nível de força Moderate |
| 18 | **QA-CAD-07** | 1.0 | Cadastro | Validação de limite mínimo de caracteres no campo Password |
| 19 | **QA-FAV-01** | 1.0 | Favoritos | Adicionar produto aos favoritos com sucesso |
| 20 | **QA-FAV-02** | 1.0 | Favoritos | Remover produto dos favoritos |
| 21 | **QA-FAV-03** | 1.0 | Favoritos | Persistência da lista de favoritos após logout e login |
| 22 | **QA-FAV-04** | 1.0 | Favoritos | Adicionar múltiplos produtos aos favoritos |
| 23 | **QA-FAV-05** | 1.0 | Favoritos | Ver lista de favoritos vazia |
| 24 | **QA-FAV-06** | 1.0 | Favoritos | Impedir alteração indevida de estado e duplicidade para produto já favoritado |
| 25 | **QA-FAV-07** | 1.0 | Favoritos | Bloqueio de favoritamento para usuário não autenticado (Negativo) |
| 26 | **QA-CON-01** | 1.0 | Contato | Enviar mensagem de contato com sucesso |
| 27 | **QA-CON-02** | 1.0 | Contato | Bloqueio de envio com Assunto e Mensagem vazios |
| 28 | **QA-CON-03** | 1.0 | Contato | Rejeição de anexo em formato inválido |
| 29 | **QA-CON-04** | 1.0 | Contato | Rejeição de arquivo .txt acima do limite de tamanho |
| 30 | **QA-CAR-01** | 1.0 | Carrinho | Adição de produtos ao carrinho |
| 31 | **QA-CAR-02** | 1.0 | Carrinho | Adição de produto com quantidade inicial customizada |
| 32 | **QA-CAR-03** | 1.0 | Carrinho | Alteração e recálculo de quantidade de item no carrinho |
| 33 | **QA-CAR-04** | 1.0 | Carrinho | Remoção de item do carrinho |
| 34 | **QA-CAR-05** | 1.0 | Carrinho | Análise do Valor Limite da quantidade de produto (Página do Produto) |
| 35 | **QA-CAR-06** | 1.0 | Carrinho | Análise do Valor Limite da quantidade de produto já dentro do carrinho |
| 36 | **QA-CAR-07** | 1.0 | Carrinho | Persistência dos itens do carrinho pós-autenticação (Logout/Login) |
| 37 | **QA-CAR-08** | 1.0 | Carrinho | Validação de agrupamento/soma de itens no carrinho |
| 38 | **QA-CKT-01** | 1.0 | Checkout | Finalizar pedido com Cartão de Crédito com sucesso |
| 39 | **QA-CKT-02** | 1.0 | Checkout | Tentativa de pagamento com Cartão de Crédito com campos vazios |
| 40 | **QA-CKT-03** | 1.0 | Checkout | Tentativa de pagamento com Cartão de Crédito com dados inválidos |
| 41 | **QA-CKT-04** | 1.0 | Checkout | Finalizar pedido via Transferência Bancária (Bank Transfer) com sucesso |
| 42 | **QA-CKT-05** | 1.0 | Checkout | Tentativa de pagamento via Bank Transfer com campos vazios |
| 43 | **QA-CKT-06** | 1.0 | Checkout | Tentativa de pagamento via Bank Transfer com dados inválidos |
| 44 | **QA-CKT-07** | 1.0 | Checkout | Tentativa de finalizar o checkout sem escolher forma de pagamento |
| 45 | **QA-CKT-08** | 1.0 | Checkout | Validação de campos obrigatórios no formulário de endereço |
| 46 | **QA-CKT-09** | 1.0 | Checkout | Validação de formatos inválidos no formulário de endereço (CEP e Número da Casa) |
| 47 | **QA-CKT-10** | 1.0 | Checkout | Checkout com carrinho de compras vazio |
| 48 | **QA-CKT-11** | 1.0 | Checkout | Acesso ao checkout para usuário não autenticado |
| 49 | **QA-FIL-01** | 1.0 | Busca e Filtro | Ordenação e Filtro Combinado de Produtos |
| 50 | **QA-FIL-02** | 1.0 | Busca e Filtro | Busca por produto inexistente no catálogo |
| 51 | **QA-FIL-03** | 1.0 | Busca e Filtro | Tratamento de Caracteres Especiais na Busca (Segurança) |
| 52 | **QA-FIL-04** | 1.0 | Busca e Filtro | Restauração do Catálogo via Limpeza de Filtros |
| 53 | **QA-FIL-05** | 1.0 | Busca e Filtro | Filtragem por Categorias |
| 54 | **QA-USER-01** | 1.0 | User Profile | Alterar dados básicos do perfil com sucesso |
| 55 | **QA-USER-02** | 1.0 | User Profile | Alterar senha do usuário com sucesso |
| 56 | **QA-USER-03** | 1.0 | User Profile | Tentativa de salvar dados básicos do perfil em branco |
| 57 | **QA-USER-04** | 1.0 | User Profile | Tentativa de alterar a senha para uma senha fraca |
| 58 | **QA-USER-05** | 1.0 | User Profile | Tentativa de alterar a senha para a mesma senha atual |




