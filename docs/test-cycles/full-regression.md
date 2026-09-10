# Ciclo de Testes: Regressão Total (Full Regression)

**Aplicação:** Practice Software Testing - Tool Shop  
**Objetivo:** Execução completa da suíte de testes cobrindo todos os módulos validados (Autenticação, Carrinho, Checkout, Favoritos, Busca/Filtros, Perfil e Contato) para assegurar a integridade geral do sistema.  
**Métrica do Ciclo:** 59 casos totais (52 Passados / 7 Falhados)  

---

## 1. Casos com Status: PASS (Passou — 52 Casos)

| ID | Chave | Versão | Nome do Caso de Teste | Atribuído a | Status |
| :---: | :---: | :---: | :--- | :---: | :---: |
| 1 | **QA-T6** | 1.0 | TC01 — Login com sucesso | enzo coelho | Passou |
| 2 | **QA-T9** | 1.0 | TC02 — Login com campos vazios | enzo coelho | Passou |
| 3 | **QA-T43** | 1.0 | TC03 — Login com campos preenchidos apenas com espaços | enzo coelho | Passou |
| 4 | **QA-T44** | 1.0 | TC04 — Login com espaços antes/depois de credenciais válidas | enzo coelho | Passou |
| 5 | **QA-T7** | 1.0 | TC05 — Login com senha incorreta | enzo coelho | Passou |
| 6 | **QA-T8** | 1.0 | TC06 — Login com e-mail não cadastrado | enzo coelho | Passou |
| 7 | **QA-T45** | 1.0 | TC07 — Login com e-mail em formato inválido | enzo coelho | Passou |
| 8 | **QA-T46** | 1.0 | TC08 — Acessar link "Cadastre-se" a partir do login | enzo coelho | Passou |
| 9 | **QA-T47** | 1.0 | TC09 — Acessar link "Esqueceu a senha" a partir do login | enzo coelho | Passou |
| 10 | **QA-T48** | 1.0 | TC10 — Ícone de mostrar/esconder senha | enzo coelho | Passou |
| 11 | **QA-T181** | 1.0 | TC11 — Logout | enzo coelho | Passou |
| 12 | **QA-T1** | 1.0 | TC01 — Cadastro válido com sucesso | enzo coelho | Passou |
| 13 | **QA-T2** | 1.0 | TC02 — Cadastro com e-mail já existente | enzo coelho | Passou |
| 14 | **QA-T3** | 1.0 | TC03 — Validação de campos obrigatórios vazios ou contendo apenas espaços | enzo coelho | Passou |
| 15 | **QA-T49** | 1.0 | TC06 — Análise do Valor Limite do tamanho da senha | enzo coelho | Passou |
| 16 | **QA-T183** | 1.0 | TC01 — Adição de produtos ao carrinho | enzo coelho | Passou |
| 17 | **QA-T59** | 1.0 | TC02 — Adição de produto com quantidade inicial customizada | enzo coelho | Passou |
| 18 | **QA-T60** | 1.0 | TC03 — Alteração e recálculo de quantidade de item no carrinho | enzo coelho | Passou |
| 19 | **QA-T11** | 1.0 | TC04 — Remoção de item do carrinho | enzo coelho | Passou |
| 20 | **QA-T12** | 1.0 | TC05 — Análise do Valor Limite da quantidade de produto | enzo coelho | Passou |
| 21 | **QA-T22** | 1.0 | TC07 — Persistência dos itens do carrinho pós-autenticação (Logout/Login) | enzo coelho | Passou |
| 22 | **QA-T10** | 1.0 | TC08 — Validação de agrupamento/soma | enzo coelho | Passou |
| 23 | **QA-T24** | 1.0 | TC01 — Finalizar pedido com Cartão de Crédito com sucesso | enzo coelho | Passou |
| 24 | **QA-T26** | 1.0 | TC03 — Tentativa de pagamento com Cartão de Crédito com dados inválidos | enzo coelho | Passou |
| 25 | **QA-T64** | 1.0 | TC04 — Finalizar pedido via Transferência Bancária (Bank Transfer) com sucesso | enzo coelho | Passou |
| 26 | **QA-T66** | 1.0 | TC06 — Tentativa de pagamento via Bank Transfer com dados inválidos | enzo coelho | Passou |
| 27 | **QA-T67** | 1.0 | TC07 — Tentativa de finalizar o checkout sem escolher forma de pagamento | enzo coelho | Passou |
| 28 | **QA-T68** | 1.0 | TC08 — Validação de campos obrigatórios no formulário de endereço | enzo coelho | Passou |
| 29 | **QA-T69** | 1.0 | TC09 — Validação de formatos inválidos no formulário de endereço (CEP e Número) | enzo coelho | Passou |
| 30 | **QA-T70** | 1.0 | TC10 — Checkout com carrinho de compras vazio | enzo coelho | Passou |
| 31 | **QA-T71** | 1.0 | TC11 — Acesso ao checkout para usuário não autenticado | enzo coelho | Passou |
| 32 | **QA-T93** | 1.0 | TC01 — Adicionar produto aos favoritos com sucesso | enzo coelho | Passou |
| 33 | **QA-T94** | 1.0 | TC02 — Remover produto dos favoritos | enzo coelho | Passou |
| 34 | **QA-T95** | 1.0 | TC03 — Persistência da lista de favoritos após logout e login | enzo coelho | Passou |
| 35 | **QA-T96** | 1.0 | TC04 — Adicionar múltiplos produtos aos favoritos | enzo coelho | Passou |
| 36 | **QA-T97** | 1.0 | TC05 — Ver lista de favoritos vazia | enzo coelho | Passou |
| 37 | **QA-T98** | 1.0 | TC06 — Impedir alteração indevida de estado e duplicidade para produto já favoritado | enzo coelho | Passou |
| 38 | **QA-T99** | 1.0 | TC07 — Bloqueio de favoritamento para usuário não autenticado (Negativo) | enzo coelho | Passou |
| 39 | **QA-T85** | 1.0 | TC01 — Ordenação e Filtro Combinado de Produtos | enzo coelho | Passou |
| 40 | **QA-T86** | 1.0 | TC02 — Busca por produto inexistente no catálogo | enzo coelho | Passou |
| 41 | **QA-T87** | 1.0 | TC03 — Tratamento de Caracteres Especiais na Busca (Segurança) | enzo coelho | Passou |
| 42 | **QA-T88** | 1.0 | TC04 — Restauração do Catálogo via Limpeza de Filtros | enzo coelho | Passou |
| 43 | **QA-T184** | 1.0 | TC05 — Filtragem por Categorias | enzo coelho | Passou |
| 44 | **QA-T106** | 1.0 | TC01 — Alterar dados básicos do perfil com sucesso | enzo coelho | Passou |
| 45 | **QA-T107** | 1.0 | TC02 — Alterar senha do usuário com sucesso | enzo coelho | Passou |
| 46 | **QA-T108** | 1.0 | TC03 — Tentativa de salvar dados básicos do perfil em branco | enzo coelho | Passou |
| 47 | **QA-T109** | 1.0 | TC04 — Tentativa de alterar a senha para uma senha fraca | enzo coelho | Passou |
| 48 | **QA-T110** | 1.0 | TC05 — Tentativa de alterar a senha para a mesma senha atual | enzo coelho | Passou |
| 49 | **QA-T100** | 1.0 | TC01 — Enviar mensagem de contato com sucesso | enzo coelho | Passou |
| 50 | **QA-T101** | 1.0 | TC02 — Bloqueio de envio com Assunto e Mensagem vazios | enzo coelho | Passou |
| 51 | **QA-T105** | 1.0 | TC03 — Rejeição de anexo em formato inválido | enzo coelho | Passou |
| 52 | **QA-T182** | 1.0 | TC06 — Rejeição de arquivo .txt acima do limite de tamanho | enzo coelho | Passou |

