## Modeling Mental Health: Can Machine Learning Models Assess the Mental Health of People Who Express Themselves Online? 

By Aimee Williams, Michael Garfagnoli, Abhas Wanchu, Wendy Matta, and Nura Hossainzadeh

**Project description:** In this project, we used machine learning models to gauge the mental health of the authors of short statements that were posted in online forums. Such models could be used as a tool to comprehend patterns of language used by people with certain mental health conditions, to predict future mental health conditions or crises based on expressions by patients in their mental health records (machine learning models would be able to study large quantities of material in a short amount of time), and to develop chatbots that could supplement but not replace mental health professionals. 

We experimented with various models, both “binary”--which placed individuals into one of two categories, healthy or unhealthy–and “multiclass,” which placed each individual into one of several categories (anxious, stressed, depressed, suicidal, bipolar, indications of personality disorder, or none/healthy). 

Our most performant binary model exhibited about 95% accuracy, while our most performant multiclass model exhibited 88% accuracy. In the case of our most performant multiclass model, we had to combine "anxious" and "stressed" into one category, and "depressed" and "suicidal" categories into another, in order to achieve a higher level of accuracy. So the model was not able to differentiate between an anxious and a stressed person, nor a depressed and a suicidal person. 

### Features of the most performant binary model:
For our most performant binary model, the text was preprocessed into bag-of-words format, which means that each statement was converted in a numerical vector that indicated whether a word from a vocabulary (consisting of all the words in the entire dataset) was present in the statement. This means that a statement was represented by a "bag" of 0's and 1's (0 indicating that a word was present, 1 that it was not), and the vector did not capture relationships between words. Perhaps not too surprisingly, the model could predict whether the author of a statement was healthy or unhealthy just based on individual words and groups of words that they used, rather than by reconstructing meaning through word order.

Our most performant binary model was a multilayer perceptron, a type of neural network (whose structure, consisting of layers of nodes connected to each other, is inspired by the human brain). This model had two hidden layers, composed of 128 and 64 nodes, connected by numeric weights. These weights were tuned by the model to discern the words in the text input, where the weights turned nodes "off" and "on" to a certain degree, and node patterns represented meaning. For example, the word “beautiful” would represented by a particular set of weights in each layer. As it was being trained, the model learned associations between, on the one hand, the words in a statement, and on the other, “healthy” or “unhealthy” labels for each statement, and then was able to predict, at 95% accuracy, whether a previously unseen statement was likely to have been written by a “healthy” or “unhealthy” author. “Beautiful,” for example, in combination with other words, would likely be found by the model to be associated more commonly with a “healthy” label. 

<img src="images/binary_model.png?raw=true"/>

### Features of the most performant multiclass model:
Our most performant multiclass model was also a neural network, but one in which words were represented within embeddings. In this approach, every word was converted into a numeric vector, where the values in the vector capture the word’s relationship to other words — for example, words expressing positive emotions, or words describing hopes and dreams, would tend to have similar vector patterns. The model processed these sequences of embedded words from each statement, and then consolidated and simplified the words within each statement into a single vector (through GlobalAveragePooling1D), which computes the average embedding across all words in the statement. 

The nodes (which are characteristic of neural networks) appear in the last layer of the model, and there are five of them, each corresponding to a mental health state. Each node is attached to a weight that reflects the values in the numerical vector produced by the previous layer, and these weights are used to calculate a score for each node.  A softmax activation function then converts these scores into probabilities, representing the model’s estimated likelihood that the statement reflects each of the five mental health states.  To put it simply, words are converted into patterns of numbers, and these patterns of numbers are associated with states of mental health.

<img src="images/performant_multiclass_model_slide.png?raw=true"/>

For the code for the data preprocessing, see: [Modeling Mental Health Data Preprocessing Code](https://nbviewer.org/github/nuraalia/nuraalia.github.io/blob/main/code_files/207_final_preprocessing.ipynb).

For the code that produced our final models, see: [Modeling Mental Health Code Final Models](https://nbviewer.org/github/nuraalia/nuraalia.github.io/blob/main/code_files/Nura_edits_207_final_models.ipynb).

For a Powerpoint presentation of this project, see: [Modeling Mental Health Presentation](/pdf/Nura_edits_207_presentation.pdf).
