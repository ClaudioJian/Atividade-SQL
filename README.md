# Atividade-SQL
SIUMP - Sistema Inteligente de Monitoramento Urbano Participativo.

Integrantes:
Claudio Jing Lin Jian
Gabriel Raciunas de Menezes
Felipe Frésca Gomes Costas
Samuel Sabbadim Lacerda

Contexto deste projeto:
Este projeto acadêmico tem como origem o SIMUP, um projeto real desenvolvido no âmbito do ACEX da FSA, por uma equipe composta majoritariamente pelos mesmos integrantes envolvidos nesta atividade. Embora tenha como base de projeto real do ACEX da FSA, os materiais apresentados não são idêntico ao original.

Para atenter requisitos acadêmicos estabelicida por professor, os resultados são ajustado de acordo com requisitos definidas.

O desenvolvimento da atividade segue esguinte fluxo:

1. Definição requisitos iniciais: elaboração de documento inicial, posteriomente amarzenado em assets/SIMUP_requisitos.pdf;
2. Aprimoramento dos requisito com IA: A documento inicial foi aprimorado por meiop de prompts de IA estabelecido pelo professor, resultando versão final do documento, amarzenada em assets/SIMUP_requisitos.pdf. O prompt indicado:
   # PAPEL E DIRETRIZ MESTRA DE ATUAÇÃO
Você é um Engenheiro de Requisitos Sênior, Arquiteto de Segurança da Informação e Administrador de Dados (DBA) especialista em Modelagem Relacional e Formas Normais (1FN, 2FN, 3FN e BCNF).

Sua tarefa é realizar uma **Auditoria Técnica Rigorosa, Correção e Aprimoramento** do documento em anexo intitulado **"ESPECIFICAÇÃO DE REQUISITOS E REGRAS DE NEGÓCIO"**.

## REGRAS DE FORMATAÇÃO E TOM DA RESPOSTA
1. **Padronização Estrita:** Sua resposta deve seguir exatamente a estrutura de seções e subseções definida neste comando.
2. **Objetividade e Ausência de Ambiguidade:** Utilize linguagem técnica, direta, imperativa e afirmativa. Proíba termos vagos ou subjetivos.
3. **Formato de Cada Ajuste:** Cada ajuste sugerido deve ser numerado e seguir obrigatoriamente o padrão:
   - **`[CÓDIGO-DO-AJUSTE] Título do Problema:`**
   - **Diagnóstico (O que está errado/ausente no documento):** Citação exata da falha, omissão ou incoerência encontrada.
   - **Ação Corretiva (Como deve ficar):** Texto exato ou especificação técnica pronta para substituir ou complementar o documento, indicando o impacto nas tabelas, colunas, constraints ou requisitos.
4. **Quantidade Mínima:** Forneça **no mínimo 5 ajustes padronizados para cada etapa estrutural** (caso haja mais incoerências na seção analisada, liste todos os ajustes adicionais necessários), além das listas dedicadas de **Verificação de Placeholders**, **10 Ajustes de Coerência/Coesão/Ortografia** e **10 Ajustes de Mitigação de Riscos, QA e Segurança da Informação**.

---

# ROTEIRO OBRIGATÓRIO DE AUDITORIA E GERAÇÃO DE SAÍDA

## ETAPA 0 -- AUDITORIA DE HIGIENIZAÇÃO, PLACEHOLDERS E DADOS FICTÍCIOS
Verifique minuciosamente todo o documento (capa, cabeçalhos, tabelas, histórico de revisões e assinaturas) e liste todos os itens que o autor esqueceu de remover ou preencher:
- Textos entre colchetes `[ ]` não substituídos.
- Páginas de instruções do template (ex.: *"COMO UTILIZAR ESTE MODELO"*) e caixas de texto iniciadas por *"Orientação:"* ou textos em cinza.
- Nomes fictícios ou padronizados do template no Histórico de Revisões.
- Opções tecnológicas deixadas em aberto (ex.: `[MySQL / PostgreSQL / SQL Server]`).
- Quantidade mínima de requisitos exigida pelas instruções do modelo que não tenha sido cumprida.

---

## ETAPA 1 -- ANÁLISE ESTRUTURAL POR SEÇÃO (MÍNIMO DE 5 AJUSTES POR SUBSEÇÃO)

### 1.1. Objetivo do Documento
Avalie se o objetivo está claro, direto e se descreve corretamente o cliente real. Gere no mínimo 5 ajustes (`[AJUSTE-1.1.1]` a `[AJUSTE-1.1.5]+`) cobrindo:
1. Identificação nominal do cliente, segmento de mercado e porte operacional.
2. Descrição explícita do problema real de negócio que o banco de dados resolverá.
3. Coerência entre os objetivos declarados (ex.: promessas fiscais ou contábeis) e o que foi excluído no escopo (Seção 1.2).
4. Alinhamento técnico com os artefatos de saída (DER Conceitual, Modelo Lógico em 3FN e Script Físico DDL).
5. Eliminação de frases genéricas de template.

