# Saúde Mental no Brasil: Uma Análise Exploratória

[![Python](https://img.shields.io/badge/Python-3.10+-blue)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.x-green)](https://pandas.pydata.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)](https://powerbi.microsoft.com)

## Status do projeto

🟡 Em desenvolvimento

| Etapa | Status |
|---|---|
| Coleta e limpeza dos dados | ✅ Concluído |
| Análise exploratória — DATASUS | ✅ Concluído |
| Análise exploratória — PNS 2019 | 🔄 Em finalização |
| Dashboard Power BI | 🔄 Em finalização |
| Documentação dos achados | 🔄 Em andamento |

---

## Sobre o projeto

Análise exploratória do perfil epidemiológico dos transtornos mentais no Brasil,
combinando dados de prevalência (PNS 2019/IBGE) e internações hospitalares
(SIH/SUS DATASUS, 2015–2024).

## Pergunta de pesquisa

Como variáveis sociodemográficas (sexo, faixa etária, região) se associam
à prevalência de depressão e ao padrão de internações psiquiátricas no Brasil?

---

## Fontes de dados

| Fonte | Período | Acesso |
|---|---|---|
| PNS 2019 — IBGE | 2019 | [Link](https://www.ibge.gov.br/estatisticas/sociais/saude/9160-pesquisa-nacional-de-saude.html) |
| SIH/SUS — DATASUS | 2015–2024 | [Link](https://datasus.saude.gov.br/informacoes-de-saude-tabnet/) |

> Os dados brutos não estão incluídos neste repositório devido ao tamanho dos arquivos.
> Consulte os links acima e o notebook `01_coleta_dados.ipynb` para reproduzir a análise.

---

## Estrutura do projeto

```
saude-mental-brasil/
├── data/
│   ├── raw/                  ← arquivos originais (não versionados)
│   └── processed/            ← dados após limpeza
├── notebooks/
│   ├── 01_coleta_dados.ipynb
│   ├── 02_limpeza_tratamento.ipynb
│   ├── 03_analise_datasus.ipynb
│   └── 04_analise_pns.ipynb
├── outputs/
│   └── figures/              ← gráficos gerados
├── dashboard-saude-mental.pbix
├── requirements.txt
└── README.md
```

---

## Principais achados

1. A prevalência geral de diagnóstico de depressão no Brasil em 2019 foi de aproximadamente **9,2%**, segundo a PNS 2019 (IBGE).

2. Mulheres apresentam prevalência de **13,3%** — aproximadamente 3 vezes maior que a dos homens (4,6%), padrão consistente com a literatura epidemiológica em saúde mental.

3. A prevalência de depressão aumenta com a idade, atingindo o pico na faixa de **50–59 anos (12,3%)**, com leve redução nas faixas seguintes.

4. Observa-se um **declínio nas internações por transtornos mentais em 2020–2021**, possivelmente relacionado à pandemia de COVID-19, que pode ter impactado o acesso a serviços de saúde mental e a priorização de notificações hospitalares.

5. A **região Sudeste** concentra o maior volume de internações psiquiátricas no período (2015–2024), porém é a região com maior densidade populacional. Esse achado merece investigação adicional, considerando fatores como densidade populacional, cobertura de serviços especializados e subnotificação em outras regiões (ex: Norte, região com menor número registrado).

---

## Notas Metodológicas

### Prevalência vs. Distribuição — gráficos de depressão por sexo

Dois tipos de cálculo foram utilizados na análise e é importante distingui-los:

**Prevalência por grupo (usado no Python):**
Calcula a proporção de pessoas com diagnóstico *dentro de cada grupo*.
Fórmula: `diagnosticados(grupo) / total(grupo)`
Exemplo: 13,3% das mulheres entrevistadas relataram diagnóstico de depressão.

**Distribuição do total (gerada automaticamente no Power BI):**
Calcula quanto cada grupo representa *do total de diagnosticados*.
Fórmula: `diagnosticados(grupo) / total de diagnosticados (ambos os sexos)`
Exemplo: mulheres representam 52,89% de todos os casos diagnosticados.

Ambos os cálculos são válidos, mas respondem perguntas diferentes.
Este projeto adota a **prevalência por grupo** como métrica principal,
por ser a medida padrão em estudos epidemiológicos de saúde mental.

---

## Visualizações

### Internações por Transtornos Mentais (2015–2024)
![Serie Temporal](outputs/figures/01_serie_temporal_internacoes.png)

### Internações por Região (2015–2024)
![Internações por Região](outputs/figures/02_internacoes_por_regiao.png)

### Prevalência de Depressão por Sexo — PNS 2019
![Depressão por Sexo](outputs/figures/03_depressao_por_sexo.png)

### Prevalência de Depressão por Faixa Etária — PNS 2019
![Depressão por Faixa Etária](outputs/figures/04_depressao_por_faixa_etaria.png)

---

## Como reproduzir

```bash
pip install -r requirements.txt
jupyter notebook
```

---

## Tecnologias

Python | pandas | matplotlib | seaborn | Power BI

---

## Autora

Desiree Daphine — [LinkedIn](https://www.linkedin.com/in/desiree-daphine/) | [Lattes](http://lattes.cnpq.br/2522194140416829)
