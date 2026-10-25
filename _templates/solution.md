---
id: PROJ-123-1
type: solution
issue: PROJ-123
created_at: AAAA-MM-DD
chosen_by: <pseudônimo não identificável escolhido pela pessoa, no formato <prefixo>-<id> (ex. reviewer-01); nunca nome real, e-mail ou identificador de conta>
agency:
repositories: [acme-shop-checkout]
component: checkout
category: bug
confidence: 70
reference_url: https://github.com/<org>/acme-shop-checkout/pull/12
result: pending | resolved | not-resolved
---

# Manter o orderFormId na troca de seller

**Problema:** o carrinho é recriado quando o usuário troca de seller.

**Causa provável:** o orderForm antigo é descartado em vez de atualizado.

**Solução:** reaproveitar o `orderFormId` ao trocar de seller.

**Riscos:** itens de sellers diferentes no mesmo carrinho.

**Alternativas descartadas:** recriar o carrinho e reaplicar os itens (45).

**Fontes:** `acme-shop-checkout/src/views/checkout/Cart.tsx@<commit>`

**Observação:**
