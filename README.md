# IA na redação científica

Slides (Quarto + reveal.js) da palestra de 40 minutos **"IA na redação científica: ética, regras editoriais e boas práticas de reporte"**, de Diogo B. Provete (Instituto de Biociências, UFMS · [Biodiversity Synthesis Lab](https://provetelab.org)).

Público-alvo: pós-graduação e docentes.

## Conteúdo

| Bloco | Tema |
|---|---|
| 0 | O cenário: crescimento das submissões, prevalência de texto assistido por LLM, retratações |
| 1 | Ética: autoria, responsabilidade, equidade e formação |
| 2 | As políticas das cinco maiores editoras (Elsevier, Springer Nature, Wiley, Taylor & Francis, Sage) + Cambridge e OUP |
| 3 | Portaria CNPq nº 2.664/2026 — Política de Integridade na Atividade Científica |
| 4 | A posição do COPE sobre autoria e ferramentas de IA |
| 5 | Limites dos LLMs e cuidados ao gerar texto científico |
| 6 | Boas práticas de reporte: o framework AIdIT |

Todas as citações literais de políticas e normas foram extraídas das páginas oficiais e dos PDFs originais; todos os DOIs e URLs foram verificados.

## Roteiro de tempo (40 min)

São 54 slides, dos quais 7 são aberturas de bloco (5 s cada) e 3 são de apoio (referências e declaração de IA, normalmente não apresentados). Sobram **~44 slides para ~38 min**, ou cerca de 50 s por slide.

| Bloco | Slides | Minutos |
|---|---|---|
| Abertura + roteiro | 1–2 | 2 |
| 0 · Cenário | 3–9 | 7 |
| 1 · Ética | 10–14 | 5 |
| 2 · Editoras | 15–25 | 9 |
| 3 · CNPq | 26–31 | 5 |
| 4 · COPE | 32–34 | 3 |
| 5 · Limites | 35–42 | 7 |
| 6 · AIdIT + síntese | 43–51 | 7 |

**Se o tempo apertar**, estes cinco slides podem ser cortados sem quebrar o argumento: *O pano de fundo: integridade sob pressão* (6), *O custo invisível* (13), *Duas a mais que valem a pena conhecer* (23), *Limite 5* (40) e *Outras propostas na mesa* (47).

## Estrutura do repositório

```
index.qmd                     # os slides
custom.scss                   # tema reveal.js com a paleta do site (--bsl-*)
_quarto.yml                   # projeto Quarto, output-dir: docs
assets/qr-provetelab.png      # QR code do slide final (https://provetelab.org)
.github/workflows/publish.yml # render + deploy no GitHub Pages
```

## Como renderizar localmente

```bash
quarto render          # gera docs/index.html
quarto preview         # recarrega ao salvar
```

Não há chunks executáveis: o render precisa apenas do Quarto (sem R, sem Python).

## Publicação — fluxo completo

O repositório já está inicializado localmente, na branch `main`, com o primeiro commit feito. O que falta é criar o repositório remoto, habilitar o Pages e empurrar.

### 1. Conferir o estado local

```bash
cd "~/Library/CloudStorage/OneDrive-Pessoal/Aulas/Palestras esparsas minhas/palestra AI bio animal/ia-escrita-cientifica"

git status --short          # deve vir vazio
git log --oneline           # deve mostrar 1 commit em main
quarto render               # confirma que docs/index.html é gerado sem erro
```

### 2. Autenticar o `gh` (só na primeira vez nesta máquina)

```bash
gh auth status || gh auth login    # escolha GitHub.com → HTTPS → browser
```

### 3. Criar o repositório remoto e habilitar o Pages

A ordem importa: **habilite o Pages antes do primeiro push**.

```bash
REPO=ia-escrita-cientifica          # troque se quiser outro nome

gh repo create diogoprov/$REPO --public --source=. --remote=origin \
  --description "Palestra: IA na redação científica — ética, regras editoriais e boas práticas de reporte"

gh api -X POST repos/diogoprov/$REPO/pages -f build_type=workflow

git push -u origin main
```

`build_type=workflow` é o equivalente por API de **Settings → Pages → Source = "GitHub Actions"**. Se esse passo for pulado, o job `deploy` falha com `Failed to create deployment (status: 404)` — isso significa que o Pages nunca foi habilitado no repositório, e **não** um problema de permissão. Recuperação: habilite em Settings e clique em "Re-run jobs" (o artefato do build é reaproveitado).

### 4. Acompanhar o build e abrir a página

```bash
gh run watch                                   # acompanha o Actions ao vivo
gh run list --limit 3                          # histórico, se preferir
gh api repos/diogoprov/$REPO/pages --jq .html_url   # URL publicada
```

A URL padrão será `https://diogoprov.github.io/ia-escrita-cientifica/`.

### 5. Ciclo de edição, dali em diante

```bash
quarto preview              # recarrega ao salvar, para ajustar os slides
# (Ctrl+C para sair)

git add -A
git commit -m "Ajusta o bloco X"
git push                    # o Actions renderiza e publica sozinho
```

`docs/` está no `.gitignore`: a saída é construída pelo Actions, não versionada. Isso é **diferente** do repo do site (`diogoprov.github.io`), onde `docs/` precisa ficar versionado — não confunda os dois.

### Se quiser servir em `provetelab.org/ia-escrita-cientifica/`

Mesmo padrão das disciplinas migradas: adicione `site-url` ao `_quarto.yml` e crie o arquivo `CNAME`. Só faz sentido se você já tiver o DNS apontado para esse repositório.

### Nota sobre OneDrive

O repositório fica dentro do OneDrive. Para evitar `mmap failed: Operation timed out` no push e `Resource deadlock avoided` na leitura, marque a pasta como **"Always keep on this device"** no Finder. O OneDrive não aplica isso automaticamente a arquivos criados depois — reconfira se algum render falhar ao ler um arquivo.

## Licença

Não definida. Escolha uma antes de tornar o repositório público (sugestão usual para material didático: CC BY 4.0 para os slides).

## Declaração de uso de IA

O último slide traz a declaração de uso de IA generativa na preparação destes slides, no formato AIdIT (Drobniak et al. 2026, doi:10.1186/s41073-026-00230-1).
