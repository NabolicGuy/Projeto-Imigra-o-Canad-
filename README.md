# Projeto Imigração Canadá

Um repositório simples e direto para mostrar o mini‑projeto de análise de **tendências de imigração do Brasil e América do Sul para o Canadá**. A ideia é que qualquer pessoa consiga abrir, rodar e ver os resultados rapidamente.

---

## 🔎 Visão geral

Este projeto explora dados públicos de imigração para entender **tendências por ano, país de origem e região**, com foco no **Brasil** e na **América do Sul**. O trabalho inclui:

* Limpeza e preparo dos dados (tratamento de colunas, padronização de nomes e datas).
* Análises descritivas (crescimento ao longo do tempo, variações sazonais, top países).
* Visualizações com **Matplotlib**, **Seaborn** e **Plotly** (linhas, barras, mapas/treemaps quando aplicável).
* Pequenas conclusões e insights prontos para apresentação.

> **Formato do projeto:** notebook principal pronto para abrir no Jupyter/Colab e scripts opcionais em `src/` para modularizar etapas.

---

## ✅ O que você encontra aqui

* `notebooks/Projeto.ipynb` — Notebook principal com toda a análise passo a passo (comentada e didática).
* `data/` — Pasta para os dados (brutos e processados). **Não versionamos arquivos grandes**; ver instruções abaixo.
* `src/` — Scripts utilitários (carregamento, limpeza, gráficos) para quem preferir rodar a análise via Python.
* `reports/figures/` — Imagens geradas pelos notebooks/scripts.
* `requirements.txt` — Dependências mínimas para rodar localmente.
* `README.md` — Este guia rápido.

---

## 🗂️ Estrutura sugerida

```
Projeto-Imigracao-Canada/
├── README.md
├── requirements.txt
├── notebooks/
│   └── Projeto.ipynb
├── src/
│   ├── __init__.py
│   ├── utils_io.py         # leitura/escrita de dados
│   ├── preprocess.py       # limpeza e padronização
│   └── viz.py              # funções de gráficos
├── data/
│   ├── raw/                # datasets originais (local, não versionado)
│   └── processed/          # saídas limpas (local, não versionado)
└── reports/
    └── figures/            # imagens salvas
```

---

## 📦 Dataset

* **Nome:** (ex.) `imigracao_canada_america_sul.csv`
* **Origem:** base pública/aberta. Se o arquivo for grande, **não suba no Git**; mantenha em `data/raw/` localmente.
* **Dicionário mínimo:**

  * `ano` (int) — ano de referência
  * `pais_origem` (str) — país de origem do imigrante
  * `regiao_origem` (str) — ex.: América do Sul
  * `quantidade` (int) — contagem de entradas/aprovações (conforme fonte)

> Caso use outra estrutura de colunas, ajuste os nomes nas funções de `src/preprocess.py` e nos trechos do notebook.

---

## ▶️ Como rodar

1. **Clonar e entrar na pasta**

```bash
git clone https://github.com/SEU_USUARIO/Projeto-Imigracao-Canada.git
cd Projeto-Imigracao-Canada
```

2. **Criar ambiente e instalar dependências**

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
```

3. **Colocar o dataset localmente**

* Salve o(s) CSV(s) em `data/raw/`.

4. **Rodar o notebook**

* Abra `notebooks/Projeto.ipynb` no Jupyter/VSCode/Colab e execute as células.

> Também é possível rodar via scripts em `src/` (ex.: `python -m src.preprocess`).

---

## 🔧 Requisitos (requirements.txt)

Exemplo mínimo de dependências:

```
pandas
numpy
matplotlib
seaborn
plotly
```

Inclua `jupyter` se for rodar localmente fora do Colab.

---

## 📊 Principais análises (no notebook)

* **Série temporal**: evolução anual de imigração do Brasil e comparação com América do Sul.
* **Ranking por país**: top países sul‑americanos por volume.
* **Participação relativa**: participação do Brasil dentro da região.
* **Variações**: crescimento/queda por períodos (CAGR, dif. absoluta e relativa).

---

## 💡 Insights & conclusões (exemplos)

* Tendência de **crescimento**/estabilidade/queda no período X–Y.
* O Brasil aparece entre os **top N** países da região em Z anos.
* Mudanças relevantes em anos específicos possivelmente ligadas a **fatores econômicos/políticos** (contextualizar no notebook).

> Os insights finais estão resumidos no fim do notebook e ilustrados em `reports/figures/`.

