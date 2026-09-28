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

São 71 slides, dos quais 7 são aberturas de bloco (5 s cada) e 5 são de apoio (referências e declaração de IA, normalmente não apresentados). Sobram **~59 slides**.

Em 38 minutos de fala isso dá **41 s por slide** — rápido demais para os slides que têm tabela ou citação longa. **A versão completa não cabe em 40 min.** O deck está montado para servir a dois formatos:

**Versão 40 min (~50 slides).** Corte estes nove, que não quebram o argumento. Eles estão marcados no deck com **✂ opcional** no canto superior direito — a marca vem da classe `.opcional` no cabeçalho do slide (`## Título {.smaller .opcional}`), estilizada em `custom.scss`. Para esconder a marca sem mexer no conteúdo, basta comentar a regra `.reveal section.opcional::after`.

- *O pano de fundo: integridade sob pressão* (retratações — a mensagem já está no bloco 0)
- *Quem faz o quê* (o semáforo cobre)
- *Duas a mais que valem a pena conhecer* (Cambridge e OUP)
- *Por que o COPE importa mais que parece*
- *Limite 2 — o viés do corpus* (já aparece no slide de equidade)
- *Limite 5 — o que você não percebe que perdeu*
- *O que esse caso ensina* (a crítica ao mecanismo do *Reviews in Aquaculture*; o slide anterior já entrega a regra)
- *Outras propostas na mesa* (Mehta, Park, DAISY)
- *E na tese? Não existe regra* (mantendo só o *Modelo para tese*)

**Versão 60 min ou aula:** tudo, com discussão.

## Onde esta palestra foi/será dada

- **Outubro de 2026** — reunião anual do PPG em Biologia Animal, UFMS, Campo Grande
- **Dezembro de 2026** — UNILA, Foz do Iguaçu

O slide de título **não traz data**: `date: today` imprimiria a data do render, que fica errada
na segunda apresentação, e qualquer texto livre no campo `date` faz o Quarto imprimir
*"Invalid Date"*. O local e a data são ditos em voz alta e ficam registrados aqui e em
[provetelab.org/talks.html](https://provetelab.org/talks.html).

**Para a UNILA, vale considerar:** o público de uma universidade de integração
latino-americana tende a ser mais diverso em língua materna, com hispanofalantes.
O slide *O problema de equidade tem dois lados* e o argumento de barreira linguística
(Amano et al. 2023) ganham peso ali — vale demorar mais nesses e menos na Portaria do CNPq,
que é regra brasileira e não se aplica a parte da audiência.

| Bloco | Minutos (versão 40) |
|---|---|
| Abertura + de onde eu falo + roteiro | 3 |
| 0 · Cenário | 6 |
| 1 · Ética | 5 |
| 2 · Editoras + os quatro usos + o contraexemplo | 10 |
| 3 · Política de IA + CNPq | 5 |
| 4 · COPE | 2 |
| 5 · Mapa dos termos + limites (inclui detecção) | 6 |
| 6 · AIdIT + tese + contra-argumento + síntese | 5 |

Os slides que **não** deveriam sair, mesmo com o tempo curto: *De onde eu falo* (declaração de conflito de interesses), *Antes de falar de limites: o mapa dos termos* (a plateia usa "IA", "LLM" e "ChatGPT" como sinônimos; sem o mapa, o bloco 5 inteiro fica ambíguo), *Os quatro usos que vocês de fato fazem*, *Responder ao parecerista*, *Modelo para tese e dissertação*, e o par *O contra-argumento* / *A resposta*. São eles que tornam a palestra acionável e impedem que ela vire propaganda do AIdIT.

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
