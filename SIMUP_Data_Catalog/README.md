# SIMUP — Data Catalog

Site estático de documentação do banco de dados do Sistema Inteligente de Monitoramento Urbano Participativo.

## Executar localmente

Como o site carrega o SQL por `fetch`, execute-o por um servidor HTTP local (não abra `index.html` diretamente via `file://`). Exemplos:

- VS Code: extensão Live Server, botão **Go Live**.
- Python: `python -m http.server 8000` e acesse `http://localhost:8000`.

## Publicar no GitHub Pages

1. Envie o conteúdo desta pasta para a raiz de um repositório GitHub.
2. Acesse **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**.
4. Selecione a branch principal e a pasta `/ (root)`.
5. Salve e aguarde a publicação.

## Arquivos

- `index.html`: estrutura e conteúdo da interface.
- `style.css`: identidade visual responsiva.
- `script.js`: catálogo das sete tabelas, busca, relacionamentos e modais.
- `assets/atividade_sql_simup.sql`: script SQL original extraído do ZIP.
- `assets/SIMUP_modelo_mermaid.pdf`: DER original.
- `assets/SIMUP_requisitos.pdf`: documento de requisitos original.

## Critério de fidelidade

O dicionário descreve a estrutura efetivamente presente no DDL. Divergências com os requisitos são expostas na seção **Auditoria documental**, sem alterar silenciosamente o modelo físico.
