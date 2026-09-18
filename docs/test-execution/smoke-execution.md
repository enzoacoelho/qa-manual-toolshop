# Execução: Smoke Test (Testes de Fumaça)

**Ciclo:** Ciclo 1 - Smoke Test (QA-R5)
**Data de execução:** 01/09/2026
**Build/Versão testada:** 1.0
**Ambiente:** practicesoftwaretesting.com / (produção/demo pública)
**Executor:** Enzo Coelho
**Resultado geral:** ✅ 5/5 passaram — Build aprovado

---

| ID | Componente/Tela | Nome do Teste | Status | Bug Vinculado |
|---|---|---|---|---|
| **QA-LOG-01** | Login | Login com credenciais válidas com sucesso | ✅ Passou | — |
| **QA-CAD-01** | Cadastro | Cadastro válido com sucesso | ✅ Passou | — |
| **QA-CAR-01** | Carrinho | Adição de produtos ao carrinho | ✅ Passou | — |
| **QA-CKT-01** | Checkout | Finalizar pedido com Cartão de Crédito com sucesso | ✅ Passou | — |
| **QA-LOG-12** | Login | Encerramento de sessão (Logout) com sucesso | ✅ Passou | — |

---

## Observações
Todos os casos críticos do fluxo principal (cadastro → login → adicionar ao carrinho → pagamento → logout) passaram sem desvios. Nenhum defeito identificado nesta rodada. Build liberado para prosseguir para os ciclos de Regressão High e Full.