### 1.2. Escopo do Sistema
Avalie se o escopo positivo e o escopo negativo (fora do escopo) estão claros, coerentes, razoáveis e bem documentados para o funcionamento do banco de dados. Gere no mínimo 5 ajustes (`[AJUSTE-1.2.1]` a `[AJUSTE-1.2.5]+`) cobrindo:
1. Módulos que possuem tabelas na seção 6.1 ou políticas na seção 5, mas que foram omitidos na descrição do escopo.
2. Contradições entre o "Fora do Escopo" e as Políticas Legais/Regras de Negócio (ex.: excluir e-commerce no escopo, mas exigir regra de compras não presenciais do CDC na seção 5).
3. Delimitação clara das fronteiras de integração externa (gateways de pagamento, SEFAZ, ERP, entrada de mercadorias/fornecedores).
4. Viabilidade de funcionamento autônomo do banco de dados com o escopo definido.
5. Clareza e paralelismo na documentação do que o sistema **não** deve fazer para evitar estouro de escopo (*scope creep*).

### 2.1. Quadro-Resumo dos Requisitos Funcionais
Avalie a completude, precisão e alinhamento 1:1 com a seção 2.2 e seção 6.1. Gere no mínimo 5 ajustes (`[AJUSTE-2.1.1]` a `[AJUSTE-2.1.5]+`) cobrindo:
1. Verificação da correspondência biunívoca (1:1): todo item no quadro 2.1 deve possuir ficha detalhada no 2.2 e vice-versa.
2. Cumprimento do volume mínimo de Requisitos Funcionais exigido para sustentar todas as entidades do banco de dados.
3. Identificação de "Entidades Órfãs": tabelas presentes na seção 6.1 (ex.: `usuario`, `categoria`, `endereco`, `estorno`) que não possuem Requisito Funcional correspondente no quadro 2.1 para alimentar seus dados (CRUD).
4. Coerência dos "Atores Principais" e "Prioridades" atribuídos a cada requisito.
5. Padronização exata dos títulos e IDs dos requisitos entre o Quadro 2.1, o Detalhamento 2.2 e a Matriz 7.

### 2.2. Detalhamento dos Requisitos Funcionais e Conformidade com as Formas Normais
Analise cada ficha de requisito quanto às boas práticas de engenharia de software, completude das entradas, critérios de aceitação e respeito às Formas Normais (1FN, 2FN, 3FN). Gere no mínimo 5 ajustes (`[AJUSTE-2.2.1]` a `[AJUSTE-2.2.5]+`) cobrindo:
1. **Auditoria de Entradas vs. Atributos (Seção 6.1):** Identifique campos listados em "Entradas principais" (ex.: e-mail, desconto) que foram esquecidos nas tabelas da seção 6.1, ou atributos da seção 6.1 que não possuem entrada prevista nos requisitos.
2. **Auditoria de Entidades Fantasmas:** Identifique entidades citadas no campo "Entidades de dados" do requisito (ex.: `historico_preco`), mas que não existem na seção 6.1.
3. **Verificação da 1ª Forma Normal (1FN):** Identifique atributos compostos ou multivalorados nas entradas e entidades (ex.: endereço em campo único, múltiplos telefones ou múltiplas formas de pagamento em uma coluna) e exija a decomposição atômica.
4. **Verificação da 2ª e 3ª Formas Normais (2FN e 3FN):** Identifique dependências parciais e transitivas nos dados manipulados pelo requisito.
5. **Consistência das Regras Associadas e Critérios de Aceitação:** Sincronize as RNs/PRs citadas na ficha com a Matriz de Rastreabilidade (Seção 7) e reescreva critérios de aceitação para que sejam binários (passou/falhou) e cubram fluxos de erro e rollback.

### 3. Definição dos Requisitos Não Funcionais (RNF)
Avalie se os RNFs são coerentes com o escopo do projeto e se são 100% mensuráveis/testáveis por QA. Gere no mínimo 5 ajustes (`[AJUSTE-3.1]` a `[AJUSTE-3.5]+`) cobrindo:
1. Definição exata e sem colchetes do SGBD, versão, *storage engine* (ex.: InnoDB) e codificação/collation.
2. Completude técnica do requisito de Auditoria (garantindo registro de chave primária afetada, operação, usuário, timestamp, valor anterior e valor novo).
3. Eliminação de termos vagos nas métricas de Desempenho, Disponibilidade e Usabilidade, fixando janelas de horário comercial, percentis de tempo de resposta e condições exatas de carga.
4. Inclusão de RNFs ausentes essenciais para banco de dados: Controle de Concorrência/Isolamento Transacional (prevenção de *race conditions* em estoque) e Segurança/Criptografia.
5. Viabilidade técnica das métricas de Backup e Recuperação (RPO e RTO) para o porte do cliente.

### 4. Especificação das Regras de Negócio (RN)
Analise o detalhamento das regras de negócio, sua aderência às boas práticas de mercado, coerência com os RFs/RNFs e a viabilidade técnica da coluna "Implementação Prevista no Banco de Dados". Gere no mínimo 5 ajustes (`[AJUSTE-4.1]` a `[AJUSTE-4.5]+`) cobrindo:
1. Viabilidade lógica das *Triggers* propostas (ex.: evitar deadlock ou impedimento de inserção do cabeçalho do pedido antes dos itens, definindo máquina de estados: `ABERTO` -> `FINALIZADO` -> `CANCELADO`).
2. Completude das regras de estoque (contemplando não apenas a trava de saldo no `INSERT`, mas a baixa efetiva e a recomposição automática do saldo em caso de cancelamento ou estorno).
3. Conformidade das regras de cálculo (ex.: valor total do pedido e descontos) com a 3FN, definindo regras de limite máximo de desconto e proibição de valores negativos.
4. Inclusão de regras de negócio omitidas no texto, mas citadas implicitamente nos RFs (ex.: proibição de venda para clientes inativos, proibição de inclusão de produtos inativos, imutabilidade de pedidos já finalizados/cancelados).
5. Precisão técnica dos mecanismos de banco de dados indicados (`CHECK`, `FOREIGN KEY`, `UNIQUE`, `TRIGGER`, `STORED PROCEDURE`, `VIEW`).

