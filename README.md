# Atividade Prática 4 — Manipulação e decisões de visualização de dados das IFES (1996–2026)

Disciplina **Ferramentas para Data Science** · DCOMP/UFSJ · Profa. Carolina Xavier

Análise da série histórica do investimento público e da força de trabalho nas Instituições Federais de Ensino Superior (IFES), com **pandas** (`groupby`, `agg`, `filter`, `apply`) e decisões de visualização justificadas com **seaborn** e **matplotlib**.

O entregável principal é o notebook [`atividade_pratica_4_ifes.ipynb`](atividade_pratica_4_ifes.ipynb): ele já está executado, então as figuras e o texto aparecem direto aqui no GitHub. O resumo das decisões de visualização, as conclusões e as limitações estão na seção final do notebook.

## Como reproduzir

```bash
conda env create -f environment.yml
conda activate ifes-viz
jupyter lab atividade_pratica_4_ifes.ipynb
```

O `environment.yml` fixa as versões de pandas 3.0.5, numpy 2.5.3, matplotlib 3.11.2 e seaborn 0.13.2.

## Estrutura

```
├── atividade_pratica_4_ifes.ipynb   # código + justificativas em Markdown
├── data/dados_investimento_e_vagas_ifes.csv
├── figuras/                         # PNGs gerados pelo notebook
├── environment.yml
└── README.md
```

## Decisões de visualização (resumo)

| Figura | Pergunta | Escolha |
|---|---|---|
| 1 | Evolução do investimento total e das vagas | dois painéis de linha, x compartilhado, y independente (sem eixo duplo) |
| 2 | Por que não eixo único/duplo? | evidência das alternativas descartadas |
| 3 | Estudantes por docente e por TAE | um painel, duas linhas, mesmo eixo y |
| 4 | Heatmap de correlação serve? | não — correlação espúria e dependente do recorte |
| 5 | A assistência acompanhou as vagas? | *bubble chart* com trajetória e linha de proporção |
| 6 | Anos críticos da assistência estudantil | marcadores destacados (cor + forma) e barras de novas vagas |
| 7 | Fase institucional de cada ano | paleta divergente (`sns.diverging_palette`) sobre categorias ordenadas |

## Principais achados

- De 2014 a 2022 o investimento total caiu 35,6%, enquanto as vagas de estudantes cresceram 15,4%.
- A vaga de TAE passou a atender muito mais estudantes (de 15,0 em 2014 para 19,2 em 2026); a razão por docente ficou estável (13,5 → 14,1).
- A assistência por vaga de estudante em 2026 está 23,1% abaixo do patamar de 2014.
- Oito anos combinam corte ou estagnação da assistência com mais vagas: 2015–2020, 2022 e 2026.

![Evolução](figuras/01_evolucao_investimento_vagas.png)

![Bubble chart](figuras/05_bubble_assistencia_vs_vagas.png)

## Observações sobre os dados

- O CSV não informa a fonte nem se os valores monetários são correntes ou constantes. Eles foram usados **como fornecidos**; comparações de longo prazo exigiriam deflacionar.
- 2026 é o ano corrente: se for estimativa, as conclusões sobre o último ano são provisórias.
- Os mandatos são recortes de calendário, sem atribuição causal a governos.
