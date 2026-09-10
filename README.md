# Manual QA Testing Portfolio – Practice Software Testing

Este repositório apresenta um projeto prático de QA manual criado para demonstrar habilidades em testes funcionais, gerenciamento de testes e rastreamento de defeitos utilizando Jira e Zephyr Scale.
O projeto cobre o design de casos de teste, ciclos de execução e relatórios detalhados de bugs.

---

## 🎯 Escopo do Projeto

Implementação de processos de garantia de qualidade em ambiente de homologação, abrangendo:
* Validação funcional de regras de negócio e fluxos end-to-end.
* Projeto de cenários de teste cobrindo caminhos críticos, cenários negativos e análise de valores limites.
* Mapeamento, execução e rastreamento de ciclos de teste via Zephyr Scale.

---

## 🧪 Aplicação Alvo

* **Sistema:** Practice Software Testing (Tool Shop)
* **URL:** [https://practicesoftwaretesting.com/](https://practicesoftwaretesting.com/)

---

## 🔍 Módulos Validados

* **Autenticação e Gestão de Contas:** Restrições de senha, validação de inputs e tratamento de erros de cadastro.
* **Catálogo e Busca:** Filtros de pesquisa, paginação e listagem de produtos.
* **Carrinho e Checkout:** Regras de limite de itens, validações de formulário e fluxos de pagamento (Cartão de Crédito e Transferência Bancária).
* **Suporte e Perfil:** Formulários de contato e atualização de dados cadastrais.

---

## 🛠 Stack de Ferramentas

* **Jira Cloud:** Gestão de apontamentos e ciclo de vida de bugs.
* **Zephyr Scale:** Organização de suítes de teste, planos de execução e métricas de cobertura.
* **Git / Markdown:** Versionamento e padronização da documentação técnica.

---

## 📊 Métricas de Execução (Zephyr Scale)

A execução integral da suíte planejada registrou os seguintes indicadores:

![Resultados de Test Execution](../docs/screenshots/zephyr-report-summary.png)

* **Casos de Teste Executados:** 59
* **Sucesso (Pass):** 52
* **Falhas (Fail):** 7
* **Defeitos Mapeados:** 7 relatórios técnicos de bugs com evidências visuais e passos de reprodução.

---

## 📂 Estrutura do Repositório

```text
docs/
├── bugs/           # Relatórios de defeitos estruturados em Markdown
├── screenshots/    # Evidências visuais de execução e falhas
├── test-cases/     # Cenários e casos de teste documentados por módulo
└── test-cycles/    # Escopos de execução (Smoke, Alto Risco e Regressão)