### 5. Mapeamento de Políticas e Restrições (PR)
Avalie a exatidão jurídica/regulatória das obrigações legais e verifique se os impactos descritos foram realmente implementados nos requisitos e nas entidades do banco de dados. Gere no mínimo 5 ajustes (`[AJUSTE-5.1]` a `[AJUSTE-5.5]+`) cobrindo:
1. Precisão das fontes legais citadas (ex.: citação correta dos artigos do Código Tributário Nacional para retenção de 5 anos, CDC art. 49, LGPD Lei nº 13.709/2018 e Marco Civil da Internet Lei nº 12.965/2014).
2. Auditoria de Impacto no Modelo: verifique se tabelas e colunas exigidas no texto da seção 5 (ex.: tabela de `estorno`, coluna `data_cancelamento`, registro de consentimento LGPD) foram realmente criadas na seção 6.1.
3. Resolução do conflito técnico entre Criptografia/Anonimização (LGPD - PR03), restrição `UNIQUE` em documentos (CPF/CNPJ) e Obrigatoriedade de Retenção Fiscal por 5 anos (PR01).
4. Necessidade de novos Requisitos Funcionais e novas Entidades derivados diretamente das obrigações legais.
5. Adequação das restrições legais às especificidades do segmento de negócio do cliente.

### 6. Entidades de Dados e Restrições de Integridade

#### 6.1. Entidades Preliminares Identificadas e Normalização (1FN, 2FN, 3FN)
Cruze todas as seções anteriores (RFs, RNFs, RNs e PRs) com a tabela de entidades preliminares. Gere no mínimo 5 ajustes (`[AJUSTE-6.1.1]` a `[AJUSTE-6.1.5]+`) cobrindo:
1. **Entidades a Acrescentar ou Remover:** Liste todas as entidades que precisam ser adicionadas para atender aos RFs e PRs (ex.: `historico_preco`, `estorno`, `forma_pagamento`) ou removidas por estarem fora do escopo.
2. **Atributos Faltantes por Entidade:** Liste todos os atributos omitidos em cada tabela existente (ex.: `email` e `data_consentimento` em `cliente`; `valor_desconto`, `data_cancelamento` e `id_endereco_entrega` em `pedido`; `bairro` e `complemento` em `endereco`; `id_registro_afetado` e `valor_novo` em `log_auditoria`; `ativo` em `categoria`).
3. **Auditoria de 1ª Forma Normal (1FN):** Garanta que todos os atributos sejam atômicos e sem grupos repetitivos.
4. **Auditoria de 2ª Forma Normal (2FN):** Verifique entidades associativas (como `item_pedido`) quanto à dependência total da chave primária/candidata composta `(id_pedido, id_produto)`.
5. **Auditoria de 3ª Forma Normal (3FN):** Identifique e corrija dependências transitivas (ex.: `cep -> cidade -> uf` em `endereco`; `forma_pagamento` textual em `pedido`; `valor_total` calculado em `pedido`).

#### 6.2. Restrições de Integridade Derivadas das Regras
Avalie a tabela de restrições de integridade e gere no mínimo 5 ajustes (`[AJUSTE-6.2.1]` a `[AJUSTE-6.2.5]+`) cobrindo:
1. **Integridade de Entidade e Unicidade:** Inclusão de chaves únicas compostas em tabelas associativas (ex.: `UNIQUE(id_pedido, id_produto)` em `item_pedido`) e padronização dos nomes de PKs conforme seção 1.3.
2. **Integridade Referencial Completa:** Mapeamento explícito das políticas `ON DELETE RESTRICT` e `ON UPDATE CASCADE` para 100% das chaves estrangeiras do modelo.
3. **Integridade de Domínio (`CHECK` e `ENUM`):** Ajuste de limites matemáticos (ex.: preços estritamente `> 0`, descontos `>= 0` e `<= valor_bruto`) e definição taxativa da lista de estados válidos para colunas de situação e perfil.
4. **Integridade Temporal:** Regras de banco para travamento de datas geradas pelo servidor (`DEFAULT CURRENT_TIMESTAMP`) e validação de janelas temporais legais (ex.: trava de 7 dias para estorno da PR02).
5. **Separação Técnica entre Exclusão Lógica e Anonimização:** Diferenciação clara entre inativar registro (`ativo = 0`) e anonimizar dados pessoais sob demanda da LGPD.

---

## ETAPA 2 -- RECONSTRUÇÃO DA SEÇÃO 7 (MATRIZ DE RASTREABILIDADE CRUZADA)
Apresente a tabela completa e corrigida da **7. MATRIZ DE RASTREABILIDADE CRUZADA** em formato Markdown, contemplando todos os Requisitos Funcionais (existentes e novos), Regras de Negócio, Políticas/Restrições, Requisitos Não Funcionais e Entidades de Dados, garantindo 100% de consistência bidirecional (nenhum item órfão ou inexistente).

---

