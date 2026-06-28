## Status do projeto

🟡 Em desenvolvimento

| Etapa | Status |
|---|---|
| Coleta e limpeza dos dados | ✅ Concluído |
| Análise exploratória — DATASUS | ✅ Concluído |
| Análise exploratória — PNS 2019 | ✅ Concluído |
| Dashboard Power BI | 🔄 Em finalização |
| Documentação dos achados | 🔄 Em andamento |


# Rascunho do Projeto:


## Saúde Mental no Brasil: Uma Análise Exploratória

[![Python](https://img.shields.io/badge/Python-3.10+-blue)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.x-green)](https://pandas.pydata.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)](https://powerbi.microsoft.com)

## Sobre o projeto

Análise exploratória do perfil epidemiológico dos transtornos mentais no Brasil,
combinando dados de prevalência (PNS 2019/IBGE) e internações hospitalares
(SIH/SUS DATASUS, 2015–2024).

## Pergunta de pesquisa

Como variáveis sociodemográficas (sexo, faixa etária, região) se associam
à prevalência de depressão e ao padrão de internações psiquiátricas no Brasil?

## Fontes de dados

| Fonte | Período | Acesso |
|---|---|---|
| PNS 2019 — IBGE | 2019–2020 | [Link](https://www.ibge.gov.br/estatisticas/sociais/saude/9160-pesquisa-nacional-de-saude.html) |
| SIH/SUS — DATASUS | 2015–2024 | [Link](https://datasus.saude.gov.br/informacoes-de-saude-tabnet/) |

> Os dados brutos não estão incluídos neste repositório.
> Consulte os links acima e o notebook `01_coleta_dados.ipynb` para reproduzir.

## Estrutura do projeto

\```
saude-mental-brasil/
├── data/processed/        ← dados após limpeza
├── notebooks/             ← análises em Jupyter Notebook
├── outputs/figures/       ← gráficos gerados
├── dashboard_saude_mental.pbix
└── requirements.txt
\```

## Principais achados
(Rascunhos dos achados):

1. Há uma prevalência no diagnóstico de depressão em mulheres na faixa etárias de 50-59 anos.
2. Em homens a prevalência é menor chegando a 4,6%
3. Há um declínio na notificação de internações por transtornos mentais nos anos de 2020-2021, possivimente por conta da pandemia de COVID-19, devido ao aumento de casos, o sistema pode ter privilegiado a notificação por internações do vírus
4. A região sudeste possui um número expressivo de internações ao longo dos anos de 2015 a 2024 (interessante investigar o provável motivo, talvez com pesquisas de revisão?)
5. A prevalência geral de diagnóstico de depressão nos anos de 2015-2024 no Brasil de aproximadamente 9,17%

[Preencher após concluir a análise]

## Notas Metodológicas

### Prevalência vs. Distribuição — gráficos de depressão por sexo

Dois tipos de cálculo diferentes foram utilizados na análise e
é importante distingui-los:

**Prevalência por grupo (usado no Python):**
Calcula a proporção de pessoas com diagnóstico *dentro de cada grupo*.
Fórmula: diagnosticados(grupo) / total(grupo)
Exemplo: 13,3% das mulheres entrevistadas relataram diagnóstico de depressão.

**Distribuição do total (gerada automaticamente no Power BI):**
Calcula quanto cada grupo representa *do total de diagnosticados*.
Fórmula: diagnosticados(grupo) / total de diagnosticados (ambos os sexos)
Exemplo: mulheres representam 52,89% de todos os casos diagnosticados.

Ambos os cálculos são válidos, mas respondem perguntas diferentes.
Este projeto adota a **prevalência por grupo** como métrica principal,
por ser a medida padrão em estudos epidemiológicos de saúde mental.

> Fonte de referência para prevalência: PNS 2019 — IBGE.

## Referências Bibliográficas



## Visualizações

![Prevalência de Intenações]("../data/outputs/figures/01_serie_temporal_internacoes.png")

<img src="..data/outputs/figures/01_serie_temporal_internacoes.png" alt= "Teste" width="500">




## Como reproduzir

\```bash
pip install -r requirements.txt
jupyter notebook
\```

## Tecnologias

Python | pandas | matplotlib | seaborn | Power BI

## Autora

Desiree Daphine — [LinkedIn](https://www.linkedin.com/in/desiree-daphine/?skipRedirect=true) | [Lattes](http://lattes.cnpq.br/2522194140416829)