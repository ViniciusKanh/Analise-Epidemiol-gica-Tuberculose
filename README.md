# Análise Epidemiológica e Visualização de Dados — Tuberculose (MG)

Repositório **sem código**. O objetivo é disponibilizar **artefatos de visualização** e documentação técnica para leitura, verificação e comunicação de resultados.

---

## 1) Visão Geral
- Tema: epidemiologia da **tuberculose** em Minas Gerais (2001–2021).
- Entregáveis: **dashboard Power BI**, **mapa interativo (HTML)**, **relatório de perfilamento**, **figuras estáticas** (PNG), **apresentação** (PPTX) e **manuscrito** (PDF).
- Uso previsto: exploração descritiva, suporte a ensino, comunicação científica e decisões de saúde pública (nível descritivo).

---

## 2) Estrutura do Repositório
```
.
├── 0-Dataset/                      # Dados brutos e derivados (não publicar CSVs sensíveis/grandes)
├── 1-Pré Processamento/            # Produtos do EDA e organização dos insumos visuais
├── 2-Dashboard e Apresentação/     # Dashboard (.pbix) e slides (.pptx)
├── 3-Artigo/                       # Manuscrito e relatórios técnicos (PDF)
├── LICENSE
└── README.md
```

### Conteúdo esperado por pasta
- **0-Dataset/**
  - Dicionário de dados; metadados da fonte; snapshots de tabelas públicas.
  - *Boa prática*: não versionar arquivos muito grandes; preferir Git LFS ou link para fonte oficial.

- **1-Pré Processamento/**
  - **`tuberculose_profile_report.html`**: perfilamento automático (ydata‑profiling).
  - **`Analise dos Graficos.pdf`**: interpretação técnica das figuras.
  - **`mapa_tuberculose.html`**: mapa interativo (Folium).
  - **Figuras** (ex.: `Correlacao.png`, `Grafico_de_Radar.png`), prontos para citação em artigo/slide.

- **2-Dashboard e Apresentação/**
  - **`Dash-Tuberculose.pbix`**: relatório Power BI com navegação por sexo, idade, zona, desfecho e comorbidades.
  - **`Slides-*.pptx`**: apresentação para defesa/briefing executivo.

- **3-Artigo/**
  - **`Manuscrito_*.pdf`** e versões (`Analise de TB-VI.pdf`, `Analise-Tuberculose.pdf`).

---

## 3) Como Navegar (passo a passo)
1. **Dashboard**: abrir `2-Dashboard e Apresentação/Dash-Tuberculose.pbix` no **Power BI Desktop** (Windows).
2. **Mapa interativo**: abrir `1-Pré Processamento/mapa_tuberculose.html` em um navegador moderno.
3. **Perfilamento de dados**: abrir `1-Pré Processamento/tuberculose_profile_report.html` para estatísticas, tipos e alertas de qualidade.
4. **Figuras estáticas**: utilizar `1-Pré Processamento/*.png` em artigos, relatórios e slides (DPI ≥ 200).
5. **Manuscrito/relatórios**: consultar `3-Artigo/*.pdf` para contexto metodológico e discussão.

> *Observação:* este repositório não contém notebooks ou scripts. A reprodutibilidade de cálculos deve ser conduzida com base nos metadados, métodos e referências descritos no manuscrito e no relatório de gráficos.

---

## 4) Metodologia (resumo executivo)
- **Pré‑processamento**: padronização de tipos; tratamento de nulos e categorias “Ignorado”; harmonização temporal (2001–2021).
- **Agregações**: totais por mês/ano, sexo, faixa etária, zona e situação de encerramento (cura, abandono, óbito etc.).
- **Comorbidades**: indicadores para HIV, diabetes e outros agravos.
- **Visualização**:
  - **Heatmap de correlação** entre variáveis (apoia seleção de atributos e leitura de redundâncias).
  - **Radar mensal por desfecho** para sazonalidade/volume relativo.
  - **Mapa interativo** para variações espaciais e densidade de casos.
  - **Dashboard** para exploração guiada com filtros e segmentos.
- **Validação**: conferência de totais anuais, consistência de faixas etárias e campos críticos; discussão em `Analise dos Graficos.pdf` e no manuscrito.

---

## 5) Principais Achados (síntese)
- **Predominância masculina** e concentração em **adultos/idosos**.
- **Cura** como desfecho mais frequente; **abandono** e **óbitos** em menor proporção, porém relevantes.
- **Co‑infecção por HIV** e **diabetes** com impacto programático.
- **Maior concentração urbana** de notificações (associada à densidade populacional).
- Interpretações detalhadas e limitações: ver PDFs em `1-Pré Processamento/` e `3-Artigo/`.

---

## 6) Dados e Proveniência
- **Fonte principal**: dados públicos da Secretaria de Saúde/Estado de Minas Gerais (ver metadados em `0-Dataset/`).
- **Cobertura temporal**: 2001–2021.
- **Licença de dados**: respeitar termos do portal público; **não redistribuir** dados sensíveis/identificáveis.
- **Ética**: uso estritamente acadêmico/educacional; resultados são **descritivos** e não implicam causalidade.

---

## 7) Requisitos para Abertura de Arquivos
- **Power BI Desktop** para `.pbix`.
- **Navegador** atualizado para `.html` (mapa e perfilamento).
- **Leitor PDF** para relatórios/manuscrito.
- **Microsoft PowerPoint** (opcional) para `.pptx`.

---

## 8) Citação
```
Santos, V. (2024). Análise Epidemiológica e Visualização de Dados — Tuberculose (MG).
Repositório de artefatos visuais e documentação técnica.
```
BibTeX:
```bibtex
@misc{Santos2024TBViz,
  author = {Santos, Vinícius de Souza},
  title  = {Análise Epidemiológica e Visualização de Dados — Tuberculose (MG)},
  year   = {2024},
  note   = {Repositório de artefatos visuais e documentação técnica}
}
```

---

## 9) Contato e Afiliação
**Autor**: Vinícius de Souza Santos — UNESP/PPGC  
**E-mail**: vinicius-souza.santos@unesp.br

---

## 10) Licença
Este repositório está sob **MIT** (ver `LICENSE`). Artefatos de dados e conteúdos de terceiros seguem as respectivas licenças/origens.