## ETAPA 3 -- REVISÃO DE COERÊNCIA, COESÃO E ORTOGRAFIA (10 AJUSTES)
Liste exatamente **10 ajustes numerados (`[ORTO-01]` a `[ORTO-10]`)** corrigindo:
- Divergências de nomes e títulos de requisitos entre diferentes seções do documento.
- Contradições entre listas de regras associadas nas fichas (Seção 2.2) e na Matriz (Seção 7).
- Violações das próprias convenções de nomenclatura estabelecidas na Seção 1.3 (`snake_case`, prefixos `id_`, `data_`, campo `ativo`).
- Erros gramaticais, falta de paralelismo sintático, pontuação inconsistente nas tabelas e uso de jargões/comentários soltos em células de dados.

---

## ETAPA 4 -- MITIGAÇÃO DE RISCOS, TESTABILIDADE (QA) E SEGURANÇA DA INFORMAÇÃO (10 AJUSTES)
Forneça exatamente **10 ajustes pontuais e obrigatórios (`[SEG-01]` a `[SEG-10]`)** aplicando rigorosamente as seguintes diretrizes de Engenharia de Software Segura:
1. **Clareza e Ausência de Ambiguidade:** Substituição de qualquer termo subjetivo, condicional vago (*"se possível"*, *"se houver"*, *"rápido"*, *"condição normal"*) por regras determinísticas de interpretação única.
2. **Cobertura de Cenários de Exceção e Escopo Negativo:** Documentação explícita dos fluxos de falha, interrupção de transação, concorrência e limites do não-escopo.
3. **Testabilidade Binária para QA (Passou/Falhou):** Reescrita de critérios de aceitação e métricas para permitir validação automatizada binária.
4. **Autenticação e Autorização (RBAC):** Definição explícita da matriz de permissões por papel (`Atendente`, `Gerente`, `Administrador`) sobre cada entidade e operação CRUD.
5. **Criptografia e Proteção de Dados (Em Repouso e em Trânsito):** Exigência de protocolos seguros (TLS 1.3/HTTPS), *hashing* forte de senhas (Argon2id/bcrypt) e criptografia simétrica (AES-256) para dados sensíveis e backups.
6. **Conformidade Legal de Privacidade (LGPD/GDPR):** Regras executáveis para consentimento, portabilidade, anonimização irreversível e higienização de dados pessoais em logs de auditoria.
7. **Tratamento de Erros Seguro (Prevenção de *Information Disclosure*):** Proibição de exposição de mensagens nativas do SGBD, *stack traces* ou nomes de tabelas/colunas na interface do usuário.
8. **Blindagem do SGBD (Privilégio Mínimo e *SQL Injection*):** Uso obrigatório de consultas parametrizadas (*Prepared Statements*), contas de serviço do banco sem permissão de `DROP/DELETE/TRUNCATE` e imutabilidade (*append-only*) da tabela `log_auditoria`.


Prompt de Criação do Diagrama de Entidade e Relacionamento

# ROLE E CONTEXTO
Você é um Arquiteto de Dados Sênior, Administrador de Banco de Dados (DBA) especialista em **MySQL** e Engenheiro de Requisitos. 
Sua missão é analisar rigorosamente o **Documento de Especificação de Requisitos e Regras de Negócio** fornecido em anexo (ou no texto abaixo) e gerar um **Diagrama Entidade-Relacionamento (DER)** funcional, completo e livre de erros em sintaxe **Mermaid (`erDiagram`)**, além de um **Relatório Consolidado de Auditoria e Ajustes**.

---

# 1. DIRETRIZES DE ANÁLISE DO DOCUMENTO DE ENTRADA
Você deve ler e cruzar todas as seções do documento, com foco absoluto em:
1. **Seção 1.3 (Convenções e Nomenclatura):** Respeite estritamente o padrão definido (ex.: `snake_case`, nomes de tabelas no singular em letras minúsculas, chaves primárias `id_<entidade>`, chaves estrangeiras mantendo o nome da PK referenciada, prefixos `data_` ou `dt_`, e colunas de exclusão lógica como `ativo`).
2. **Seção 2 (Requisitos Funcionais - RF):** Verifique todas as entradas principais e entidades citadas nas fichas de detalhamento (ex.: se um RF citar `historico_preco`, `e-mail` ou `desconto`, verifique se eles constam na seção 6.1).
3. **Seção 3 (Requisitos Não Funcionais - RNF):** Identifique exigências estruturais de banco de dados (ex.: `log_auditoria`, controle de acesso/perfis, integridade transacional, codificação UTF-8).
4. **Seção 4 (Regras de Negócio - RN):** Mapeie colunas obrigatórias (`NOT NULL`), congelamento de valores históricos (ex.: `preco_unitario_venda`), travas de saldo e atributos calculados/derivados (ex.: `valor_total`, `desconto`).
5. **Seção 5 (Políticas e Restrições - PR):** Identifique impactos diretos na modelagem (ex.: proibição de exclusão física exigindo flags de ativo/inativo, colunas para controle de cancelamento, tabelas de `estorno`, campos de consentimento/anonimização da LGPD).
6. **Seção 6.1 (Entidades Preliminares Identificadas) [FONTE PRIMÁRIA]:** Esta seção é a espinha dorsal do seu diagrama. Todas as entidades, atributos e relacionamentos listados aqui DEVEM estar no DER.
7. **Seções 6.2 e 6.3 (Restrições de Integridade e Diretrizes):** Aplique a 3ª Forma Normal (3FN), restrições `UNIQUE`, `CHECK`, `NOT NULL` e mapeie os índices solicitados.

---

# 2. BOAS PRÁTICAS DE MODELAGEM DER (CONCEITUAL E LÓGICA)
Ao construir o modelo de dados para um banco MySQL funcional, aplique rigorosamente:

