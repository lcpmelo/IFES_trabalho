# Atividade Prática 4: Manipulação e decisões de visualização de dados das IFES (1996–2026)

Análise da série histórica do investimento público e da força de trabalho nas Instituições Federais de Ensino Superior (IFES), com **pandas** (`groupby`, `agg`, `filter`, `apply`) e decisões de visualização justificadas com **seaborn** e **matplotlib**.

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

## Principais achados

- De 2014 a 2022 o investimento total caiu 35,6%, enquanto as vagas de estudantes cresceram 15,4%.
- A vaga de TAE passou a atender muito mais estudantes (de 15,0 em 2014 para 19,2 em 2026); a razão por docente ficou estável (13,5 → 14,1).
- A assistência por vaga de estudante em 2026 está 23,1% abaixo do patamar de 2014.
- Oito anos combinam corte ou estagnação da assistência com mais vagas: 2015–2020, 2022 e 2026.
