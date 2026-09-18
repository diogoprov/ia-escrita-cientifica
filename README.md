# IA na redação científica

Slides (Quarto + reveal.js) da palestra de 40 minutos **"IA na redação científica: ética, regras editoriais e boas práticas de reporte"**, de Diogo B. Provete (Instituto de Biociências, UFMS · [Biodiversity Synthesis Lab](https://provetelab.org)).

Publicado em **<https://provetelab.org/ia-escrita-cientifica/>**.

Público-alvo: pós-graduação e docentes.

## Conteúdo

| Bloco | Tema |
|---|---|
| 0 | O cenário: crescimento das submissões, prevalência de texto assistido por LLM, retratações |
| 1 | Ética: autoria, responsabilidade, equidade e formação |
| 2 | As políticas das cinco maiores editoras (Elsevier, Springer Nature, Wiley, Taylor & Francis, Sage) + Cambridge e OUP |
| 3 | Política de IA no mundo e a Portaria CNPq nº 2.664/2026 |
| 4 | A posição do COPE sobre autoria e ferramentas de IA |
| 5 | Limites dos LLMs e cuidados ao gerar texto científico |
| 6 | Boas práticas de reporte: o framework AIdIT |

Todas as citações literais de políticas e normas foram extraídas das páginas oficiais e dos PDFs originais; todos os DOIs e URLs foram verificados.

## Roteiro de tempo (40 min)

São 62 slides, dos quais 7 são aberturas de bloco (5 s cada) e 5 são de apoio (referências e declaração de IA, normalmente não apresentados). Sobram **~50 slides para ~38 min**, ou cerca de 45 s por slide — apertado de verdade: **ensaie ao cronômetro antes de decidir o que fica.**

| Bloco | Minutos |
|---|---|
| Abertura + roteiro | 2 |
| 0 · Cenário | 7 |
| 1 · Ética | 6 |
| 2 · Editoras | 9 |
| 3 · Política de IA + CNPq | 6 |
| 4 · COPE | 2 |
| 5 · Limites | 6 |
| 6 · AIdIT + síntese | 6 |

**Se o tempo apertar**, estes slides saem sem quebrar o argumento: *O pano de fundo: integridade sob pressão*, *Quem faz o quê*, *Duas a mais que valem a pena conhecer*, *Por que o COPE importa mais que parece*, *Limite 5* e *Outras propostas na mesa*. Cortando os seis, sobram ~44 slides.

Os dois slides que **não** deveriam sair, mesmo com o tempo curto, são *O contra-argumento que você vai ouvir* e *A resposta: declarar não é detectar*. São eles que impedem a palestra de virar propaganda do AIdIT — e é a pergunta que alguém da plateia vai fazer de qualquer jeito.

## Estrutura do repositório

```
index.qmd                     # os slides
custom.scss                   # tema reveal.js com a paleta do site (--bsl-*)
_quarto.yml                   # projeto Quarto, output-dir: docs, site-url
LICENSE                       # CC BY 4.0 + licenças das figuras de terceiros
assets/qr-provetelab.png      # QR code do slide final (https://provetelab.org)
assets/figs/                  # figuras reaproveitadas de artigos abertos
.github/workflows/publish.yml # render + deploy no GitHub Pages
```

## Como renderizar localmente

```bash
quarto render          # gera docs/index.html
quarto preview         # recarrega ao salvar
```

Não há chunks executáveis: o render precisa apenas do Quarto (sem R, sem Python).

`docs/` está no `.gitignore` — a saída é construída pelo GitHub Actions a cada push, não versionada. Isso é **diferente** do repo do site (`diogoprov.github.io`), onde `docs/` precisa ficar versionado.

## Licença

Os slides, o tema e este README estão sob **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.pt-br)**.

Atribuição sugerida:

> Provete DB (2026). *IA na redação científica: ética, regras editoriais e boas práticas de reporte.* <https://provetelab.org/ia-escrita-cientifica/> — CC BY 4.0

As figuras em `assets/figs/` vêm de artigos de acesso aberto e **mantêm as licenças dos originais** — duas delas são CC BY-NC-ND, mais restritivas que a deste repositório. O arquivo [`LICENSE`](LICENSE) detalha a procedência e a licença de cada figura.

## Declaração de uso de IA

O último slide traz a declaração de uso de IA generativa na preparação destes slides, no formato AIdIT (Drobniak et al. 2026, doi:10.1186/s41073-026-00230-1).