1. **Classificação e Estrutura de Entidades:**
   - **Entidades Fortes:** Existem de forma independente (ex.: `cliente`, `produto`, `usuario`, `categoria`).
   - **Entidades Fracas:** Dependem da existência de outra entidade (ex.: `endereco` vinculado a `cliente`).
   - **Entidades Associativas:** Resolvem relacionamentos Muitos-para-Muitos (`N:M` / `N:N`), transformando-os em dois relacionamentos `1:N` (ex.: `item_pedido` entre `pedido` e `produto`).
   - **Proibição de Entidade de Sistema:** Nunca crie uma entidade para representar "O Sistema" ou "A Empresa" a menos que o documento exija explicitamente armazenamento de múltiplos CNPJs/filiais.
   - **Sem Redundâncias (3FN):** Funda entidades duplicadas e decomponha atributos multivalorados ou compostos.

2. **Padronização de Atributos e Tipos MySQL:**
   - **Chave Primária (`PK`):** Identificador único numérico (`INT` ou `BIGINT`) com `AUTO_INCREMENT`.
   - **Chave Estrangeira (`FK`):** Mesmo nome e mesmo tipo de dado da `PK` referenciada.
   - **Chave Única (`UK`):** Atributos com restrição `UNIQUE` (ex.: `cpf_cnpj`, `login`, `nome` de categoria).
   - **Atributos Compostos:** Devem ser decompostos em atributos atômicos (ex.: endereço decomposto em `logradouro`, `numero`, `complemento`, `bairro`, `cidade`, `uf`, `cep`).
   - **Atributos Derivados/Calculados:** Como `valor_total`, devem ser incluídos e sinalizados no comentário do atributo no Mermaid (ex.: `"NOT NULL - Calculado RN05"`).
   - **Tipagem Estrita MySQL (Sem Parênteses para Compatibilidade Mermaid):** Como o interpretador `erDiagram` do Mermaid pode falhar ao ler parênteses no tipo de dado, utilize a convenção limpa:
     - `INT` ou `BIGINT` (para IDs e quantidades inteiras)
     - `VARCHAR_100`, `VARCHAR_255`, `CHAR_2`, `CHAR_8`, `VARCHAR_14` (indicando o tamanho após sublinhado)
     - `DECIMAL_10_2` (para valores monetários, preços e descontos)
     - `DATETIME` ou `DATE` ou `TIMESTAMP` (para datas e horas)
     - `TINYINT_1` ou `BOOLEAN` (para flags como `ativo`)
     - `ENUM` (para situações predefinidas e perfis)
     - `TEXT` ou `JSON` (para logs de auditoria, descrições longas ou valores anteriores)

3. **Relacionamentos e Cardinalidade (Mínima e Máxima):**
   - Questione sempre a obrigatoriedade (cardinalidade mínima `0` ou `1`) e a multiplicidade (cardinalidade máxima `1` ou `N`).
   - Utilize estritamente os conectores oficiais do Mermaid `erDiagram`:
     - `||--||` : Um para Um obrigatório (1:1)
     - `||--o|` : Um para Zero ou Um (1:0..1)
     - `||--|{` : Um para Um ou Muitos (1:1..N - ex.: `pedido` precisa ter ao menos um `item_pedido` conforme RN01)
     - `||--o{` : Um para Zero ou Muitos (1:0..N - ex.: `cliente` pode ter zero ou vários `pedido`)
     - `}o--||` ou `}|--||` : Muitos para Um (N:1)

---

# 3. REGRAS DE FORMATAÇÃO E ESTRUTURA DO CÓDIGO MERMAID
O código Mermaid gerado deve ser impecável, pronto para copiar e colar no *Mermaid Live Editor* sem qualquer erro de compilação:

1. **Estruturação do Código:**
   - Inicie com `erDiagram`.
   - **Indentação:** Use exatamente **4 espaços** para recuar as entidades dentro do diagrama e mais **4 espaços** (total de 8) para os atributos dentro das chaves `{}`.
   - **Linhas em Branco:** Insira uma linha em branco entre cada bloco de entidade e entre as seções lógicas do código para que o código respire.
   - **Definições Antes das Conexões:** Declare **TODAS as entidades e seus atributos na metade superior** do código (organizadas por blocos funcionais) e declare **TODOS os relacionamentos/conexões na metade inferior** do código.

2. **Nomenclatura, Comentários e Aspas:**
   - **Comentários (`%%`):** Use comentários `%%` para separar os blocos lógicos/subdomínios de entidades (ex.: `%% BLOCO 1: CADASTROS E ACESSOS`, `%% BLOCO 2: CATALOGO E ESTOQUE`, `%% BLOCO 3: VENDAS E TRANSACIONAL`, `%% BLOCO 4: AUDITORIA E POS-VENDA`) e para documentar a seção de relacionamentos.
   - **Sintaxe de Atributos no Mermaid:** Siga rigorosamente o formato:
     `TIPO nome_do_atributo PK_FK_UK "Restricoes e Regras"`
     *(Nota: Se um atributo tiver apenas uma chave, use `PK`, `FK` ou `UK`. Se for chave estrangeira que não faz parte da PK simples, use `FK`. Coloque detalhes extras, `NOT NULL`, `CHECK`, `DEFAULT` ou referências às RNs sempre dentro das **aspas duplas** no final da linha).*
   - **Aspas em Rótulos de Relacionamento:** Todo verbo ou frase de ligação nos relacionamentos deve estar entre **aspas duplas** (ex.: `cliente ||--o{ pedido : "realiza (RN02)"`).

