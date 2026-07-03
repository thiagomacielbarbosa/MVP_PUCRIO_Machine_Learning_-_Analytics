# 🛒 MVP: Segmentação de Clientes e Perfis de Consumo (Clusterização)

Este repositório contém o MVP (Minimum Viable Product) desenvolvido como requisito de avaliação para a **Pós-Graduação em Engenharia de Dados**. O objetivo principal do projeto é aplicar técnicas de **Machine Learning Não Supervisionado** para agrupar clientes de um e-commerce com base em seus comportamentos de compra, transformando dados transacionais brutos em inteligência estratégica de negócios.

---

## 🎯 O Problema
No cenário do varejo contemporâneo, entender o comportamento do consumidor é um diferencial competitivo. Campanhas de marketing genéricas possuem baixo engajamento e alto custo. Este projeto resolve o problema da segmentação estática ao criar uma clusterização automatizada baseada na **Matriz RFM** (Recência, Frequência e Valor Monetário), permitindo que áreas de negócio criem campanhas direcionadas para perfis específicos (ex: fidelização de clientes VIPs ou reativação de clientes dormentes).

---

## 📊 O Dataset
Foi utilizado o **Online Retail Dataset**, hospedado no [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail). 
* **Volume:** Mais de 540.000 registros transacionais brutos.
* **Características:** Dados reais de um e-commerce do Reino Unido (notas fiscais, códigos de produtos, quantidades, datas e IDs de clientes).

---

## ⚙️ Tecnologias e Ferramentas Utilizadas
* **Linguagem:** Python 3
* **Manipulação e Limpeza de Dados:** Pandas, NumPy
* **Visualização de Dados:** Matplotlib, Seaborn, Plotly (Gráficos 3D interativos)
* **Machine Learning:** Scikit-Learn (K-Means, StandardScaler)
* **Ambiente de Desenvolvimento:** Google Colab / Jupyter Notebook

---

## 🚀 Metodologia Aplicada

O desenvolvimento seguiu o fluxo clássico de um projeto de Data Science / Data Engineering:

1. **Extração e Limpeza:** Download automatizado da base, remoção de registros sem `CustomerID`, filtragem de estornos (quantidades negativas) e transações zeradas.
2. **Engenharia de Atributos (Feature Engineering):** Agrupamento de mais de 390.000 linhas transacionais em uma base consolidada por cliente através da **Matriz RFM**:
   * **R (Recency):** Dias desde a última compra.
   * **F (Frequency):** Número de pedidos únicos.
   * **M (Monetary):** Valor total gasto (£).
3. **Pré-processamento:** Aplicação de Transformação Logarítmica (`np.log1p`) para normalizar a assimetria (cauda longa) dos dados comerciais, seguida de Padronização (`StandardScaler`).
4. **Modelagem:** Aplicação do algoritmo **K-Means**.
5. **Otimização de Hiperparâmetros:** Definição do número ideal de clusters (K) utilizando o **Método do Cotovelo (Inércia)** e o **Silhouette Score**, chegando à configuração ótima de K=4.

---

## 💡 Resultados e Personas Identificadas

A clusterização com K=4 permitiu a identificação clara de quatro personas estratégicas para o negócio:

1. 🏆 **Campeões / VIPs:** Compram com muita frequência, gastam altos valores e visitaram a loja recentemente. (Foco em programas de exclusividade).
2. ⭐ **Leais / Promissores:** Consistência média de compras. (Foco em estratégias de *cross-sell* e *up-sell* para aumentar o ticket médio).
3. 👋 **Novos / Casuais:** Fizeram compras recentemente, mas o volume e o valor ainda são baixos. (Foco em réguas de boas-vindas e incentivos para a segunda compra).
4. ⚠️ **Em Risco / Adormecidos:** Alta recência (muitos dias sem comprar). (Foco em campanhas agressivas de reativação).

---

💻 Como Executar o Projeto
O projeto foi desenvolvido para ser executado de forma totalmente nuvem e automatizada, sem a necessidade de configurações locais, downloads manuais ou chaves de API.

Para visualizar o relatório técnico e executar o código ponta a ponta, basta clicar no botão abaixo:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/thiagomacielbarbosa/MVP_PUCRIO_Machine_Learning_-_Analytics/blob/main/MVP_PUCRIO_Machine_Learning_%26_Analytics.ipynb)

Nota: Ao abrir o ambiente do Google Colab, vá até o menu superior e clique em Ambiente de Execução > Executar tudo (ou utilize o atalho Ctrl + F9). O script fará o download e processamento do dataset de mais de 500 mil linhas automaticamente.

---