---

## 2. Casos com Status: FAIL (Falhou — 7 Casos)

| ID | Chave | Versão | Nome do Caso de Teste | Atribuído a | Status |
| :---: | :---: | :---: | :--- | :---: | :---: |
| 1 | **QA-T187** | 1.0 | TC07 — Validação de limite mínimo de caracteres no campo Password | enzo coelho | Falhou |
| 2 | **QA-T186** | 1.0 | TC06 — Validação de bloqueio de cadastro ao utilizar senha com nível insuficiente | enzo coelho | Falhou |
| 3 | **QA-T185** | 1.0 | TC06 — Análise do Valor Limite da quantidade de produto já dentro do carrinho | enzo coelho | Falhou |
| 4 | **QA-T4** | 1.0 | TC04 — Validação de formato de campos (E-mail, Data, Telefone e CEP) | enzo coelho | Falhou |
| 5 | **QA-T5** | 1.0 | TC05 — Validação de bloqueio de cadastro ao utilizar senha com nível fraco | enzo coelho | Falhou |
| 6 | **QA-T63** | 1.0 | TC02 — Tentativa de pagamento com Cartão de Crédito com campos vazios | enzo coelho | Falhou |
| 7 | **QA-T65** | 1.0 | TC05 — Tentativa de pagamento via Bank Transfer com campos vazios | enzo coelho | Falhou |