# Análise e Previsão de Sobreviventes do Titanic com KNN

Este repositório contém um notebook em Python que demonstra um fluxo de trabalho completo de Machine Learning para prever a sobrevivência de passageiros do Titanic, utilizando o algoritmo K-Nearest Neighbors (KNN).

## Sobre o Projeto

O objetivo principal é aplicar técnicas de pré-processamento de dados em um dataset real e, em seguida, treinar e avaliar um modelo de classificação KNN. O notebook é estruturado de forma didática, ideal para fins de estudo e demonstração de conceitos fundamentais em ciência de dados.

## Como Executar o Notebook

Para que o código funcione corretamente, é necessário que o arquivo `train.csv` esteja no mesmo ambiente de execução do notebook.

1.  **Faça o download dos arquivos:** Clone ou baixe este repositório para a sua máquina.

2.  **Carregue o dataset:**
    * **Se estiver usando o Google Colab:**
        1.  No painel à esquerda, clique no ícone de pasta (Arquivos).
        2.  Clique no botão "Fazer upload para o armazenamento da sessão".
        3.  Selecione o arquivo `train.csv` que você baixou.
        4.  Aguarde o upload ser concluído. O arquivo aparecerá no painel.

    * **Se estiver usando Jupyter Notebook (localmente):**
        1.  Certifique-se de que o arquivo `train.csv` está na mesma pasta onde você salvou o notebook (`.ipynb`).

3.  **Execute o código:** Com o arquivo no lugar certo, basta executar as células do notebook em ordem.

### Metodologia

O processo abordado no código segue as seguintes etapas:

1.  **Análise Exploratória e Entendimento dos Dados:** Carregamento do dataset e investigação inicial das colunas e tipos de dados.
2.  **Pré-processamento de Dados:**
    * **Limpeza:** Exclusão de colunas irrelevantes (`id`, `nome`, `bilhete`) e da coluna `cabine` por excesso de valores ausentes.
    * **Tratamento de Dados Faltantes:** Remoção de linhas com valores nulos (`dropna`).
    * **Transformação de Dados Categóricos:** Aplicação de One-Hot Encoding nas colunas `classe_social`, `sexo` e `embarque` com `pd.get_dummies`.
    * **Normalização de Dados Numéricos:** As colunas contínuas (`idade`, `parentes`, `dependentes`, `tarifa`) são normalizadas (escala de 0 a 1), uma vez que o teste de normalidade de Shapiro-Wilk indicou que não seguem uma distribuição normal.
3.  **Modelagem com KNN:**
    * Implementação da distância euclidiana como base para o algoritmo.
    * Divisão do dataset em conjuntos de treino e teste (`train_test_split`).
    * Treinamento do classificador `KNeighborsClassifier`.
    * Busca por um valor ideal de `k` (vizinhos) para otimizar a performance.
4.  **Avaliação do Modelo:**
    * Realização de previsões no conjunto de teste.
    * Cálculo da acurácia do modelo para medir seu desempenho.

### Bibliotecas Utilizadas

* **Pandas:** Para manipulação e análise de dados.
* **NumPy:** Para operações numéricas.
* **Scikit-learn:** Para a divisão dos dados, implementação do KNN e avaliação de métricas.
* **SciPy:** Para a realização do teste de normalidade de Shapiro-Wilk.
* **Seaborn:** Para visualização de dados.