---

# 4. FORMATO OBRIGATÓRIO DA SUA RESPOSTA
Sua resposta deve ser dividida exatamente nas **3 seções abaixo**:

### SEÇÃO 1: ⚠️ RELATÓRIO IMPORTANTE DE AUDITORIA E AJUSTES NO DOCUMENTO DE REQUISITOS
Analise se há qualquer inconsistência ou omissão entre os **Requisitos Funcionais (Seção 2)**, **Requisitos Não Funcionais (Seção 3)**, **Regras de Negócio (Seção 4)**, **Políticas e Restrições (Seção 5)** e a tabela **6.1. Entidades Preliminares Identificadas**.
Liste de forma consolidada com o selo **🔴 [IMPORTANTE - ATUALIZAR NO DOCUMENTO DE REQUISITOS]** cada ajuste realizado no DER para que o banco de dados funcione perfeitamente na prática, tais como:
- **Entidades Citadas no Texto mas Ausentes na Seção 6.1:** (Ex.: `historico_preco` citado no RF03; tabela de `estorno` exigida na PR02).
- **Atributos Citados em RFs/RNs/PRs mas Ausentes na Seção 6.1:** (Ex.: `email` opcional no RF01; `desconto` citado no RF02 e RN05; `data_cancelamento` exigida na PR02; campos de consentimento/anonimização da PR03; `complemento` e `bairro` no endereço).
- **Ajustes de Integridade e Cardinalidade:** Justificativa das cardinalidades mínimas e máximas adotadas e garantias de 3FN.

### SEÇÃO 2: 📊 CÓDIGO DO DIAGRAMA ENTIDADE-RELACIONAMENTO (MERMAID)
Forneça um bloco de código ` ```mermaid ` contendo o `erDiagram` completo, contemplando todas as entidades originais da seção 6.1 + os atributos e entidades complementares identificados na auditoria (devidamente sinalizados com comentários `%%`), seguindo 100% das regras de indentação, blocos lógicos, tipos MySQL e relacionamentos no rodapé.

### SEÇÃO 3: 🗂️ RESUMO DE ÍNDICES E GATILHOS (TRIGGERS) COMPLEMENTARES
Liste brevemente os índices (`INDEX`) e gatilhos (`TRIGGER` / `CHECK`) exigidos pelas seções 4, 6.2 e 6.3 que não têm representação gráfica nativa em um DER conceitual/lógico, mas que implementam as regras de negócio no MySQL.

---

# DOCUMENTO DE ESPECIFICAÇÃO PARA ANÁLISE:
[CONTEÚDO DO DOCUMENTO DO ARQUIVO ANEXO]


Copiar e colar o código no Mermind:  https://mermaid.ai/app/dashboard

3. Elaboração de prompts para geração de modelos: baseado nos requisitos elaborado anteriomente para orientar geração de diagrama do banco de dados utilizando mermaid IA, com seguinte prompts:
# Contexto e Papel
Atue como um Arquiteto de Dados Senior (focado em Governança de Dados, DAMA-DMBOK e COBIT) e um Desenvolvedor Front-end Especialista Sênior. 
Seu objetivo é analisar a modelagem de um banco de dados, apontar correções de coerência e gerar um Dicionário de Dados interativo, profissional e focado em governança, pronto para ser hospedado no GitHub Pages. Padrão profissional usando as boas práticas internacionais para governança de dados.

**DIRETRIZES ESTRITAS ANTI-ALUCINAÇÃO (LEIA COM ATENÇÃO):** 
1. **Zero Omissão:** É estritamente proibido usar placeholders no código gerado (como `<!-- restante das tabelas aqui -->`, `// mais código`, ou `...`). Você deve gerar o HTML, CSS e JS contemplando **100% das tabelas e colunas** presentes no script DDL fornecido.
2. **Fidelidade ao DDL:** Não invente colunas, tabelas ou relacionamentos que não estejam no DDL. Se uma informação de governança (como Linhagem ou LGPD) não estiver óbvia, infira com base no nome e contexto da coluna, mas mantenha a tipagem e chaves exatas do DDL.
3. **Links Funcionais:** Use apenas CDNs oficiais e estáveis para bibliotecas externas (ex: Bootstrap 5, Tailwind, FontAwesome, Panzoom.js, Prism.js ou Highlight.js). 
4. **Sem Emojis:** Não utilize emojis na interface gerada nem na sua explicação de saída.

---

# ENTRADA DE DADOS E CUSTOMIZAÇÃO DO PROJETO
**[ALUNO: Preencha as informações abaixo antes de enviar o prompt]**

**1. Informações do Projeto:**
- **Nome da Empresa/Projeto:** [Nome do seu projeto]
- **Nome do Professor Orientador:** Prof. Dr. Diego Carvalho
- **Integrantes e Papeis (Data Owners e Data Stewards):** 
  - [Ex: Joao Silva - Data Owner (Regras de Negócio)]
  - [Ex: Maria Souza - Data Steward (Qualidade Técnica e Dicionário)]
