# Análise Visual da Epidemiologia da Tuberculose em Minas Gerais

> Projeto de ciência de dados com foco em **visualização** e **insights epidemiológicos** a partir de dados abertos.

---

## 📌 Objetivos
- Consolidar dados públicos de tuberculose (MG) e produzir **visualizações explicativas** (mapas, gráficos e dashboard).
- Documentar um **pipeline reprodutível** (Python/Colab + Power BI) para EDA e storytelling de dados.
- Disponibilizar artefatos: **notebook**, **mapa interativo**, **relatório de perfilamento**, **gráficos** e **dashboard**.

## 🗂️ Estrutura do Repositório
```
.
├── data/                         # Dados brutos e tratados (não versionar grandes CSVs)
├── notebooks/
│   └── Analise-Tuberculose.ipynb # EDA e geração das figuras
├── reports/
│   ├── tuberculose_profile_report.html  # Perfilamento automático (ydata-profiling)
│   ├── Analise-dos-Graficos.pdf        # Interpretação textual das figuras
│   └── Manuscrito_Artigo.pdf           # Manuscrito técnico/acadêmico
├── dashboards/
│   └── Dash-Tuberculose.pbix           # Dashboard Power BI
├── docs/
│   ├── img/
│   │   ├── Correlacao.png
│   │   └── Grafico_de_Radar.png
│   └── mapa_tuberculose.html           # Mapa Folium (interativo)
├── slides/
│   └── Apresentacao-Tuberculose.pptx   # Deck de slides
├── requirements.txt
└── README.md
```

> **Observação**: mantenha arquivos grandes (CSV/Parquet/PBIX) fora do Git ou use Git LFS. Armazene credenciais via variáveis de ambiente.

## 📥 Dados
- **Fonte**: Portal de Dados Abertos do Governo de Minas Gerais.
- **Período**: 2001–2021 (informações demográficas, geográficas e clínicas).
- **Escopo**: casos notificados, variáveis clínicas (HIV, diabetes, baciloscopia etc.), desfechos (cura, abandono, óbito), sexo, faixa etária, raça/cor, município, zona.
- **Licença**: conforme o portal de dados (verifique termos antes de redistribuir).

## 🔧 Ambiente e Instalação
Requisitos mínimos:
- Python ≥ 3.10
- Power BI Desktop (para abrir o `.pbix`)

Crie e ative um ambiente virtual e instale as dependências:
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# Linux/macOS
# source .venv/bin/activate

pip install -U pip
pip install -r requirements.txt
```

### `requirements.txt` sugerido
```text
pandas>=2.2
numpy>=1.26
matplotlib>=3.8
plotly>=5.22
folium>=0.16
ydata-profiling>=4.8
geopandas>=1.0; platform_system != "Windows"  # opcional
pyarrow>=17.0
```

> **Dica**: se usar Google Colab, suba o notebook `notebooks/Analise-Tuberculose.ipynb` e aponte o caminho da pasta `data/` no início do notebook.

## ▶️ Reprodutibilidade (Passo a Passo)
1. **Obtenha os dados** no portal (CSV) e coloque em `data/raw/`.
2. **Execute o notebook** `notebooks/Analise-Tuberculose.ipynb` para:
   - limpeza e padronização (tipos, nulos, categorias);
   - geração do **perfilamento** (`reports/tuberculose_profile_report.html`);
   - produção das **figuras** (salvas em `docs/img/`);
   - exportação do **mapa Folium** (`docs/mapa_tuberculose.html`).
3. **Abra o dashboard** `dashboards/Dash-Tuberculose.pbix` no Power BI e aponte as fontes em `data/`.
4. **Valide** os resultados com o relatório `reports/Analise-dos-Graficos.pdf` e o **manuscrito**.

## 📊 Visualizações Principais
- **Heatmap de correlação** entre variáveis categóricas e clínicas.
  ![Heatmap de Correlação](docs/img/Correlacao.png)
- **Gráfico de Radar** por **situação de encerramento** (mensal).
  ![Gráfico de Radar](docs/img/Grafico_de_Radar.png)
- **Mapa interativo** (Folium) com municípios/clusterização: `docs/mapa_tuberculose.html`.
- **Dashboard Power BI** com navegação por sexo, idade, zona, desfecho e comorbidades.

## 🔍 Principais Achados (resumo)
- **Predominância masculina** nos casos notificados.
- **Adultos e idosos** concentrando maior incidência.
- **Cura** recorrente como desfecho majoritário; **abandono** e **óbito** existem, mas em menor proporção.
- **Co-infecção por HIV** e **diabetes** aparecem como **comorbidades relevantes** e exigem atenção programática.
- **Áreas urbanas** concentram maior número de casos, sugerindo relação com densidade populacional.

> *Interpretações completas e limitações* estão detalhadas em `reports/Analise-dos-Graficos.pdf` e no manuscrito técnico.

## ⚠️ Limitações e Ameaças à Validade
- Subnotificação e campos **“Ignorado/Não informado”** em variáveis críticas.
- Possíveis **mudanças de definição** ao longo dos anos (2001–2021).
- Ausência de variáveis socioeconômicas em parte do período.
- Visualizações **não implicam causalidade**; tratam-se de padrões e associações descritivas.

## 🧪 Testes e Qualidade
- Linters e formatação (opcional): `ruff`, `black`.
- Validações rápidas no notebook (consistência de faixas etárias, distribuição por sexo, totais por ano).
- Exportação controlada das figuras (DPI ≥ 200) e nomes de arquivo estáveis.

## 📝 Como Citar
Se utilizar este repositório, cite da seguinte forma:
```
Santos, V. (2024). Análise Visual da Epidemiologia da Tuberculose em Minas Gerais.
Repositório e materiais suplementares. Disponível em: <link do repositório>.
```
Ou em BibTeX:
```bibtex
@misc{Santos2024TuberculoseViz,
  author = {Santos, Vinícius de Souza},
  title  = {Análise Visual da Epidemiologia da Tuberculose em Minas Gerais},
  year   = {2024},
  note   = {Repositório e materiais suplementares}
}
```

## 📣 Contato
- Autor: **Vinícius de Souza Santos**
- E-mail: <seu-email@exemplo.com>
- Afiliação: UNESP — PPGC

## 📄 Licença
Este projeto está sob a licença **MIT**. Veja `LICENSE` para detalhes.
