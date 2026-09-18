# Execução: Regressão — Full (Completo)

**Ciclo:** Ciclo 3 - Regressão Completa (QA-R7)
**Data de execução:** 01/09/2026
**Build/Versão testada:** 1.0
**Ambiente:** practicesoftwaretesting.com / (produção/demo pública)
**Executor:** Enzo Coelho
**Resultado geral:** ⚠️ 52/59 passaram, 7 falharam — Build **não aprovado** para produção

---

| ID | Componente/Tela | Nome do Teste | Status | Bug Vinculado |
|---|---|---|---|---|
| QA-LOG-01 | Login | Login com credenciais válidas com sucesso | ✅ Passou | — |
| QA-LOG-02 | Login | Login com campos vazios | ✅ Passou | — |
| QA-LOG-03 | Login | Login com campos preenchidos apenas com espaços colados | ✅ Passou | — |
| QA-LOG-05 | Login | Login com espaços antes/depois de credenciais válidas | ✅ Passou | — |
| QA-LOG-06 | Login | Login com senha incorreta | ✅ Passou | — |
| QA-LOG-07 | Login | Login com e-mail não cadastrado | ✅ Passou | — |
| QA-LOG-08 | Login | Login com e-mail em formato inválido | ✅ Passou | — |
| QA-LOG-09 | Login | Acessar link "Cadastre-se" a partir do login | ✅ Passou | — |
| QA-LOG-10 | Login | Acessar link "Esqueceu a senha" a partir do login | ✅ Passou | — |
| QA-LOG-11 | Login | Ícone de mostrar/esconder senha | ✅ Passou | — |
| QA-LOG-12 | Login | Encerramento de sessão (Logout) com sucesso | ✅ Passou | — |
| QA-CAD-01 | Cadastro | Cadastro válido com sucesso | ✅ Passou | — |
| QA-CAD-02 | Cadastro | Cadastro com e-mail já existente | ✅ Passou | — |
| QA-CAD-03 | Cadastro | Validação de campos obrigatórios vazios ou contendo apenas espaços | ✅ Passou | — |
| QA-CAD-04 | Cadastro | Validação de formato de campos (E-mail, Data, Telefone e CEP) | ❌ Falhou | [BUG-CAD-04](../bug-reports/cadastro/BUG-CAD-04.md) |
| QA-CAD-05 | Cadastro | Validação de bloqueio de cadastro ao utilizar senha com nível de força Weak | ❌ Falhou | [BUG-CAD-05](../bug-reports/cadastro/BUG-CAD-05.md) |
| QA-CAD-06 | Cadastro | Validação de bloqueio de cadastro ao utilizar senha com nível de força Moderate | ❌ Falhou | [BUG-CAD-06](../bug-reports/cadastro/BUG-CAD-06.md) |
| QA-CAD-07 | Cadastro | Validação de limite mínimo de caracteres no campo Password | ❌ Falhou | [BUG-CAD-07](../bug-reports/cadastro/BUG-CAD-07.md) |
| QA-FAV-01 | Favoritos | Adicionar produto aos favoritos com sucesso | ✅ Passou | — |
| QA-FAV-02 | Favoritos | Remover produto dos favoritos | ✅ Passou | — |
| QA-FAV-03 | Favoritos | Persistência da lista de favoritos após logout e login | ✅ Passou | — |
| QA-FAV-04 | Favoritos | Adicionar múltiplos produtos aos favoritos | ✅ Passou | — |
| QA-FAV-05 | Favoritos | Ver lista de favoritos vazia | ✅ Passou | — |
| QA-FAV-06 | Favoritos | Impedir alteração indevida de estado e duplicidade para produto já favoritado | ✅ Passou | — |
| QA-FAV-07 | Favoritos | Bloqueio de favoritamento para usuário não autenticado (Negativo) | ✅ Passou | — |
| QA-CON-01 | Contato | Enviar mensagem de contato com sucesso | ✅ Passou | — |
| QA-CON-02 | Contato | Bloqueio de envio com Assunto e Mensagem vazios | ✅ Passou | — |
| QA-CON-03 | Contato | Rejeição de anexo em formato inválido | ✅ Passou | — |
| QA-CON-04 | Contato | Rejeição de arquivo .txt acima do limite de tamanho | ✅ Passou | — |
| QA-CAR-01 | Carrinho | Adição de produtos ao carrinho | ✅ Passou | — |
| QA-CAR-02 | Carrinho | Adição de produto com quantidade inicial customizada | ✅ Passou | — |
| QA-CAR-03 | Carrinho | Alteração e recálculo de quantidade de item no carrinho | ✅ Passou | — |
| QA-CAR-04 | Carrinho | Remoção de item do carrinho | ✅ Passou | — |
| QA-CAR-05 | Carrinho | Análise do Valor Limite da quantidade de produto (Página do Produto) | ✅ Passou | — |
| QA-CAR-06 | Carrinho | Análise do Valor Limite da quantidade de produto já dentro do carrinho | ❌ Falhou | [BUG-CAR-06](../bug-reports/carrinho/BUG-CAR-06.md) |
| QA-CAR-07 | Carrinho | Persistência dos itens do carrinho pós-autenticação (Logout/Login) | ✅ Passou | — |
| QA-CAR-08 | Carrinho | Validação de agrupamento/soma de itens no carrinho | ✅ Passou | — |
| QA-CKT-01 | Checkout | Finalizar pedido com Cartão de Crédito com sucesso | ✅ Passou | — |
| QA-CKT-02 | Checkout | Tentativa de pagamento com Cartão de Crédito com campos vazios | ❌ Falhou | [BUG-CKT-02](../bug-reports/checkout/BUG-CKT-02.md) |
| QA-CKT-03 | Checkout | Tentativa de pagamento com Cartão de Crédito com dados inválidos | ✅ Passou | — |
| QA-CKT-04 | Checkout | Finalizar pedido via Transferência Bancária (Bank Transfer) com sucesso | ✅ Passou | — |
| QA-CKT-05 | Checkout | Tentativa de pagamento via Bank Transfer com campos vazios | ❌ Falhou | [BUG-CKT-05](../bug-reports/checkout/BUG-CKT-05.md) |
| QA-CKT-06 | Checkout | Tentativa de pagamento via Bank Transfer com dados inválidos | ✅ Passou | — |
| QA-CKT-07 | Checkout | Tentativa de finalizar o checkout sem escolher forma de pagamento | ✅ Passou | — |
| QA-CKT-08 | Checkout | Validação de campos obrigatórios no formulário de endereço | ✅ Passou | — |
| QA-CKT-09 | Checkout | Validação de formatos inválidos no formulário de endereço (CEP e Número da Casa) | ✅ Passou | — |
| QA-CKT-10 | Checkout | Checkout com carrinho de compras vazio | ✅ Passou | — |
| QA-CKT-11 | Checkout | Acesso ao checkout para usuário não autenticado | ✅ Passou | — |
| QA-FIL-01 | Busca e Filtro | Ordenação e Filtro Combinado de Produtos | ✅ Passou | — |
| QA-FIL-02 | Busca e Filtro | Busca por produto inexistente no catálogo | ✅ Passou | — |
| QA-FIL-03 | Busca e Filtro | Tratamento de Caracteres Especiais na Busca (Segurança) | ✅ Passou | — |
| QA-FIL-04 | Busca e Filtro | Restauração do Catálogo via Limpeza de Filtros | ✅ Passou | — |
| QA-FIL-05 | Busca e Filtro | Filtragem por Categorias | ✅ Passou | — |
| QA-USER-01 | User Profile | Alterar dados básicos do perfil com sucesso | ✅ Passou | — |
| QA-USER-02 | User Profile | Alterar senha do usuário com sucesso | ✅ Passou | — |
| QA-USER-03 | User Profile | Tentativa de salvar dados básicos do perfil em branco | ✅ Passou | — |
| QA-USER-04 | User Profile | Tentativa de alterar a senha para uma senha fraca | ✅ Passou | — |
| QA-USER-05 | User Profile | Tentativa de alterar a senha para a mesma senha atual | ✅ Passou | — |

