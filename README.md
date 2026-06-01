# Sentiment Analysis Model

## Overview
This project provides a comprehensive framework for performing sentiment analysis on textual data. The aim is to classify text inputs into categories such as positive, negative, or neutral based on their sentiment.

- **Initial Data View**: We read data from a source (a CSV file) into a Pandas DataFrame and perform an initial check to understand its structure.

![Primeiras linhas do Dataframe](./img/Primeiras_linhas_df.PNG)

- **Chart of Sentiment Distribution**:

![Distribuição dos Sentimentos](./img/Grafico_Distribuicao_Sentimentos.PNG)

Note that the data is balanced, which is ideal for building a machine learning model. If it were unbalanced, we would have to apply strategies such as oversampling, undersampling, among others.

- After performing the sentiment distribution analysis, it was necessary to clean the data and perform feature engineering. Then, we divided the data into training and testing sets (75% - 25%) and developed a predictive modeling pipeline. Finally, we used GridSearchCV, systematically testing various configuration combinations (hyperparameters) for the pipeline to find the combination that results in the best possible performance.

- **Model Training**: In this step, we feed the pipeline with the training data. GridSearchCV executes the .fit() process, where the algorithm learns the patterns that connect the text of the reviews to their respective sentiments.

![Treinamento_Modelo](./img/Treinamento_Modelo.PNG)

- **Model Accuracy**: Finally, we use the test set (which the model has never seen) to make predictions and compare them with the actual results. Metrics such as Accuracy, Classification Report, and the Confusion Matrix tell us how well the model is generalizing and whether it meets the business objectives.

![Acurácia do Modelo](./img/Acuracia_Modelo.PNG)

An accuracy of 81.15% is ideal for our model; if it were a model for the healthcare field, for example, this percentage would be unacceptable.

An accuracy of 100% may indicate overfitting problems in the model, since ideally, the model should learn the overall relationship between the data.

![Matriz de Confusão](./img/Matriz_Confusao.PNG)

The blue diagonals show the model's correct predictions. When the true value was negative, the model predicted negative 47 times and was correct.
When the true value was positive, the model predicted positive 52 times and was correct.
The other diagonal shows the model's errors. When the true value was negative, it predicted positive 11 times and was wrong.
When the true value was positive, it predicted negative 12 times and was wrong.

## Project Structure
- **data/**: Contains datasets used for training and testing the model.
- **notebooks/**: Jupyter notebooks for exploratory data analysis and model training.
- **src/**: The source code for the sentiment analysis model.
- **models/**: Pre-trained models and model artifacts.

## Requirements
- Python 3.x
- Libraries: `pandas`, `numpy`, `scikit-learn`, `nltk`, `tensorflow`, `matplotlib`

## Installation
1. Clone the repository: `git clone https://github.com/OseasMonteiro/Modelo_Classificacao_Analise_de_Sentimentos`
2. Install the required libraries: `pip install -r requirements.txt`

## Usage
To train the sentiment analysis model:
```
cd src/
python train_model.py
```

To evaluate the model:
```
cd src/
evaluate_model.py
```

## Dataset
The datasets used are sourced from various online platforms including movie reviews, tweets, and product feedback.

## Acknowledgements
- Special thanks to [source datasets providers] for providing the datasets used in this project.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Conclusion
This sentiment analysis model is designed to enable users to gain insights from text data through automatic classification of sentiments. Contributions are welcome via pull requests!