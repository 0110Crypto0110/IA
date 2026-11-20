# Projeto 2 - Comparação de Algoritmos de Classificação (Anime Database)

Este repositório contém o notebook e os artefatos desenvolvidos para o **Projeto 2** da disciplina de **Inteligência Artificial** da **Universidade Federal Rural de Pernambuco (UFRPE)**.

## Sobre o Projeto
O objetivo deste trabalho é comparar o desempenho de 5 algoritmos de classificação (Árvore de Decisão, KNN, Naive Bayes, Regressão Logística e MLP) na tarefa de prever o **tipo de anime** (TV, OVA, Movie, etc.) com base em suas características (gênero, episódios, nota e número de membros).

## Dataset Utilizado
*   **Nome:** Anime Recommendations Database
*   **Fonte:** [Kaggle (CooperUnion)](https://www.kaggle.com/datasets/CooperUnion/anime-recommendations-database)
*   **Origem dos dados:** MyAnimeList (MAL)
*   **Licença:** CC0 1.0 Universal (Public Domain Dedication) - Permite uso livre para fins acadêmicos e comerciais.
*   **Resumo:** 12.269 exemplos válidos, 7 atributos e 6 classes (TV, OVA, Movie, Special, ONA e Other).

## Metodologia Aplicada
*   **Validação Cruzada:** 10-Fold Cross-Validation Estratificado (`StratifiedKFold`).
*   **Otimização:** `GridSearchCV` com no mínimo 3 combinações de hiperparâmetros para cada algoritmo (totalizando 270 treinamentos).
*   **Pré-processamento:** Imputação de dados faltantes (mediana), binarização de gêneros (`MultiLabelBinarizer`) e padronização (`StandardScaler`).
*   **Prevenção de Data Leakage:** A binarização dos gêneros foi encapsulada em um `TransformerMixin` customizado (`GenreBinarizer`), sendo executada estritamente dentro do pipeline de treinamento.

## Estrutura do Repositório
*   `Entrega_Final_IA.ipynb`: Notebook principal contendo toda a execução do código (preparação dos dados, treinamento, avaliação, ranking e exportação).
*   `artefatos_projeto2.zip`: Arquivo compactado contendo:
    *   `resultados_finais_projeto2.csv` (Tabela de métricas consolidadas)
    *   `grafico_comparacao_modelos.png` (Gráfico de barras comparativo)
    *   `grafico_boxplot_folds.png` (Boxplot da distribuição por fold)
    *   `anime_original.csv` (Base de dados bruta)
    *   `anime_processado.csv` (Base de dados após o pré-processamento)

## Tecnologias Utilizadas
*   Python 3.10+
*   Pandas, NumPy, Matplotlib e Seaborn
*   Scikit-Learn
*   Google Colab

## Principais Resultados
| Algoritmo | Acurácia Média | F1-Score Médio |
| :--- | :--- | :--- |
| **Árvore de Decisão** | 0.6954 ± 0.0147 | 0.6061 ± 0.0127 |
| **Regressão Logística** | 0.6351 ± 0.0175 | 0.5681 ± 0.0213 |
| **MLP** | 0.4165 ± 0.0362 | 0.3257 ± 0.0384 |
| **KNN** | 0.3957 ± 0.0136 | 0.3347 ± 0.0195 |
| **Naive Bayes** | 0.3506 ± 0.0114 | 0.2029 ± 0.0204 |

## Autores
*   Francielle Ayanne Da Silva
*   João Ricardo Justo Lins
*   Pedro Lucas Da Silva Santana

---
*Disciplina ministrada pelo Prof. Anderson Pinheiro Cavalcante.*
