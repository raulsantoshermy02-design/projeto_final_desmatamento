# Dashboard Sobre o Desmatamento dos Biomas Brasileiros

<p align="center">
  <img width="2667" height="220" alt="Captura de tela 2026-05-21 213747" src="https://github.com/user-attachments/assets/38d8ed5b-f164-4037-82d6-373b216aa8f5" />

</p>

---

## Fonte dos Dados / O Que é?				

Projeto MapBiomas – Coleção 10.1 da Série Anual de Mapas de Cobertura e Uso da Terra do Brasil, 
acessado em 11/05/2026 através do link: [MapBiomas_Brasil_Desmatamento](https://brasil.mapbiomas.org/download/estatisticas/)						

Projeto MapBiomas - é uma iniciativa multi-institucional para gerar mapas anuais de cobertura e uso da terra a partir de processos de classificação automática aplicada a imagens de satélite. 
A descrição completa do projeto encontra-se em http://mapbiomas.org							

---

## Sobre o Projeto
Este projeto apresenta uma análise abrangente de 40 anos de desmatamento nos biomas brasileiros, desenvolvida por meio de modelagem analítica avançada no Power BI. 
O objetivo é transformar dados históricos complexos em insights visuais estratégicos para apoiar o monitoramento ambiental e a tomada de decisão.

Funcionalidades do Dashboard:

> Análise Temporal: Evolução histórica do desmatamento ao longo das últimas quatro décadas.

> Comparação entre Biomas: Visão integrada para identificar o impacto relativo em cada região.

> Ranking de Estados: Identificação clara das unidades federativas com maiores índices de perda de vegetação.

> Monitoramento Regional: Detalhamento geográfico para análises localizadas.

> KPIs Executivos: Indicadores-chave de desempenho para uma leitura rápida e gerencial.

> Filtros Dinâmicos: Navegação interativa que permite a personalização de cenários e cruzamento de dados.

---

## KPI´s & Filtros

<img width="2366" height="471" alt="Captura de tela 2026-05-22 181909" src="https://github.com/user-attachments/assets/9d0414bf-bdb8-419e-8701-435ec95db275" />

## Evolução Ao Longo Do Tempo

<img width="3083" height="1098" alt="Captura de tela 2026-05-22 182021" src="https://github.com/user-attachments/assets/4c3901cf-4936-4be9-9c5b-062a4cdd9cc4" />

---

## Processamento e Modelagem de Dados

> 1. **Ingestão:** Importação dos dados históricos diretamente do **MapBiomas**.

> 2. **Normalização:** Transformação da base de *Wide* para *Long* utilizando a função *Unpivot* para otimização da performance.

> 3. **Tratamento Temporal:** Padronização e consistência da série histórica completa (**1985–2024**).

> 4. **Análise Quantitativa:** Desenvolvimento de métricas e inteligência de tempo utilizando **Medidas DAX**.

> 5. **Modelagem:** Estruturação analítica ideal para navegação interativa e relatórios de alta performance.

---

## Oportunidades de Expansão (Backlog)

O dashboard foi projetado com uma arquitetura escalável.

Abaixo estão algumas frentes de análise mapeadas como potenciais melhorias e caminhos que podem ser explorados no futuro:

| Status | Funcionalidade | Fonte/Tecnologia | Objetivo |
|---|---|---|---|
| ![Futuro](https://img.shields.io/badge/Futuro-purple) | Dados de Queimadas | INPE | Identificar correlações entre focos de incêndio e perda de vegetação |
| ![Futuro](https://img.shields.io/badge/Futuro-purple) | Mapas Customizados | Geoprocessamento Avançado | Melhorar a precisão geográfica na visualização dos biomas |
| ![Futuro](https://img.shields.io/badge/Futuro-purple) | Indicadores Econômicos | IBGE | Analisar os fatores financeiros e agrícolas que impulsionam o desmatamento |
| ![Futuro](https://img.shields.io/badge/Futuro-purple) | Visão ESG | Frameworks de Mercado | Adequar o dashboard para relatórios de sustentabilidade empresarial |

---

## Estrutura e Funcionalidades Técnicas do Dashboard
O modelo foi construído utilizando uma arquitetura de dados relacional que permite o cross-filtering (filtragem cruzada) integral entre três dimensões principais: Temporal, Geográfica e Categórica.

## 1. Visão Geral e Análise de Série Temporal
Esta interface atua como o Executive Summary (Resumo Executivo) do projeto, focando em indicadores macro e comportamento de tendência.

Cards de KPIs Centrais: Computam métricas agregadas via DAX, isolando o volume acumulado total (148,3 Mi de hectares), a taxa média anual de supressão (3,71 Mi ha/ano) e a identificação dinâmica do bioma mais impactado (Amazônia, com 42,7% do share total).

Análise de Variabilidade Temporal (YoY): Um card de contexto calcula a variação ano a ano, demonstrando que em 2024 houve uma desaceleração de -14,9% no ritmo de desmatamento em relação a 2023, totalizando 3,57 Mi de hectares no último período.

Gráfico de Linha com Preenchimento de Área: Plota a evolução cronológica anual. Tecnicamente, este visual permite identificar os picos históricos (como o teto observado próximo a 2004 com 5,7 Mi ha), os vales de controle (próximos a 2012 com 2,3 Mi ha) e a retomada da curva de inclinação nos anos recentes.

Painel de Filtros Contextuais (Slicers): Posicionados no topo (Bioma, Região e Estado), alteram o contexto de filtro de todo o modelo bi-direcionalmente.

## 2. Decomposição Volumétrica por Bioma e Classe
Esta visão aprofunda a análise dimensional, segregando o impacto volumétrico por ecossistema e tipologia de vegetação.

Gráfico de Colunas Clusterizadas (Desmatamento por Bioma): Executa uma análise de distribuição de volume, organizando os biomas em ordem decrescente. Evidencia visualmente que a Amazônia (63 Mi ha) e o Cerrado (47 Mi ha) operam como os principais drivers (ofensores) do indicador acumulado, seguidos por Caatinga, Mata Atlântica, Pampa e Pantanal.

Gráfico de Composição (Pizza): Introduz uma camada de análise qualitativa ao classificar a supressão entre Vegetação Primária (87%) e Vegetação Secundária (13%). Essa métrica é fundamental para auditorias ambientais, pois distingue o desmatamento de florestas nativas virgens (primária) do manejo de áreas já antropizadas (secundária).

## 3. Análise de Densidade Geográfica e Ranking Federativo
Focada na granularidade espacial dos dados, esta tela permite identificar gargalos regionais e mapear responsabilidades territoriais.

Gráfico de Barras Horizontais (Por Região): Consolida os dados em nível macro-geográfico, apontando a Região Norte (47,4 Mi ha) e Centro-Oeste (41,8 Mi ha) no topo do consumo de área, refletindo a atividade intensa nas franjas de expansão de fronteiras agrícolas.

Ranking de Unidades Federativas (Gráfico de Pareto/Barras Longitudinal): Plota de forma granular o comportamento de todos os estados. Visualmente, valida que os estados do Mato Grosso (27,9 Mi ha) e Pará (24,3 Mi ha) lideram isolados o ranking de perda de cobertura vegetal, permitindo ao usuário identificar instantaneamente onde o impacto está concentrado ao longo dos 40 anos.

---

 
