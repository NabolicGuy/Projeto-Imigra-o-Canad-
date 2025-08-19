# Projeto Imigração Canadá

Análise exploratória de **tendências de imigração para o Canadá** com foco em **Brasil** e **América do Sul** (dados 1980–2013). O objetivo é gerar gráficos claros (Matplotlib, Seaborn e Plotly) e um resumo rápido para apoiar decisões e apresentar resultados.

---

## 📂 Dados
**Arquivo:** `imigrantes_canada.csv`  
**Colunas principais:**
- `País`, `Continente`, `Região`
- Anos `1980` … `2013` (uma coluna por ano)
- `Total` (soma de 1980–2013)

> Coloque o CSV em `data/raw/imigrantes_canada.csv`.

---

## 🧪 O que foi feito
1. **Leitura e preparo**
   - Carregamento do CSV com `pandas`.
   - Definição da lista de anos (`1980`–`2013`) e, quando necessário, uso de `País` como índice.
   - Seleções por país (Brasil/Argentina) e por região (**América do Sul**).

2. **Análises**
   - **Série temporal (Brasil):** evolução anual 1980–2013.
   - **Comparativo Brasil × Argentina:** duas séries na mesma figura.
   - **Ranking América do Sul:** barras ordenadas por `Total` no período.
   - **Top 10 mundial:** barras com `seaborn.barplot`.

3. **Visualizações**
   - **Matplotlib:** linhas e barras com títulos, rótulos, ticks e anotações.
   - **Seaborn:** estilização (tema) e barra horizontal dos “Top 10”.
   - **Plotly (interativo):** linha animada (time-series) para Brasil e Argentina.

4. **Exportação**
   - PNG do ranking da América do Sul: `Imigracao_america_sul.png`
   - HTML interativo (Plotly): `imigracao_america_sul.html`

---

## 📊 Resultados-chave (1980–2013)
- **Brasil (total 1980–2013):** **29.659** pessoas  
- **Pico do Brasil:** **2.598** em **2010**  
- **Crescimento médio anual (CAGR) Brasil 1980→2013:** **~6,55% a.a.**  
- **Argentina (total):** **19.596**  
- **Total da América do Sul:** **295.242**

**Top países da América do Sul (por total no período):**
- Guiana: 75.785  
- Colômbia: 72.088  
- Peru: 32.652  
- **Brasil: 29.659**  
- Chile: 21.359  
- Venezuela: 21.267  
- Argentina: 19.596  

> Observação: valores somados para **1980–2013**.

---

## ▶️ Como rodar
1) **Clonar e entrar na pasta**
```bash
git clone https://github.com/NabolicGuy/Projeto-Imigracao-Canada.git
cd Projeto-Imigracao-Canada
