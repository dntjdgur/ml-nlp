# Text Classification on Relevance - Natural Language Processing Model
## Project Purpose
This project is to build a basic NLP model that can perform text classifications. Text classification models are best known by Chat-GPT4 or Llama, that performs the task of assigning a label or class to a given text. We've already conducted a classification analysis from NLP - Sentiment Analysis model, that determines whether the texts are indicating an emotionally distressed or eustressed nature by labeling each text to a given numerical indicator.
This study is to create a Grammatical Error Correction model (GEC) that finds any grammatical errors in the sentences, transform them into a corrected format. 
## Data Source
Data source was obtained from Kaggle, titled by [C4 200M Grammar Error Correction dataset](https://www.kaggle.com/datasets/dariocioni/c4200m)
## Descriptive Statistics
Data is composed of 200,000,000 rows and 2 columns. Column **Incorrect** includes sentences that are grammatically incorrect, and **correct** includes sentences that are corrected ones of the corresponding row's incorrect sentence.
## Data Pre-processing
Unlike previous study in Sentiment Analysis model, this model does not provide any score-based output dimension. Sentiment Analysis was focusing on providing a score in range 1 through 5, indicating the sentiment level of sentences, given by the tokenized context of each word in the sentences. Although both studies are similar in a way that each word needs to be tokenized and be interpreted during the training, this study focuses on determining distinctiveness in each tokenized corrected and incorrected sentence. 
Basic foundation of the model: We set the **Corrected** values to be the training data, whereas the **incorrect** values to be the input dimensions.
## Model Architecture
Similar to the Sentiment Analysis model, this model requires its neurons to learn from each other in a sequential manner. Using LSTM's composition, each neuron will learn from its predecessor neuron and increase the training complexity. This study is, conceptually, much easier than the Sentiment Analysis since we are training the model with tokenized sentences and correlating it with the corrected versions of sentences. The model will be able to determine if a certain token should be in the sentence given by the presence of other tokens, based on the correct version of sentences.

## Learning Environment
### AWS SageMaker
    Instance: ml.g4dn.4xlarge
    Storage: 100 GB
    Image: SageMaker Distribution 1.8
    Lifecycle Configuration: None

## Initial Model Training Approach
### Hyperparameters
    Batch Size: 150
    Input Dimension: 128
    Output Dimension: 5
    Training Size: 75%

### Optimizer Parameter
    Optimizer: Adam
    Learning Rate: 0.001

### Training Output
    Starting epoch 1

### Training Loss Plot

### Validation & Test Output

### Test & Validation Loss Plot

### Result Interpretations & Adjustments
