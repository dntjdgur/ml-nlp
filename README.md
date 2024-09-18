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
Similar to the Sentiment Analysis model, this model requires its neurons to learn from each other in a sequential manner. Using LSTM's composition, each neuron will learn from its predecessor neuron and increase the training complexity.



Natural Language Processing requires the neurons to learn from their predescessor, in a sequential manner. One of the most common neural network being used to analyze and predict the output is RNN. RNN (Recurrent Neural Network) is a type of neural network architecture in which the output of a neuron is fed back as an input to the network at the next time step, retaining memory of past inputs. Although it may sound RNN to be overly complex, it is actually consisted of a simple structure. And because of its simple structure, RNN is computationally less intensive. RNN, however, constantly suffers from vanishing and exploding gradient problems, which ultimately affects in learning long-range dependencies in sequences and difficulties in establishing the adequate layers.

LSTM (Long Short-Term Memory) model is a type of RNN that is more complex in its composition. LSTM is designed to overcome the limitations of traditional RNNs in learning and remembering long-range dependencies in sequential data. Each LSTM unit consists of the forget gate, the input gate, and the output gate. The forget gate determines which information from the previous state should be disregarded, the input gate decides which new information should be added to the current cell state, and the output gate determines what information from the current cell state should be outputted. The entire LSTM network is consisted of multiple LSTM units, allowing each unit to learn from its predecessor and improving the accuracy of the output. LSTM is a great fit for analyzing time-series or sequential datasets, commonly applied for Natural Language Processings. In this project, we will be applying LSTM as a basis model architecture to predict the sentiment of given input texts.