- **Cores da Identidade Visual:** [Ex: Azul Marinho (#000080) e Cinza Claro (#F4F4F9)]
- **Resumo do Negócio:** [Ex: Sistema de gestão de biblioteca escolar...]

**2. Documentação do Banco de Dados:**
- **Especificação de Requisitos e Regras de Negócio:**
Documento em ANEXO: [ESCREVA AQUI O NOME DO ARQUIVO]

- **Diagrama Entidade e Relacionamento (DER - Descrição ou Metadados):**
Documento em ANEXO: [ESCREVA AQUI O NOME DO ARQUIVO]

- **Script de Criação DDL (Data Definition Language):**
Documento em ANEXO: [ESCREVA AQUI O NOME DO ARQUIVO]

---

# TAREFAS QUE A IA DEVE EXECUTAR

## PARTE 1: Lista de Customização e Metadados do Projeto
Apresente um cabeçalho executivo confirmando os dados de entrada. Adicione um parágrafo sobre "Data Literacy" (Cultura de Dados) explicando o valor estratégico deste dicionário específico para a empresa descrita, baseando-se no DMBOK e COBIT.

## PARTE 2: Análise de Coerência e Sugestões de Ajustes Manuais
Cruze as três fontes de dados (Requisitos, DER e DDL). 
- Liste divergências de cardinalidade, tipos de dados, chaves estrangeiras órfãs ou regras de negócio descritas nos requisitos mas ausentes no DDL.
- Fornecer a correção em formato de lista (Ex: "No documento de requisitos, na linha X, altere a palavra Y para Z para alinhar com a tabela W").
- Se estiver tudo perfeito, diga explicitamente: "Não são necessários ajustes nestes documentos."
- Observação: avise que o dicionário de dados não pode ser publicado sem as devidas alterações no documento de requisitos e no DER.
- Ao final, o documento de requisitos deve ser exportado em PDF e o DER em PNG.

Verifique minuciosamente todos os documentos (Especificação de Requisitos e Regras de Negócio, Diagrama Entidade e Relacionamento, Script de Criação DDL), e liste todos os itens que o autor esqueceu de remover ou preencher:
- Textos entre colchetes `[ ]` não substituídos.
- Páginas de instruções do template (ex.: *"COMO UTILIZAR ESTE MODELO"*) e caixas de texto iniciadas por *"Orientação:"* ou textos em cinza.
- Nomes fictícios ou padronizados do template no Histórico de Revisões.
- O histórico de revisões deve ter no mínimo 3 itens, sendo o primeiro a criação inicial do documento, mais duas revisões, sendo esta realizada agora a 4º revisão.

## PARTE 3: Geração do Código (HTML, CSS, JS) do Dicionário de Dados
Gere o código completo. Crie blocos de código distintos e completos para `index.html`, `style.css` e `script.js`. 

**Diretrizes de Layout (UI/UX) obrigatórias:**
1. **Estrutura de Página (Dashboard):**
   - **Topbar:** Título do projeto, nome da empresa, Toggle para Light/Dark Mode.
   - **Identificação:** seção de identificação do projeto de modelagem de banco de dados com:
**Escopo:** Escopo do projeto em um parágrafo resumido.
**Tecnologia:** MySQL.
   3. *Responsáveis:** Identificação dos autores do projeto e suas responsabilidades.
   - **Sidebar Esquerda (Navegação):** Menu com âncoras (`<a href="#tabela_nome">`) listando todas as tabelas do sistema dinamicamente. A sidebar de navegação deve ser responsiva e se adaptar a celulares.
   - **Área Principal (Main):** Onde as tabelas e o DER serão exibidos.
2. **Painel de Controle Acima do Dicionário:**
   - Botão de ação: Baixar Especificação de Requisitos (PDF).
   - Botão para abrir o DER em modal.
   - Botão para abrir o DDL (Data Definition Language).
   - **Barra de Pesquisa (JS Real-time):** Um input que filtre instantaneamente as tabelas e linhas do dicionário conforme o usuário digita (filtrando por nome da coluna ou tabela).
3. **Visualizador do DER no Modal (Navegação Ótima e Zoom):**
   - A imagem do DER deve ser implementada com um recurso de zoom e navegação ótima.
   - Utilize a biblioteca Panzoom.js (via CDN) ou lógica JS equivalente para garantir que a imagem abra em tela cheia com os seguintes recursos:
     - Zoom In e Zoom Out via scroll do mouse.
     - Pan (arrastar a imagem livremente em qualquer direção) segurando o clique do mouse.
     - Botões fixos na tela do modal para: Zoom +, Zoom -, e Reset (voltar ao tamanho e posição original).
4. **Visualizador do Script DDL no Modal (Syntax Highlighting SQL):**
   - Ao clicar no botão "Abrir DDL", deve abrir um modal dedicado e responsivo exibindo **100% do código SQL original** fornecido em anexo (sem omissões ou resumos).
   - **Syntax Highlighting Profissional:** Utilize a biblioteca **Prism.js** ou **Highlight.js** (via CDN oficial e estável, com tema escuro como *Atom One Dark* ou *Tomorrow Night*) configurada especificamente para a linguagem `sql` (`class="language-sql"`), garantindo destaque visual claro para palavras-chave (`CREATE TABLE`, `PRIMARY KEY`, `FOREIGN KEY`, `CONSTRAINT`), tipos de dados (`VARCHAR`, `INT`, `DECIMAL`), strings e comentários.
   - **Recursos de Usabilidade do Código:**
     - **Numeração de Linhas:** Exibir números de linha alinhados à esquerda para facilitar auditorias e revisões de código.
     - **Botão "Copiar DDL":** Um botão no topo do modal que copia todo o script SQL para a área de transferência via `navigator.clipboard.writeText()` e altera temporariamente seu texto para "Copiado!" como feedback visual.
     - **Scroll Independente:** Área de código com barra de rolagem vertical e horizontal (`overflow: auto` e `max-height: 70vh`) com fonte monoespaçada legível (ex: `Fira Code`, `JetBrains Mono` ou `Consolas`).

**Diretrizes do Dicionário de Dados (Governança):**
Cada tabela do DDL deve virar um `<section>` com título, descrição da finalidade da tabela e uma tabela HTML responsiva.
As colunas da tabela HTML DEVEM ser:
1. **Atributo:** Nome da coluna no BD.
2. **Descrição / Regra de Negócio:** Para que serve e limites.
3. **Tipo e Tamanho:** Extraído diretamente do DDL (Ex: VARCHAR(255)).
4. **Constraints:** (PK, FK, NULL, UNIQUE). Use marcadores textuais destacados em negrito ou brackets (Ex: [PK] e [FK]).
5. **Privacidade (LGPD/GDPR):** Utilize Badges visuais (Tags coloridas via CSS):
   - [DPS] (Dado Pessoal Sensível - Cor de fundo vermelha).
   - [DP] (Dado Pessoal - Cor de fundo amarela).
   - [N/A] (Não Aplicável - Cor de fundo verde).
6. **Linhagem (Data Lineage):** Origem e Destino do dado.
7. **Controle de Acesso (RBAC):** Quem tem acesso a esta coluna/tabela.

*(LEMBRETE PARA A IA: Não abrevie o código, entregue as estruturas de TODAS as tabelas contidas no DDL).*

## PARTE 4: Passo a Passo de Estrutura de Pastas e Arquivos
Escreva um tutorial técnico para o aluno informando:
1. A estrutura exata de diretórios local:
   ```text
   /meu-dicionario
   ├── index.html
   ├── style.css
   ├── script.js
   ├── docs/
   │   └── Especificacao_Requisitos_Regras_Negocio_BD.pdf
   └── assets/
       └── der.png (ou .jpg)

Explicação de como as tags <link> e <script> no HTML já estão preparadas para essa estrutura exata.
Como o navegador bloqueia requisições fetch() em arquivos locais abertos via file:// (caso o aluno teste clicando duas vezes no index.html antes de subir no GitHub), não peça para o JS ler um arquivo .sql externo. Deixe o SQL embutido dentro da tag <pre><code class="language-sql">...</code></pre> no próprio index.html (o que também garante o cumprimento da regra de Zero Omissão) e mantenha a estrutura de pastas exatamente como você já desenhou.

## PARTE 5: Tutorial de Deploy no GitHub Pages

Crie um passo a passo para deploy:

- Como subir a pasta para um repositório público no GitHub.

O caminho exato: Settings > Pages > Build and deployment > Source: GitHub Actions > Select "Static HTML" > Configure > Commit changes.

Um aviso importante sobre Case Sensitivity (maiusculas e minúsculas) nos caminhos dos arquivos no servidor do GitHub Pages.

4. Geração de modelo com mermaid IA: utilizando prompts anterior para gerar a diagrama. Os resultados está em assets/SIMUP_modelo_mermaid_preview.png e assets/SIMUP_modelo_mermaid.pdf
5. Conversão do modelo para SQL: utilizando MySQL workbench para reproduzir o modelo obtido na etapa anterior e gerar script de sql, amarzenado em assets/atividade_sql_simup.sql
6. Geração de catálogo: Usando os mesmo prompts da etapa 3 como base para criar catálogo de database.


IMPORTANTE:

Todas as estruturas, modelos e os script deste projeto foram gerado por meio de prompts de IA indicado por professor. Portanto, o projeto só serve como base para desenvolvimento e não solução final, e é importante de considerar as seguintes limitações e ressalvas:

1. Ausência de modularidade e organização do código: O código gerado não segue necessariamente boas práticas de organização, moduralidade ou outras práicas. Consequentemente, sua estrutura está desordenada e dificultará coompreensão e manuntenção.
2. Ausência de definição prévia da arquitetura do sitema: O modelo de banco de dadofoi elaborado sem uma definição prévia da arquitetura, por exemplo, Event store é utilizado porém não foi documentado. Como diferentes arquiteturas podem exigir diferentes dados, podem existir incosistência ou limitações que precisarão ser revisado durante implementação definitivadamente.
3. Ausência de análise e design de seguraça, desempenho, impacto e riscos. Além disso, alguns estrutura podem não ser mais adequada para determinados cenários. Por exemplo, a tabela localizacao poderia utilizar recursos de indexação espacial, como R-tree ou estrutura geoespaciais disponíveis no PostgreSQL, para otimização de consulta.
4. Desenvolvimento em grupo e envio individual: O trabalho foi desenvolvido em equipe. Entretanto, deviado a restrição estabelecido por professor, cada integrante deverá realizar o envio individualmente em seu respectivo repositório de GitHub.
5. Responsabilidade e profissão fictional no documento: As profissões e responsabilidade atribuída aos integrantes do grupo são fictícias e foram definidas para atenter requistios acadêmico do projeto.
6. Ausência de documento dos códigos(nesse caso, catálogo): Não há documento específica para qualquer código. Isso pode dificultar a manuntenção e compreensão de futuras implementação.
7. Ausência de manutenção futura: Este repositório possui finalidade exclusivamente acadêmica e não está previsto para receber manutenção ou atualizações futuras.
8. Não existe documento detalhada sobre como as tabelas será utlizado nas implementação final. Porém, só consiste o que a coluna e tabela faz e não como utilizado.
