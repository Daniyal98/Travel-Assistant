# Travel Assistant

## Introduction

A travel assistant chat-bot that can answer questions about northern cities of Pakistan. The chat-bot is developed using RASA nlu model. The web application is developed using Django framework.

## Working

The RASA nlu model works based on intents and actions. These intents and actions are defined in the domain.yml file and all the entities of the intent are also defined in this e.g. city, price etc. The configurations for the model itself are defined in the config.yml file. In config.yml file, you can defined the pipeline for your model. The pipeline has four components i.e. Tokenizer, Featurizer, Intent Classifier and Feature Extractor. You can read in depth about them on this link https://rasa.com/blog/intents-entities-understanding-the-rasa-nlu-pipeline/. You can train the RASA nlu model on your set of data as well. We can store our questions in the data/nlu.yml file. Here we can add diferent examples of how a question can be asked for a specific intent. The data/stories.yml file is used to store different stories of the model i.e. what action should be performed for a certain intent. 
We can train the RASA model on our data using the following command.
`rasa train`
We can also do an interactive learning on the RASA model. Interactive learning means tat the model will classify an intent and suggest an appropriate action for it and you can tell the model whether its classification and suggestion is correct or not, if not, then you can suggest the correct one and the model will store that story in the stories.yml file and learn from it in the future. You can do interactive learning using the following command.
`rasa interactive` 

## Scope

The chat-bot can answer a wide range of questions. Some of them are given below.
- Weather of a particular city. 
    - Example: What is the weather like Skardu?
- Best hotels in a particular city.
    - Example: Show me the best hotels in Gilgit
- Cheapest hotels in a particular city.
    - Example: Show me the cheapest hotels in Swat

## Prerequisites

You will need to install RASA and Django using pip. The commands to install them are given below.

`pip install rasa`

`pip install django`

## How To Run

First, we will need to run the our actions script.

`rasa run actions`

After that we need to load our model.

`rasa run -m models --enable-api --cors "*"`

Lastly, we need to run our Django application.

`python manage.py runserver`

