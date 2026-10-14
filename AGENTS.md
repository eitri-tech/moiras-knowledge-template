# AGENTS.md

Instruções para agentes (as Moiras e qualquer outro) que escrevem neste repositório de knowledge.

- Cada escritor só escreve na sua pasta: `moiras-index` em `glossary/`; as Moiras em `criteria/` (com aprovação de quem está triando) e em `learnings/`.
- `learnings/` é só de acréscimo: nunca apague nem reescreva um registro. A única edição permitida é atualizar `resultado` e `observacao` de uma solução.
- Um arquivo por registro, nomeado pelo `id` do frontmatter (ex.: `learnings/solutions/PROJ-123-1.md`).
- Antes de criar um registro, procure registros parecidos. Se dois critérios conflitarem, una os dois num critério novo, regenerado, e substitua os antigos no mesmo PR.
- Nada de cópia de código: no máximo um trecho de até 20 linhas por registro, sempre com referência (repositório, caminho, commit).
- Nunca grave segredos, tokens, conteúdo de `.env`, dados pessoais ou texto bruto de issue e de conversa.
- Mudanças chegam por PR, abertos pelo `moiras-publish`. Ninguém faz push direto na `main`.
- Siga os modelos em `_templates/`.
