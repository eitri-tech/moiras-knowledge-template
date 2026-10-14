---
id: PROJ-123-1
tipo: solucao
issue: PROJ-123
repositorios: [acme-shop-checkout]
componente: checkout
categoria: bug
confianca: 70
resultado: pendente | resolveu | nao-resolveu
observacao:
escolhida_em: AAAA-MM-DD
referencias:
  - acme-shop-checkout/src/views/checkout/Cart.tsx@<commit>
---

# Manter o orderFormId na troca de seller

**Problema:** o carrinho é recriado quando o usuário troca de seller.

**Causa provável:** o orderForm antigo é descartado em vez de atualizado.

**Solução:** reaproveitar o `orderFormId` ao trocar de seller.

**Alternativas descartadas:** recriar o carrinho e reaplicar os itens (45%).
