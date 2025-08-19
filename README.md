# Projeto Imigração Canadá

Este repositório documenta o que foi feito no **notebook `Projeto.ipynb`**: uma análise exploratória das **tendências de imigração para o Canadá** com foco em **Brasil** e **América do Sul**, usando o dataset público `imigrantes_canada.csv` (anos **1980–2013**).

---

## 📂 Dados utilizados
- **Arquivo:** `imigrantes_canada.csv`
- **Colunas principais:**
  - *País*, *Continente*, *Região*
  - Uma coluna por ano, de **1980** a **2013** (valores inteiros)
  - **Total** = soma dos anos 1980–2013
- **Subconjuntos analisados no notebook:**
  - Países **Brasil** e **Argentina**
  - Países da **Região = "América do Sul"**

---

## 🧪 Passo a passo do notebook (o que foi feito)

### 1) Preparação e leitura
- Importou bibliotecas: `pandas`, `matplotlib.pyplot`, `seaborn`, `plotly.express`, `plotly.graph_objs`.
- Leu o CSV com `pandas.read_csv`.
- Criou a lista de anos `anos = ["1980", ..., "2013"]`.
- Ajustou índice por país quando necessário: `df.set_index("País", inplace=True)`.

### 2) Seleções e dados derivados
- **Brasil**: série com valores anuais `df.loc["Brasil", anos]` → virou um `DataFrame` (`dados_brasil`) com colunas `ano` e `imigrantes`.
- **Argentina**: procedimento equivalente → `dados_argentina`.
- **América do Sul**: filtro `df.query('Região == "América do Sul"')`:
  - Ordenou por `Total` para ranking.
  - Removeu colunas *Continente* e *Região* e **transpôs** a tabela para ter **anos** como linhas e **países** como colunas (estrutura apropriada para séries temporais comparativas).

### 3) Visualizações geradas
**Matplotlib**
- **Linha – Brasil (1980–2013):** evolução anual com eixos rotulados, ticks a cada 5 anos e título contextualizado.
- **Linha dupla – Brasil × Argentina:** duas séries na mesma figura para comparação direta.
- **Grid 1×2:** Brasil e Argentina lado a lado (duas linhas, mesmas escalas/estética).

**Seaborn**
- **Ranking Top 10 mundial (Total 1980–2013):** `seaborn.barplot`, versão vertical e versão **horizontal** (melhor leitura de rótulos), com tema aplicado (`sns.set_theme`).
- **Ranking América do Sul (Total 1980–2013):** barras ordenadas do menor para o maior; **Brasil** destacado por cor (condicional) para facilitar identificação visual.

**Plotly (interativo)**
- **Linha interativa – Brasil:** série 1980–2013 com *hover* e zoom.
- **Linha interativa – Países da América do Sul:** DataFrame transposto (anos no eixo X), várias séries (um país por linha).
- **Exportação para HTML:** `imigracao_america_sul.html` (pode ser aberto no navegador).

### 4) Exportações de arquivo
- **PNG** do ranking da América do Sul: `Imigracao_america_sul.png`.
- **HTML** interativo (Plotly): `imigracao_america_sul.html`.

---

## 📊 Principais resultados (calculados no notebook)
- **Brasil (Total 1980–2013):** **29.659** pessoas.
- **Pico anual do Brasil:** **2.598** em **2010**.
- **Crescimento médio anual (CAGR) – Brasil 1980→2013:** **~6,55% a.a.**.
- **Argentina (Total 1980–2013):** **19.596**.
- **Soma de todos os países da América do Sul (Total):** **295.242**.

**Ranking (América do Sul – Total 1980–2013):**
1. **Guiana** — 75.785  
2. **Colômbia** — 72.088  
3. **Peru** — 32.652  
4. **Brasil** — 29.659  
5. **Chile** — 21.359  
6. **Venezuela** — 21.267  
7. **Argentina** — 19.596  

> *Observação:* Totais acima somam os anos **1980–2013**.

---

## 🗺️ Conclusões do notebook
- O **Brasil** apresenta **tendência de crescimento** no período, com pico em **2010**.
- No contexto da **América do Sul**, o Brasil fica **atrás de Guiana e Colômbia** no total acumulado 1980–2013.
- A comparação **Brasil × Argentina** mostra **Brasil acima** de Argentina na maioria dos anos, com aceleração nos anos 2000.

---

## ▶️ Como reproduzir rapidamente
1. Coloque o CSV em `data/raw/imigrantes_canada.csv`.
2. Abra `notebooks/Projeto.ipynb` no **Jupyter/VSCode/Colab**.
3. Execute as células em ordem (as figuras aparecem no notebook; quando previsto, arquivos **PNG** e **HTML** são salvos na raiz).

**Requisitos mínimos:**
pandas
matplotlib
seaborn
plotly
jupyter

yaml
Copiar
Editar

---

## 🧾 Créditos
Análise no notebook por **Paulo Vinicius de Almeida Figueiredo Medeiros**.  
Projeto acadêmico/aplicado
