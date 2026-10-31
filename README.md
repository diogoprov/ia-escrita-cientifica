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

## Roteiro de tempo

São 65 slides, dos quais 7 são aberturas de bloco (5 s cada) e 6 são de apoio (referências e declaração de IA, normalmente não apresentados). Sobram **~52 slides** apresentáveis.

**Lição da primeira apresentação (out/2026):** as perguntas vieram no meio, não no fim, e custaram de 8 a 15 min. Num grupo engajado isso não sai de corte nenhum — o deck precisa caber em **~28 min de fala**, não em 38. Ou se anuncia no começo que as perguntas ficam para o fim de cada bloco.

**Versão curta (~42 slides).** Os slides marcados com **✂ opcional** no canto superior direito saem:

- *O pano de fundo: integridade sob pressão*
- *Quem faz o quê*
- *Por que estas cinco* (a justificativa bibliométrica da escolha das editoras; diga em uma frase sobre a tabela comparativa)
- *Taylor & Francis e Sage: o que muda* (detalhe editora-a-editora; o semáforo e os quatro usos já dão a regra)
- *Duas a mais que valem a pena conhecer* (Cambridge e OUP)
- *E se descumprir?* (sanções; a linha essencial já está em *Lendo a portaria com atenção*)
- *Por que o COPE importa mais que parece*
- *Limite 5 — o que você não percebe que perdeu*
- *Outras propostas na mesa* (Mehta, Park, DAISY)
- *E na tese? Não existe regra* (mantendo só o *Modelo para tese*)

A marca vem da classe `.opcional` no cabeçalho (`## Título {.smaller .opcional}`), estilizada em `custom.scss`. Para escondê-la, comente a regra `.reveal section.opcional::after`.

Os slides que **não** devem sair em nenhuma versão: *De onde eu falo* (declaração de conflito de interesses), *Os quatro usos que vocês de fato fazem*, *Responder ao parecerista*, *A taxonomia: estágio × tipo de uso*, *Modelo para tese e dissertação*, e o par *O contra-argumento* / *A resposta*.

### Fusões feitas na revisão pós-estreia

| Antes | Depois | Por quê |
|---|---|---|
| *O volume de submissões explodiu* + *E a triagem editorial acompanhou* | *O volume subiu — e a triagem foi junto* | Mesma fonte (ScholarOne), mesma mensagem, dois slides |
| *Elsevier: figuras e imagens* + *Wiley: a mesma linha, dita de outro jeito* | *Imagens: evidência não se melhora* | O título do segundo já admitia a repetição |
| *Limite 2 — o viés do corpus* | absorvido em *O problema de equidade tem dois lados* | Usavam a mesma citação da Wiley |
| *A portaria e as editoras: o que exige mais* | absorvido em *Lendo a portaria com atenção* | O cruzamento editora × CNPq já está, e melhor, em *Os quatro usos* |

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
