## Using Transformer and Large Language Models to Detect Racial Microaggressions in Text

By Neeharika Kotte, Carlos Schrupp, and Nura Hossainzadeh

**Project description:** Microaggressions are subtle forms of hate speech. Because they are not directly or explicitly offensive in nature, they require a nuanced approach to identify accurately, particularly in text. Our study presents both transformer and LLM (GPT-5.1) models that are able to detect microaggressive speech with a high degree of accuracy. 

The key to achieving this result was the development of a novel dataset, used to train our transformer models and evaluate our LLM model, consisting of microaggressive statements from a well-known corpus paired with LLM-generated non-microaggressive counterparts that matched their linguistic and stylistic properties while differing in semantic meaning. We found that our LLM model achieved a 90% accuracy on a 100-entry sample of our generated dataset. Of the transformer models we tested, deBERTa exhibited the best performance, achieving high accuracy (81.87%) even when cross-evaluated on a previously unseen workplace microaggressions dataset on which it had not been trained.

### Comparing Accuracy and F1 Scores of Various Transformer BERT Models, LLM Model, and Baseline CNN Model :

As indicated in the table below, our BERT models (along with the baseline CNN model) were trained on our generated novel dataset and then cross-evaluated on a workplace microaggressions dataset. 

<img src="images/model_comparisons.jpg?raw=true"/>

For the full paper, see: [Refugee Movement around the World](/pdf/205_slides.pdf).


