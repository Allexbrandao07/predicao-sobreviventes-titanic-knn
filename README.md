# Análise e Previsão de Sobreviventes do Titanic com KNN

Este repositório contém um notebook em Python que demonstra um fluxo de trabalho completo de Machine Learning para prever a sobrevivência de passageiros do Titanic, utilizando o algoritmo K-Nearest Neighbors (KNN).

## Sobre o Projeto

O objetivo principal é aplicar técnicas de pré-processamento de dados em um dataset real e, em seguida, treinar e avaliar um modelo de classificação KNN. O notebook é estruturado de forma didática, ideal para fins de estudo e demonstração de conceitos fundamentais em ciência de dados.

## Estrutura do Projeto

Este repositório contém duas versões principais do código, cada uma com um propósito específico:

* **`analise_preditiva_titanic_knn.ipynb`**: Um **Jupyter Notebook** que serve como um relatório detalhado da análise. Ele contém o passo a passo com explicações, visualizações e as saídas de cada célula, ideal para estudo e apresentação do processo.
* **`analise_preditiva_titanic_knn.py`**: Um **script Python (.py)** que é a versão refatorada e limpa do notebook. Este arquivo é modular, reutilizável e pode ser executado diretamente pelo terminal, sendo ideal para automação e implementação.
* **`train.csv`**: O conjunto de dados de treinamento contendo informações sobre os passageiros.


## Como Executar o Notebook

Para que o código funcione corretamente, é necessário que o arquivo `train.csv` esteja no mesmo ambiente de execução do notebook.

### Usando Git Clone (Recomendado)

1.  **Pré-requisito:** Tenha o [Git](https://git-scm.com/) e Python instalados.

2.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/nome-do-repositorio.git](https://github.com/seu-usuario/nome-do-repositorio.git)
    ```

3.  **Navegue até a pasta e instale as dependências:**
    ```bash
    cd nome-do-repositorio
    pip install pandas numpy scikit-learn
    ```

4.  **Execute o script:**
    ```bash
    python train_titanic_knn.py
    ```

5.  **Carregue o dataset:**
    * **Se estiver usando o Google Colab:**
        1.  No painel à esquerda, clique no ícone de pasta (Arquivos).
        2.  Clique no botão "Fazer upload para o armazenamento da sessão".
        3.  Selecione o arquivo `train.csv` que você baixou.
        4.  Aguarde o upload ser concluído. O arquivo aparecerá no painel.

    * **Se estiver usando Jupyter Notebook (localmente):**
        1.  Certifique-se de que o arquivo `train.csv` está na mesma pasta onde você salvou o notebook (`.ipynb`).

6.  **Execute o código:** Com o arquivo no lugar certo, basta executar as células do notebook em ordem.

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
