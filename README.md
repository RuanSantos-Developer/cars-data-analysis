🚗 Automotive Data Pipeline & Market Intelligence 2025
Este repositório hospeda uma solução completa de Data Pipeline (ETL) e Análise Exploratória de Dados (EDA) focada no setor automotivo global de 2025. O projeto simula um cenário real de inteligência de mercado, onde dados brutos e não estruturados são transformados em ativos estratégicos para análise de performance, precificação e competitividade entre marcas premium e populares.

<p align="center">
<img src="images/banner.png" alt="Banner do Projeto" width="100%">
</p>

📌 Arquitetura e Visão Geral
O core deste projeto é a conversão de Raw Data (dados brutos) com inconsistências de encoding e formatação em um dataset higienizado e pronto para modelagem preditiva ou visualização em Dashboards.

🛠 Etapas do Pipeline:
Ingestão e Tratamento de Encoding: Superação de barreiras de leitura de arquivos legados (ANSI/cp1252), garantindo a integridade dos caracteres especiais e símbolos monetários.

Data Cleaning & Standardizing: Normalização de campos complexos, convertendo strings de mercado (ex: $1,100,000 e 963 hp) em tipos numéricos (float/int), permitindo cálculos estatísticos precisos.

Feature Engineering: Desenvolvimento de KPIs de negócio, como o índice de Custo-Eficiência (HP por Preço), para identificar anomalias de mercado e oportunidades de investimento.

Análise Estatística Multivariada: Estudo de correlações entre potência, cilindrada, velocidade máxima e curvas de depreciação.


## 📊 Detalhamento dos Gráficos e Insights

Nesta seção, detalhamos as visualizações geradas no notebook `pipeline-cars.ipynb`, focando nos insights de negócio e engenharia.

### 1. Top 10 Custo-Benefício (Potência por Preço)
Este gráfico utiliza uma métrica customizada, **HP per Price**, calculada para identificar a eficiência entre performance e custo.

<p align="center">
  <img src="images/top10_hp_price.png" alt="Gráfico Top 10 Custo-Benefício" width="80%">
</p>

* **O que ele explica:** Mostra quais modelos entregam a maior "força bruta" (cavalaria) para cada dólar investido.
* **Insight:** Marcas de performance "de entrada" ou esportivos tradicionais muitas vezes superam hipercarros de luxo nesta métrica, pois o preço destes últimos cresce exponencialmente em relação ao ganho de potência real.

### 2. Distribuição de Preços por Tipo de Combustível
<p align="center">
  <img src="images/price_dist_fuel.png" alt="Distribuição de Preços por Combustível" width="80%">
</p>

* **O que ele explica:** Compara as faixas de preço e a densidade de modelos entre carros a Gasolina (Petrol), Híbridos e Elétricos no cenário de 2025.
* **Insight:** Permite analisar a paridade de preços entre as tecnologias. Em 2025, observamos se o segmento elétrico/híbrido já se consolidou em faixas de preço competitivas com os motores a combustão tradicionais.

### 3. Matriz de Correlação (Heatmap)
Esta é a visualização final do pipeline, mostrando como todas as variáveis numéricas se relacionam entre si.

<p align="center">
  <img src="images/heat-map.png" alt="Heatmap de Correlação" width="80%">
</p>

* **O que ele explica:** Um mapa de calor onde cores fortes (próximas de 1 ou -1) indicam forte relação entre duas variáveis.
* **Insight Profissional:**
    * **Correlação Positiva Forte:** Identificamos que `HorsePower` e `Price` possuem forte correlação, o que é esperado.
    * **Correlação Negativa Forte:** Validamos a eficiência mecânica; `HorsePower` tem forte correlação negativa com `Performance (0-100 km/h)`, confirmando que mais potência resulta em menor tempo de aceleração.
    * Este mapa ajuda a selecionar as melhores *features* (variáveis) para futuros modelos de Machine Learning de previsão de preço.🛠️ Tecnologias e FerramentasPandas: Manipulação e limpeza de dados complexos.Matplotlib/Seaborn: Geração de gráficos estatísticos com a paleta magma.Tratamento de Encoding: O pipeline foi robustecido para ler arquivos cp1252 e latin1.🚀 Como ExecutarClone o repositório:Bashgit clone https://github.com/seu-usuario/nome-do-repo.git
  Certifique-se de ter as imagens na pasta:O código do README espera que os gráficos salvos estejam em /images.Rode o Pipeline:Abra o pipeline-cars.ipynb no Jupyter e execute todas as células. O dataset limpo será gerado automaticamente como cars_cleaned_final.csv.📂 Estrutura de PastasPlaintext├── Cars Datasets 2025.csv # Dados brutos
  ├── pipeline-cars.ipynb # Código da análise
  ├── cars_cleaned_final.csv # Dados após o ETL
  ├── README.md # Documentação
  └── images/ # Gráficos e assets
  Análise realizada por Ruan. 🏎️💨[Seu LinkedIn] | [Seu Portfólio]
