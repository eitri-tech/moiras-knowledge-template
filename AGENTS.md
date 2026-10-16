# AGENTS.md

Instruções para agentes (as Moiras e qualquer outro) que escrevem neste repositório de knowledge.

- Cada escritor só escreve na sua pasta: `moiras-index` em `glossary/`; as Moiras em `criteria/` (com aprovação de quem está triando) e em `learnings/`.
- `learnings/` é só de acréscimo: nunca apague nem reescreva um registro. A única edição permitida é atualizar `result` e a observação de uma solução.
- Um arquivo por registro, nomeado pelo `id` do frontmatter (ex.: `learnings/solutions/PROJ-123-1.md`).
- Antes de criar um registro, procure registros parecidos. Se dois critérios conflitarem, una os dois num critério novo, regenerado, e substitua os antigos no mesmo PR.
- Nada de cópia de código: no máximo um trecho de até 20 linhas por registro, sempre com referência (repositório, caminho, commit).
- Nunca grave segredos, tokens, conteúdo de `.env`, dados pessoais ou texto bruto de issue e de conversa.
- Ajustes de auditoria (`moiras-audit`) seguem as mesmas regras: só `result` e a observação mudam num aprendizado, e um critério muda por regeneração com `replaces`, com `approved_by` de quem auditou. O glossário não é editado à mão.
- Mudanças chegam por PR, abertos pelo `moiras-publish` num branch `moiras/publish-<id>`. Ninguém faz push direto na `main`.
- Todo registro precisa passar em `scripts/knowledge.ts check` do plugin: campos completos, sem modelo por preencher, sem segredos nem caminhos pessoais, e sem trecho de código acima de 20 linhas ou sem referência.
- Siga os modelos em `_templates/`.
