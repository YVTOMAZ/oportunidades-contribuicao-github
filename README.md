# Tarefa: oportunidades de contribuição em projetos alheios e ideias de projetos novos

- **Identificador:** github_oportunidades-contribuicao-e-novos-projetos_2026-11-12_22-18-09_BRT
- **Data/fuso:** 12/11/2026 22:18:09 BRT (America/Sao_Paulo, UTC-3)
- **Tipo:** pesquisa e roteiro de contribuição (não é manutenção do Contextuva)
- **Prioridade:** alta para a primeira contribuição externa (issue #803 do brazilian-utils). Justificativa: o Yago pediu projetos para ajudar e projetos novos; uma contribuição real, pequena e bem documentada em repositório brasileiro ativo é o caminho legítimo mais próximo de visibilidade, Discussions (Galaxy Brain) e rede, sem inflar PRs.
- **Substitui:** nenhuma tarefa. Esta entrega não altera arquivos em `pii-guard-br` nem no perfil `YVTOMAZ/YVTOMAZ`.

## 1. Contexto

Yago Tomaz (GitHub [YVTOMAZ](https://github.com/YVTOMAZ)), dev full-stack em Ipatinga-MG. Stack vista nos repositórios: Python, PHP/Laravel, JS/TS, Vue/React. Projeto open source próprio: [Contextuva](https://github.com/YVTOMAZ/pii-guard-br) (Python, MCP, proteção de PII/LGPD; derivado de `oLucasAguilar/pii-tokens`, MIT — manter a atribuição).

Pedido desta rodada: buscar projetos para ajudar e propor projetos novos. Objetivo permanente: constância e Achievements **legítimos**. Já tem Pull Shark x3, YOLO e Quickdraw. Candidatos seguintes: Galaxy Brain (respostas aceitas em Discussions), Starstruck (estrelas orgânicas), Pair Extraordinaire (coautor **real** que de fato trabalhou no commit).

Proibido: spam, PRs triviais em massa, troca de estrelas, coautores inventados, push direto em `main`/`master` de projeto alheio (e também do próprio, pelo fluxo já combinado: branch + `gh pr create` + checks + squash).

Pesquisa feita em 12/11/2026 ~22:05–22:18 BRT, via API pública do GitHub e páginas HTML (o `gh` na box **não** estava autenticado; nada foi aberto, comentado, forçado ou publicado). Cada URL listada abaixo respondeu HTTP 200. Critérios: commit/merge nos últimos 60 dias (a partir de ~13/09/2026), mantenedores mesclando PRs, issue aberta verificada, sem assignee e sem PR em andamento dedicado àquela issue.

## 2. Objetivo

1. Entregar uma lista priorizada de **7** repositórios ativos, com **uma issue específica** (e alternativas no mesmo repo, quando couber), para o Yago contribuir de forma útil.
2. Detalhar o passo a passo da **primeira contribuição recomendada** (`brazilian-utils/python` #803), seguindo o `CONTRIBUTING.md` do projeto.
3. Propor **3** ideias de projetos novos, com nome checado, escopo de MVP, stack e primeiro passo.
4. Deixar critérios de aceite, segurança e formato de retorno para a automação local (`cronjob/fila.py`) ou execução manual.

Fora do escopo desta tarefa:

- Abrir issues, comentários, forks ou PRs a partir desta box ou desta entrega.
- Implementar o patch da #803 (isso fica para o Yago/automação local).
- Mexer no Contextuva, no perfil ou em qualquer arquivo já presente em `aguardando`.
- Pedir estrelas, seguir troca de favores ou inventar coautoria.

## 3. Lista priorizada de projetos para ajudar

### 1) [brazilian-utils/python](https://github.com/brazilian-utils/python) — **começar por este**

- **O quê:** biblioteca Python (`brutils`) para validar, gerar e formatar dados brasileiros (CPF, CNPJ, CEP, etc.). 535 estrelas, MIT, Python. Último push: 09/11/2026. PR externo mesclado em 30/10/2026 ([#754](https://github.com/brazilian-utils/python/pull/754), `rennerocha`).
- **Issue:** [#803 — Validação de CEP aceita algarismos sobrescritos](https://github.com/brazilian-utils/python/issues/803). Aberta em 10/11/2026 por `Filipcardos`. Estado conferido: `open`, 0 comentários, **sem assignee**, busca por PR mencionando 803 = 0. HTTP 200.
- **Por que encaixa:** Python, domínio brasileiro, bug pequeno e reproduzível (`is_valid('²' * 8)` retorna `True` porque `str.isdigit()` aceita dígitos Unicode). O `CONTRIBUTING.md` é em português e descreve o primeiro PR com clareza.
- **Esforço:** baixo (cerca de 1–3 h). Arquivo apontado: `brutils/cep.py`. Exigir ASCII (ou equivalente mais estrito que `isdigit()`), testes, `CHANGELOG.md` na seção `Unreleased` / `Fixed`.
- **Discussions (Galaxy Brain):** sim, ativas em pt-BR. Há pelo menos 4 threads, inclusive “Boas-vindas”, “CNPJ alfanumérico a partir de 2026” e “RFC: Estratégia para tratamento de valores inválidos nas funções do brazilian-utils”. Responder com qualidade, sem spam; o selo só conta com resposta **aceita**.
- **CONTRIBUTING:** https://github.com/brazilian-utils/python/blob/main/CONTRIBUTING.md
- **Guia desta entrega:** seção 4.

### 2) [nfephp-org/sped-nfe](https://github.com/nfephp-org/sped-nfe)

- **O quê:** API PHP de geração e comunicação de NF-e com as SEFAZ. 1623 estrelas. Último push: 05/11/2026. Comunidade brasileira viva: PRs de terceiros mesclados em novembro (`MaximusGF` #1401 e #1400, `Maykon-JDS` #1391, `darc591` #1381).
- **Issue:** [#1395 — Documentação aponta para pastas de esquema antigas (Config.md, MakePL010.md, examples, README)](https://github.com/nfephp-org/sped-nfe/issues/1395). Aberta em 04/11/2026, `open`, 0 comentários, sem assignee, sem PR vinculado. HTTP 200.
- **Por que encaixa:** PHP (stack Laravel/PHP do Yago), documentação, impacto real para quem emite nota (os esquemas atuais da reforma tributária não são os de 2017/2019 citados nos docs). Inglês no PR pode ser simples; o projeto aceita pt-BR.
- **Esforço:** baixo a médio (levar os docs e exemplos à pasta de esquemas vigente; conferir no código o padrão atual; não misturar com bugs de validação).
- **Discussions:** não habilitadas.
- **CONTRIBUTING:** https://github.com/nfephp-org/sped-nfe/blob/master/CONTRIBUTING.md — PSR-2, **testes obrigatórios** se houver mudança de código, branch própria (nunca pedir pull do `master` do fork), um assunto por PR, histórico coerente (squash local se necessário). Para um PR só de docs, seguir o guia e deixar explícito o que foi atualizado.
- **Alternativas no mesmo repo (também abertas, sem assignee/PR):** [#1394](https://github.com/nfephp-org/sped-nfe/issues/1394) (SECURITY.md, Dependabot, `composer audit` no CI) e [#1393](https://github.com/nfephp-org/sped-nfe/issues/1393) (bug de validação XSD silenciosa — esforço maior, risco alto). Não pegar [#1390](https://github.com/nfephp-org/sped-nfe/issues/1390) (já tem o PR #1392) nem [#1385](https://github.com/nfephp-org/sped-nfe/issues/1385) (campos já tratados nos PRs #1400/#1401 mesclados).

### 3) [DeHor-Labs/mcp-fiscal-brasil](https://github.com/DeHor-Labs/mcp-fiscal-brasil)

- **O quê:** servidor MCP fiscal brasileiro (CNPJ, NF-e, NFS-e, SPED, Simples, Reforma 2026). 429 estrelas, MIT, Python. Último push: 01/11/2026. README convida a PRs. Dependabot mesclado em 01/11; há PRs humanos **abertos** (ainda não mesclados nesta data) — a fila de revisão existe, mas o projeto está ativo.
- **Issue:** [#149 — Descrições incorretas na tabela de CFOP (5110, 6107, 6108 e 6110)](https://github.com/DeHor-Labs/mcp-fiscal-brasil/issues/149). Aberta em 20/09/2026, `open`, 0 comentários, sem assignee. A busca por PRs “mencionando 149” só trouxe o #124 (fechado, outro assunto — falso positivo do número). HTTP 200.
- **Por que encaixa:** MCP + Python, o mesmo recorte do Contextuva, utilidade direta para contadores. Correção de dados oficiais (CONFAZ), com testes objetivos.
- **Esforço:** baixo a médio.
- **Discussions (Galaxy Brain):** sim. Threads em pt-BR (“Bem-vindo”, “Dúvidas fiscais ou técnicas?”, “Qual feature você gostaria de ver?”, casos de uso).
- **CONTRIBUTING:** não há arquivo dedicado; o README descreve fork + PR e aponta as issues. Seguir o padrão `client.py` + `schemas.py` + `tools.py` e o estilo do repo.
- **Próxima issue livre no mesmo repo:** [#148](https://github.com/DeHor-Labs/mcp-fiscal-brasil/issues/148) (`summarize_sped` lê alíquota no lugar de `VL_CONT_PER` nos registros M210/M610) — esforço médio, também sem PR dedicado.
- **Não pegar** (já têm PR aberto): #190/#153 (PR #191), #200 (PR #201), #196 (PR #199), #194 (PR #198), #195 (PR #197), #135 (provável PR #193, 500 no Simples).

### 4) [akretion/nfelib](https://github.com/akretion/nfelib)

- **O quê:** bindings Python para XML de NF-e, NFS-e, CT-e, MDF-e, BP-e. 221 estrelas, MIT. Último push: 05/11/2026. PR externo mesclado no mesmo dia (`antoniospneto` #174); o mantenedor `rvalyi` também mescla com frequência.
- **Issue:** [#159 — CI: testes que dependem de rede reprovam PRs e afogam o sinal do watcher de schema](https://github.com/akretion/nfelib/issues/159). Aberta em 22/08/2026, atualizada em 06/09/2026, `open`, 1 comentário (`hitoshyamamoto` propõe marker `live` + deseleção por padrão, **sem reivindicar a issue e sem PR**). Sem assignee. Busca de PR = 0. HTTP 200.
- **Por que encaixa:** Python, documentos fiscais brasileiros, melhoria de CI que desbloqueia outros contribuidores (incluindo o primeiro PR do Yago neste repo, se vier depois).
- **Esforço:** médio (separar testes de rede dos unitários, preservar o `test_fingerprint` num job agendado, documentar no README).
- **Discussions:** não habilitadas.
- **CONTRIBUTING:** não há arquivo; ler o README e o comentário da #159 antes de implementar. Comentar na issue a abordagem (marker `live` ou equivalente já usado no repo) e só então abrir o PR.

### 5) [DeHor-Labs/mcp-juridico-brasil](https://github.com/DeHor-Labs/mcp-juridico-brasil)

- **O quê:** servidor MCP de acompanhamento processual sobre a API pública do DataJud (CNJ). 139 estrelas, MIT, Python. Último push: 26/10/2026. Há `CONTRIBUTING.md`. Os PRs mesclados visíveis são em grande parte do mantenedor `nikolasdehor` (junho/2026); o repositório continua recebendo commits e a issue #26 foi aberta em 28/10. Vale um PR pequeno primeiro, sem esperar revisão instantânea.
- **Issue (menor):** [#11 — Padronizar lazy init de `_provider` nos módulos datajud e comercial](https://github.com/DeHor-Labs/mcp-juridico-brasil/issues/11). Label `tech-debt`, `open`, 0 comentários, sem assignee, aberta em 22/06/2026. Os “PRs mencionando 11” são falso positivo (outros PRs do repo). HTTP 200.
- **Issue (maior, mais recente):** [#26 — Cálculo de prazo: ritos além do CPC, leis especiais, prazo em dobro e regra do DJEN](https://github.com/DeHor-Labs/mcp-juridico-brasil/issues/26). `enhancement`, 28/10/2026, único comentário é o bot de boas-vindas, sem assignee, sem PR. Esforço alto; só depois de um PR menor no mesmo projeto, ou se o Yago quiser se aprofundar em prazos.
- **Por que encaixa:** MCP + Python + dados públicos brasileiros; o #11 é refactor localizado com testes.
- **Esforço:** #11 baixo a médio; #26 alto.
- **Discussions:** não habilitadas.
- **CONTRIBUTING:** https://github.com/DeHor-Labs/mcp-juridico-brasil/blob/main/CONTRIBUTING.md — ambiente com `uv`, convenção `client.py` / `schemas.py` / `tools.py`.

### 6) [nfephp-org/sped-common](https://github.com/nfephp-org/sped-common)

- **O quê:** classes PHP comuns das APIs de NF-e, CT-e e MDF-e. 114 estrelas. Último push: 30/09/2026 (dentro dos 60 dias). PR #321 (suporte a PHP 8.5, `gersonfs`) mesclado nessa data.
- **Issue:** [#323 — Leitura de XML sem bloqueio de acesso externo (LIBXML_NONET)](https://github.com/nfephp-org/sped-common/issues/323). Aberta em 04/11/2026, `open`, 0 comentários, sem assignee, sem PR. HTTP 200.
- **Por que encaixa:** PHP, endurecimento legítimo de biblioteca fiscal muito usada (irmã do sped-nfe).
- **Esforço:** baixo a médio (aplicar a flag no parse, testes de regressão, documentar o comportamento). **Não** incluir PoC de ataque, payload de XXE nem passo a passo exploratório no PR, na issue ou em logs — a issue já descreve o problema; o PR deve ser só a correção e os testes de defesa.
- **Discussions:** não habilitadas.
- **CONTRIBUTING:** https://github.com/nfephp-org/sped-common/blob/master/CONTRIBUTING.md (mesmo espírito do sped-nfe: PSR-2, testes, branch própria).
- **Cuidado com a irmã [#322](https://github.com/nfephp-org/sped-common/issues/322)** (`CURLOPT_SSL_VERIFYPEER` nunca ligado): também está livre, mas é mudança de segurança de alto impacto e pode ter motivo histórico (cadeia de certificados das SEFAZ). Só abordar depois de ler o código e conversar na issue; não é a primeira escolha.

### 7) [DeHor-Labs/mcp-agro-brasil](https://github.com/DeHor-Labs/mcp-agro-brasil)

- **O quê:** servidor MCP de cotações e dados do agronegócio brasileiro. 71 estrelas, Python. Último push: 02/11/2026. PRs do mantenedor e Dependabot mesclados até agosto; o repo segue recebendo commits.
- **Issue:** [#12 — Integração com a Calculadora de Piso Mínimo de Frete da ANTT](https://github.com/DeHor-Labs/mcp-agro-brasil/issues/12). `open`, sem assignee, 1 comentário (só o link da calculadora pública). Sem PR dedicado (os “mentions” são PRs de dependências). Última atualização: 26/08/2026. HTTP 200.
- **Por que encaixa:** MCP + Python + dado oficial brasileiro. É uma feature, não um bug pontual.
- **Esforço:** alto (metodologia da Resolução ANTT nº 5.867/2020 e atualizações; preferir coeficientes oficiais a scraping da calculadora, se não houver API documentada).
- **Discussions:** não habilitadas.
- **Prioridade:** a mais baixa desta lista. Comentar a abordagem na issue antes de escrever código.

### Comunidades para acompanhar (sem issue livre agora)

Úteis para **Galaxy Brain** ou para um PR futuro, mas **não** têm issue aberta livre nesta data:

- [Engenere/BrazilFiscalReport](https://github.com/Engenere/BrazilFiscalReport) (144 estrelas, Python, DANFE/DACTE em PDF, push em 11/11/2026, PRs externos mesclados na mesma semana). Discussions ativas (“Campos de IBS, ISS e CBS no DANFe e DANFSe”, notas de versão). A única issue aberta, [#232](https://github.com/Engenere/BrazilFiscalReport/issues/232), **já tem os PRs #233 e #234**. Não sobrepor. Pode responder Discussions e esperar a próxima issue.
- [data-privacy-stack/presidio](https://github.com/data-privacy-stack/presidio) (framework de detecção/anonimização de PII, ~11,8 mil estrelas, Discussions ativas). Há recognizers por país (`australia`, `canada`, `india`, `italy`, etc.) e **nenhuma pasta Brazil**. As issues com label `good first issue` que apareceram (#2256, #1090) **já têm trabalho/PRs em andamento** — não entrar nelas. As Discussions incluem packs de país (ex.: `canpii` para identificadores canadenses), que servem de modelo para a ideia de projeto novo nº 2.

### O que foi verificado e descartado (não inventado)

- `brazilian-utils/javascript`: ativo (push 04/11, 1687 estrelas, Discussions), mas a única issue aberta listada (#602) é um guarda-chuva de breaking changes da v3, não um primeiro PR.
- `alvarofpp/validate-docbr`: existe e teve push em 01/10/2026 (485 estrelas), porém **zero issues abertas**.
- `LaravelLegends/pt-br-validator`: existe (649 estrelas, Laravel), mas último push em 12/05/2026 (fora dos 60 dias).
- `geekcom/validator-docs`: push em 03/11, issues fracas (a #160 se chama “Oi”); último merge humano relevante é mais antigo. Não priorizar.
- `leandrocfe/filament-ptbr-form-fields`: ativo, mas a #88 já tem o PR #89.
- `TadaSoftware/PyNFe` e `mstuttgart/brazilcep`: existam, porém último push em fev/2026.
- `brasil-mcp/match`: existe, último push em maio, 0 issues, 0 estrelas.
- `pythonbrasil/manual` e `pythonbrasil/wiki`: a org existe e alguns repos tiveram push recente, mas as issues abertas estão em maioria antigas e o histórico de merge de PRs é lento. A wiki tem labels “amigável para iniciantes” (#283, #313) com comentários velhos — risco de trabalho ignorado.
- `laravel-brasil/laravel-brasil` e `Laravel-Brasil/forum`: **não existem** (404).
- `mityda/ClauseKeeper` #2 (LGPD, `good first issue`): último push do repo em 23/06/2026 (fora dos 60 dias) e já havia interesse declarado de outro contribuidor.
- FastMCP e `modelcontextprotocol/python-sdk`: muito ativos, mas as issues “boas” de docs/bugs são reivindicadas em horas (ex.: python-sdk #3846 já tem o PR #3848 fechado à espera de assignee). Ambiente em inglês e altamente competitivo — só vale depois das contribuições brasileiras desta lista.

## 4. Tarefas ordenadas — primeira contribuição recomendada (`brazilian-utils/python` #803)

Execução pelo Yago ou pela automação local. **Não** implementar nem publicar a partir desta entrega. Se no momento de executar a #803 tiver assignee, comentário “bora!” de outra pessoa, ou PR aberto, **parar** e pular para o item 2 da lista (sped-nfe #1395).

```bash
# 0. Pré-checagem (conta YVTOMAZ)
export PATH="$HOME/.local/bin:$PATH"
gh auth status
# Conferir de novo, no dia da execução:
# - issue ainda open, sem assignee, sem PR:
#   https://github.com/brazilian-utils/python/issues/803
```

1. **Ler** o [CONTRIBUTING.md](https://github.com/brazilian-utils/python/blob/main/CONTRIBUTING.md) inteiro (está em pt-BR) e a issue #803. O guia exige: uma issue por vez; branch com o **número da issue**; Python 3.10+; testes passando; entrada no `CHANGELOG.md`; PR com `Closes #803` (ou `Fixes #803`).

2. **Comentar na issue exatamente `bora!`** (é o texto que o guia pede) e **esperar o bot atribuir a issue a você**. Só depois disso avançar. Se outra pessoa comentou `bora!` ou o bot atribuiu a outro login, desistir desta issue.

3. Fork de https://github.com/brazilian-utils/python para `YVTOMAZ/python` (ou o nome que o GitHub der ao fork). Não altere o upstream.

4. Clone o **fork**, adicione o upstream, atualize `main`:

```bash
git clone git@github.com:YVTOMAZ/python.git brutils-python
cd brutils-python
git remote add upstream https://github.com/brazilian-utils/python.git
git fetch upstream
git checkout main
git merge --ff-only upstream/main
```

5. Branch no formato exigido pelo projeto (o número da issue, sem prefixo):

```bash
git checkout -b 803
```

6. Ambiente local (preferir o fluxo oficial com Poetry + Makefile). Requisitos: Python 3.10+.

```bash
make shell          # repetir em cada novo terminal
make install        # instala deps e configura hooks em .githooks/
make test           # precisa retornar OK **antes** de qualquer patch
```

Alternativa com pip, só se o Poetry não estiver disponível: `python -m venv venv && source venv/bin/activate && pip install -r requirements-dev.txt` e o comando de teste equivalente documentado no Makefile/`CONTRIBUTING`.

7. **Corrigir o bug** em `brutils/cep.py` (caminho citado na issue). Reprodução atual, segundo a #803: `is_valid('²' * 8)` retorna `True` e `format_cep('²' * 8)` retorna `'²²²²²-²²²'`. O esperado é `False` e `None`. Causa apontada: `str.isdigit()` aceita dígitos Unicode (ex.: `²`). A própria issue sugere exigir `cep.isascii()` além da checagem atual. Manter o comportamento para CEPs ASCII válidos (com e sem hífen, se já for o contrato). Não expandir o PR para outros validadores, a menos que o mesmo buraco esteja no mesmo arquivo e os testes já existentes quebrem — nesse caso, descrever no PR e não “consertar o mundo”.

8. **Testes novos** cobrindo o caso da issue (algarismos sobrescritos e, se fizer sentido, outros dígitos não ASCII). Rodar de novo:

```bash
make test
```

Hipótese, **não verificada aqui:** a suíte passa hoje no `main`. Se falhar antes do patch, parar e reportar; não “consertar” falhas alheias no mesmo PR.

9. Teste manual rápido no interpretador, como o guia pede (`from brutils.cep import is_valid, format_cep` ou o import público equivalente no README). Não usar CEP, CPF ou nome reais — só os exemplos sintéticos da issue (`'²' * 8`) e CEPs fictícios claramente inválidos/válidos de teste.

10. Se o README documentar `is_valid` / `format_cep` de CEP e a mudança de contrato merecer uma linha, atualizar `README.md` e `README_EN.md` (passo 10 do guia). Se a API pública não mudar para entradas ASCII, talvez não seja necessário — julgar no diff e não inventar seção nova.

11. Entrada no `CHANGELOG.md`, seção `## [Unreleased]`, tipo `### Fixed` (criar a subseção se não existir). Ordem alfabética das subseções: Added, Changed, Deprecated, Fixed, Removed, Security — o repo tem lint disso. Formato no estilo do guia, ligando a issue, por exemplo:

   `- Validação e formatação de CEP rejeitam algarismos não ASCII (ex.: sobrescritos). [#803](https://github.com/brazilian-utils/python/issues/803)`

12. Formatar e commitar **só os arquivos desta correção** (não usar `git add --all` se houver artefatos locais, `.env` ou chaves):

```bash
make format
git add brutils/cep.py tests/  CHANGELOG.md
# incluir README.md e README_EN.md somente se tiverem sido alterados de fato
git status   # revisar o palco
git commit -m "Corrige validação de CEP que aceitava algarismos sobrescritos"
git push --set-upstream origin 803
```

O hook de pre-push do projeto deve rodar. Se falhar, corrigir antes de reenviar. **Nunca** dê push no `main` do fork com o patch, e **nunca** no `main` do upstream.

13. Abrir o PR no repositório **brazilian-utils/python** (base `main`), não no fork:

```bash
gh pr create --repo brazilian-utils/python --base main --head YVTOMAZ:803 \
  --title "Corrige validação de CEP que aceitava algarismos sobrescritos" \
  --body "$(cat <<'EOF'
## O que
A validação e a formatação de CEP passam a rejeitar algarismos não ASCII (por exemplo \`²\`), que \`str.isdigit()\` aceitava.

## Por que
Reproduz o caso da issue: \`is_valid('²' * 8)\` retornava True e \`format_cep('²' * 8)\` devolvia um CEP “formatado” com sobrescritos.

## Testes
Incluí cobertura para esse caso e rodei \`make test\` e \`make format\` localmente.

Closes #803
EOF
)"
```

Preencher também o template do repositório, se o `gh pr create` abrir o editor: marcar testes, documentação (se couber) e changelog. A palavra-chave `Closes #803` precisa estar no corpo.

14. Acompanhar os checks do PR. Responder revisão com educação, em pt-BR. Não insistir com pings. Não abrir PR paralelo “para completar” o mesmo assunto. Se pedirem mudanças, commitar na mesma branch `803`.

15. Quando mesclarem, puxar o `upstream/main` no fork e apagar a branch `803`. Não abrir PR de release nem mexer em versão — o guia reserva isso aos mantenedores.

**Rollback:** se o PR ainda não foi mesclado, fechá-lo, apagar a branch `803` no fork e deixar a issue como os mantenedores preferirem (se o bot já tiver atribuído e você desistir, comentar isso na issue). Nada a reverter no `main` do upstream, porque não se empurra direto.

## 5. Ideias de projetos novos (próprios)

Nomes checados na busca `in:name` da API do GitHub em 12/11/2026: nenhum repositório popular homônimo. `contextuva` como nome isolado também estava livre; o repo atual do Yago continua sendo `YVTOMAZ/pii-guard-br`.

### A) `pii-scan-br`

- **Uma linha:** GitHub Action e hook pre-commit que vasculham o diff (e, opcionalmente, o repo) atrás de PII brasileira e reprovam o CI se achar CPF, CNPJ (inclusive alfanumérico), CNS, PIS/NIS, telefone, chave PIX ou similares.
- **Por que pode ganhar estrela de forma orgânica:** completa o Contextuva (que atua no fluxo do agente/MCP) com prevenção no repositório, um problema cotidiano de times brasileiros. Não é troca de estrelas: é ferramenta de CI.
- **Escopo MVP:** padrões e validadores (dígito verificador onde existir), fixtures só com dados **sintéticos**, Action que roda no `pull_request`, hook pre-commit, README em pt-BR e um inglês curto, configuração para permitir arquivos de teste (allowlist). Sem enviar trechos de PII para serviço externo.
- **Stack:** Python (reaproveitar o que fizer sentido do Contextuva, mantendo a atribuição MIT de `pii-tokens` se houver código derivado) + Action em YAML. Licença MIT.
- **Primeiro passo:** repositório novo `YVTOMAZ/pii-scan-br` (não reutilizar o nome `pii-guard-br`), `README` + detector de CPF/CNPJ com testes, depois a Action. Publicar por PR no próprio repo, no fluxo habitual.

O nome `contextuva-action` também estava livre, se quiser marcar a família; `pii-scan-br` fica mais descritivo para quem procura no GitHub.

### B) `presidio-recognizers-br`

- **Uma linha:** pacote Python de recognizers brasileiros para o [Presidio](https://github.com/data-privacy-stack/presidio) (CPF, CNPJ, CNS, título de eleitor, PIS/NIS, CEP, chaves PIX), já que o upstream tem pastas por país e **não tem Brazil**.
- **Por que pode ganhar estrela:** o Presidio é referência mundial de PII; nas Discussions deles há packs de país (ex.: `canpii` para o Canadá). Um pack brasileiro bem testado, com falso-positivo documentado, atrai quem já usa Presidio e quem busca LGPD.
- **Escopo MVP:** pacote instalável, recognizers de CPF e CNPJ (alfanumérico) com checksum, registro documentado no Analyzer, testes com textos sintéticos em pt-BR, README explicando como plugar no Presidio. Não precisa (e não deve) forkear o monorepo inteiro no MVP. Uma issue/PR no upstream pode ser um passo **posterior**, se o pacote amadurecer — não abrir issue vazia agora.
- **Stack:** Python, pytest, API pública do Presidio Analyzer. MIT. Exemplos sem PII real.
- **Primeiro passo:** esqueleto do pacote + recognizer de CPF com testes de dígito e de contexto (para não marcar qualquer sequência de 11 dígitos), publicado em repo `YVTOMAZ/presidio-recognizers-br`.

### C) `vue-br-inputs`

- **Uma linha:** componentes Vue 3 + TypeScript para CPF, CNPJ alfanumérico, telefone, CEP (consulta opcional a serviço público de CEP) e chave/copia-e-cola PIX, com máscara acessível e exemplos sem dados reais.
- **Por que pode ganhar estrela:** o Yago tem Vue no repertório; as libs visíveis (`vue-brazil` e afins) são pequenas, em parte paradas ou ainda em Vue 2. Formulários brasileiros com CNPJ alfanumérico e acessibilidade ainda são uma dor comum.
- **Escopo MVP:** biblioteca Vue 3 (Vite), componentes controlados, validação no cliente, documentação com Storybook ou VitePress, zero log de valores, placeholders fictícios. Sem backend obrigatório no MVP (CEP pode ser adapter).
- **Stack:** Vue 3, TypeScript, Vite. MIT.
- **Primeiro passo:** repo `YVTOMAZ/vue-br-inputs` com o componente de CPF (máscara, validação, testes) e README. Não chamar de `vue-brazil` (esse nome já existe, ainda que com poucas estrelas).

Nenhum desses três deve nascer com commit direto em `main` se o fluxo do Yago for o de sempre: branch, PR, checks, squash.

## 6. Achievements — o que esta entrega pode (e não pode) fazer

- **Pull Shark:** cada PR **útil** mesclado (no brazilian-utils, no sped-nfe, etc.) soma. Não abrir PRs só para contar. O próximo patamar público conhecido é alto; o valor aqui é constância.
- **Galaxy Brain:** só com respostas **aceitas** em Discussions. Melhores filas hoje: brazilian-utils/python, mcp-fiscal-brasil, BrazilFiscalReport (e, em inglês, Presidio, se o Yago quiser). Uma resposta boa, com reprodução ou trecho de lei/docs, vale mais que dez “eu também”.
- **Starstruck:** orgânico, via Contextuva + os projetos novos úteis. Sem pedir estrela em massa e sem troca.
- **Pair Extraordinaire:** somente se uma pessoa real trabalhar no mesmo commit e for creditada com `Co-authored-by` verdadeiro. Não inventar.
- Dependabot e PRs de terceiros no repo do Yago **não** contam como autoria dele.

## 7. Critérios de aceite

- [ ] A issue #803 (ou a substituta, se ela tiver sido reivindicada) foi reconfirmada aberta, sem assignee e sem PR, no dia da execução.
- [ ] O comentário `bora!` foi feito e o bot atribuiu a issue ao YVTOMAZ **antes** do desenvolvimento.
- [ ] O trabalho está numa branch `803` do fork, não no `main` do fork nem no upstream.
- [ ] `make test` e `make format` passam localmente; há teste novo para o caso da issue.
- [ ] `CHANGELOG.md` tem entrada `Fixed` em `[Unreleased]`, no formato do guia.
- [ ] O PR no `brazilian-utils/python` contém `Closes #803`, segue o template e não inclui segredos, CEP/CPF reais nem arquivos irrelevantes.
- [ ] Nada desta entrega foi usado para abrir issue/PR a partir da box do assistente.
- [ ] (Opcional, depois do primeiro PR) uma resposta útil em uma Discussion listada na seção 3, sem spam.

## 8. Segurança, licença e atribuição

- Não commitar `.env`, tokens, certificados A1, chaves SSH nem exemplos com PII real (CPF, CNPJ, nome, telefone, XML de nota de produção). A #803 já traz o caso sintético `'²' * 8`.
- `.env.example`, se algum projeto novo tiver, só com placeholders.
- Não pedir ao Yago que cole tokens no chat.
- Respeitar a licença de cada repo (MIT na maioria desta lista; BrazilFiscalReport é LGPL-3.0, só relevante se for contribuir lá depois). Manter cabeçalhos e créditos. No Contextuva e em código derivado, permanecer a atribuição MIT a Lucas Aguilar / `pii-tokens`.
- No sped-common #323 (se for feita mais tarde): PR de correção e testes de defesa apenas. Sem PoC ofensivo.
- Usar `~/.bashrc` no ambiente do Yago, nunca `/.bashrc`.
- Não habilitar workflows que façam commit automático em `main`.

## 9. Rollback

- PR ainda aberto: fechar, apagar a branch no fork, informar na issue se desistir depois do `bora!`.
- PR já mesclado: não reverter por conta própria; abrir issue/PR novo só se os mantenedores pedirem.
- Não usar `reset --hard` em branch já enviada sem necessidade; não force-push no `main`.

## 10. Formato de retorno (para a automação ou execução local)

Ao terminar (ou ao parar), relatar em pt-BR, curto:

1. URL da issue e se ainda estava livre quando o `bora!` foi enviado.
2. URL do fork, nome da branch, hash do commit.
3. URL do PR e estado dos checks (`gh pr checks`).
4. Comando de teste rodado e o resultado (sem colar PII, tokens ou logs com segredo).
5. Se a #803 não estava mais livre: qual item da lista foi escolhido no lugar, com a URL da issue.
6. O que não foi feito e por quê.

## 11. Fontes desta rodada

Conferência por API pública do GitHub (`/repos`, `/issues`, `/pulls?sort=updated&direction=desc`, busca de PRs, `contents`) e HTTP 200 nas URLs finais, em 12/11/2026 entre ~22:05 e 22:18 BRT. O `gh` na box não estava autenticado. Nenhum comentário, fork, issue ou PR foi aberto por esta entrega.


## Revisao automatica

CORRIGIR

Verificacao de publicacao: Manifesto Git sem repositório da missão

repo-publicacao [local]: Manifesto Git sem repositório da missão | Evidencia: /home/ttechnology/Documentos/melhorar-github/cronjob/estado/github_oportunidades-contribuicao-e-novos-projetos_2026-11-12_22-18-09_BRT.md.git.json | Acao: Criar e publicar o repositorio GitHub com o commit da missao; confirmar a branch publica