---

## Observações
Volume concentrado de falhas em **validações de formulário, mensagens de erro e feedback visual (UX)** — o sistema apresenta inconsistências entre o comportamento da interface (UI) e as regras do backend:

- **Validações de Cadastro e Políticas de Senha** (QA-CAD-04, QA-CAD-05, QA-CAD-06, QA-CAD-07): o sistema falha ao validar datas futuras no campo de data de nascimento, exibe medidores de força de senha estáticos/inconsistentes e dispara mensagens de erro incorretas ou contraditórias (conflito entre o mínimo de 6, 7 ou 8 caracteres e falsos alertas de "caracteres inválidos").
- **Regras de Negócio do Carrinho** (QA-CAR-06): a manipulação de limites de quantidade exibe feedback visual trocado, emitindo um toast de sucesso ("Product quantity updated") mesmo ao corrigir valores inválidos, além de mensagens duplicadas/contraditórias acima de 99, como por exemplo alerta de erro e sucesso ao mesmotempo.
- **Validações de Pagamento e Checkout** (QA-CKT-02, QA-CKT-05): o formulário de Cartão de Crédito omite validações visuais individuais nos inputs e retorna um erro genérico ("Unknown error"), enquanto o fluxo de Transferência Bancária desabilita o botão de confirmação sem fornecer nenhum feedback visual de orientação ao usuário sobre os campos em branco.