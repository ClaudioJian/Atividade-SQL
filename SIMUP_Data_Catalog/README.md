# SIMUP · Data Catalog

Catálogo técnico e documentação de governança do banco de dados do Sistema Inteligente de Monitoramento Urbano Participativo.

## Como executar

1. Extraia a pasta `SIMUP_Data_Catalog`.
2. Abra `index.html` em um navegador ou publique a pasta em um servidor estático (por exemplo, GitHub Pages).
3. Para melhor compatibilidade com os recursos do navegador, prefira abrir por um servidor local/HTTPS.

## Downloads dos artefatos

No menu lateral, abra **Modelo DER**, **Script SQL** ou **Requisitos**. O botão principal no cabeçalho de cada janela baixa diretamente o respectivo arquivo:

- **Modelo DER:** imagem PNG; a barra da janela também oferece o PDF original.
- **Script SQL:** arquivo `.sql` completo.
- **Requisitos:** documento PDF.

Os links apontam para arquivos dentro de `assets/` e usam o atributo de download do navegador. Se a política do navegador ou do servidor bloquear downloads, abra o link do artefato em uma nova aba e use a opção de salvar do próprio navegador.

## Conteúdo

- `index.html`: estrutura da aplicação.
- `style.css`: estilos responsivos.
- `script.js`: dados do catálogo, filtros, modais, pré-visualização SQL e metadados de governança.
- `assets/atividade_sql_simup.sql`: DDL MySQL fornecido.
- `assets/SIMUP_modelo_mermaid.pdf`: modelo DER original em PDF.
- `assets/SIMUP_modelo_mermaid_preview.png`: imagem do DER usada na pré-visualização e no download.
- `assets/SIMUP_requisitos.pdf`: especificação de requisitos original.

## Observação de governança

Classificações LGPD e linhagem são avaliações preliminares. As permissões RBAC exibidas são recomendações e não estão implementadas no DDL.
