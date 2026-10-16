# Moiras: template de knowledge

Template público para criar um repositório de knowledge do plugin **Moiras**, que faz triagem de issues do Jira. O plugin é genérico; o que é específico de um time, de um grupo de projetos ou de um projeto mora num repositório criado a partir deste template.

> Crie o seu com **Use this template** e deixe-o **privado**: ele vai guardar nomes de repositórios, clientes e o que o time aprendeu.

## Para que serve

Cada repositório de knowledge tem um escopo. Exemplos:

| Escopo | Exemplo | O que guarda |
|---|---|---|
| Projeto | `knowledge-acme-shop` | Glossário dos repositórios de um projeto e o que se aprendeu nele |
| Grupo de projetos | `knowledge-acme-group` | O que vale para todos os projetos de um mesmo tipo (ex.: todos feitos na mesma plataforma): problemas recorrentes, critérios, soluções |
| Global | `knowledge-time` | Critérios e decisões que valem para tudo |

As Moiras sempre trabalham com o knowledge local. Os repositórios de knowledge servem para sincronizar e mesclar o que cada pessoa aprendeu; usar um deles é opcional.

## Estrutura

| Pasta | Conteúdo | Quem escreve | Regra |
|---|---|---|---|
| `glossary/` | Glossário de repositórios: um arquivo por repositório, com localização e metadados | `moiras-index` | Derivado do código; pode ser regenerado a qualquer momento |
| `criteria/` | Regras de classificação e de decisão | as Moiras, com o "sim" de quem está triando ou audita (`moiras-audit`) | Um arquivo por critério; critérios conflitantes são unidos num só, regenerado |
| `learnings/solutions/` | Soluções escolhidas e o resultado delas | Átropos | Só acréscimo; um arquivo por registro |
| `learnings/patterns/` | Padrões de problema recorrentes | Láquesis / Átropos | Só acréscimo; um arquivo por registro |
| `learnings/decisions/` | Decisões que valem para casos futuros | as Moiras, a partir de soluções que funcionaram | Só acréscimo; um arquivo por registro |
| `_templates/` | Modelo de cada tipo de arquivo | pessoas | Referência para quem escreve |

Os modelos (`_templates/`) usam nomes fictícios (`acme-shop-checkout`, `PROJ-123`). Apague as pastas `.gitkeep` à medida que os primeiros arquivos chegarem, se quiser.

## O que não entra num knowledge

- Cópia de código. As Moiras sempre olham o código real; aqui fica só onde ele está e o que se aprendeu com ele.
- Trechos de código maiores que 20 linhas, ou sem referência (repositório, caminho, commit).
- Segredos, tokens, `.env`, dados pessoais, texto bruto de issue ou de conversa.

## Fluxo

1. `moiras-sync` (opcional, sugerido): traz o que foi mergeado aqui para o clone local, só avançando-o (`git merge --ff-only`). Nunca envia.
2. As Moiras triam e aprendem localmente; `moiras-index` gera e atualiza o glossário a partir do código (com `sources_hash`) quando um repositório novo aparece ou muda.
3. `moiras-audit` (quando alguém for revisar): aponta registros velhos, pendentes ou conflitantes e aplica ajustes só com o "sim" de quem audita. Altera o knowledge local; para levar o ajuste para cá, siga para o passo 4.
4. `moiras-publish`: confere cada registro com `scripts/knowledge.ts check` (do plugin) e abre um PR aqui, num branch `moiras/publish-<id>`, com o que é novo. Nunca faz push direto na `main` e nunca faz merge sozinho.
