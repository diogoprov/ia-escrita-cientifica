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

## Publicação

O deploy é feito pelo GitHub Actions. **Antes do primeiro push**, habilite o Pages com origem "GitHub Actions":

```bash
gh repo create diogoprov/<nome-do-repo> --public --source=. --remote=origin
gh api -X POST repos/diogoprov/<nome-do-repo>/pages -f build_type=workflow
git push -u origin main
```

Sem esse passo, o job `deploy` falha com `Failed to create deployment (status: 404)` — o que significa que o Pages nunca foi habilitado para o repositório, e não um problema de permissão.

`docs/` está no `.gitignore`: a saída é construída pelo Actions, não versionada.

## Licença

Não definida. Escolha uma antes de tornar o repositório público (sugestão usual para material didático: CC BY 4.0 para os slides).

## Declaração de uso de IA

O último slide traz a declaração de uso de IA generativa na preparação destes slides, no formato AIdIT (Drobniak et al. 2026, doi:10.1186/s41073-026-00230-1).
