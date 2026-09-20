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

São 68 slides, dos quais 7 são aberturas de bloco (5 s cada) e 5 são de apoio (referências e declaração de IA, normalmente não apresentados). Sobram **~56 slides**.

Em 38 minutos de fala isso dá **41 s por slide** — rápido demais para os slides que têm tabela ou citação longa. **A versão completa não cabe em 40 min.** O deck está montado para servir a dois formatos:

**Versão 40 min (~48 slides).** Corte estes oito, que não quebram o argumento. Eles estão marcados no deck com **✂ opcional** no canto superior direito — a marca vem da classe `.opcional` no cabeçalho do slide (`## Título {.smaller .opcional}`), estilizada em `custom.scss`. Para esconder a marca sem mexer no conteúdo, basta comentar a regra `.reveal section.opcional::after`.

- *O pano de fundo: integridade sob pressão* (retratações — a mensagem já está no bloco 0)
- *Quem faz o quê* (o semáforo cobre)
- *Duas a mais que valem a pena conhecer* (Cambridge e OUP)
- *Por que o COPE importa mais que parece*
- *Limite 2 — o viés do corpus* (já aparece no slide de equidade)
- *Limite 5 — o que você não percebe que perdeu*
- *Outras propostas na mesa* (Mehta, Park, DAISY)
- *E na tese? Não existe regra* (mantendo só o *Modelo para tese*)

**Versão 60 min ou aula:** tudo, com discussão.

| Bloco | Minutos (versão 40) |
|---|---|
| Abertura + de onde eu falo + roteiro | 3 |
| 0 · Cenário | 6 |
| 1 · Ética | 5 |
| 2 · Editoras + os quatro usos | 9 |
| 3 · Política de IA + CNPq | 5 |
| 4 · COPE | 2 |
| 5 · Limites (inclui detecção) | 5 |
| 6 · AIdIT + tese + contra-argumento + síntese | 5 |

Os slides que **não** deveriam sair, mesmo com o tempo curto: *De onde eu falo* (declaração de conflito de interesses), *Os quatro usos que vocês de fato fazem*, *Responder ao parecerista*, *Modelo para tese e dissertação*, e o par *O contra-argumento* / *A resposta*. São eles que tornam a palestra acionável e impedem que ela vire propaganda do AIdIT.

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
