# Building a Historical Network Analysis: International Relations in the 20th Century

###### This project was completed as a requirement for the course, Data Visualizations with Python, by CareerFoundry as part of their Data Analytics Certificate Program.

## Project Objective

##### As a freelance analyst contracted by the Institute for Public Policy to give an analytical overview and visualization of the interrelations between countries throughout the twentieth century. Given the volatility of world politics, the Institute is looking for historical ties between different countries to inform its research.

##### Many new job positions seek freelancers, so you’ll need to choose which tools you’ll use to structure your schedule and complete the assigned task. As a freelancer, some of the most common tasks you’ll receive will require you to create visualizations to share your results. Academic institutions, startups, and other companies hire freelance data analysts to interpret and explain data that can help fit into the context of larger projects.

## Context

##### For this project, the Institute for Public Policy has employed you to analyze and create a visualization as part of a larger initiative it’s working on.

##### In this scenario, the institute believes that past events heavily influence the current geopolitical climate. To delve deeper into this hypothesis, a clearer understanding of the historical relationships between countries in the twentieth century is needed.

##### Suitable results can be achieved by looking at major global events throughout the twentieth century. To do so, you’ll need to give a visualization and an analysis of the chain of events that led to the current state of affairs. To be effective, your visualization must highlight these past relationships. This way, other researchers can understand and tie your findings into the final report.

## Tools/Skills Used
##### Skills: Web scraping, text mining, Natural Language Processing (NLP), Network Analysis Visualization, Data Cleaning and Prep, Data Wrangling
##### Python: pandas, numpy, os, matplotlib.pyplot, seaborn, textblob, nltk, spacy, networkx, scipy, requests, beautifulsoup

## Data
##### Text data from Wikipedia ("Key Events of the 20th Century") will be scraped for this project's analysis
##### https://en.wikipedia.org/wiki/Key_events_of_the_20th_century

## Analysis

### Step 1: Set up Virtual Workspace

##### Create virtual environment and install necessary libraries (see in "Tools/Skills Used" Section)

### Step 2: Data Collection (Text Data)

##### Using Beautiful Soup, scrape data from web page
##### Save scraped file as "20th_Century_Scrape.txt"

### Step 3: Text Mining: Data Cleaning and Initial Exploration (Notebook 1.5)

##### Tokenization of Words: Remove stop words and punctuation
##### Create lists according to parts of speech
##### Plot bar chart of top words for each POS: nouns, verbs and adjectives
##### Create and save dataframe of countries and how many times they are mentioned in the text
##### Plot bar chart of how many times each country is mentioned in text 

### Step 4: NLP and Network Analysis (Notebook 1.6)

##### Create NER Object from Text
##### Split sentence entities, and get named entity list per sentence (two columns)
##### Using countries list (from separate csv file of country names), filter the entities from the text, retrieving only country names (as a third column)
##### Define relationships between countries: if countries are mentioned within five sentences of each other, there is an interaction
##### Summarize the interactions between countries in a new dataframe: save data frame as "countries_relationships.csv"

### Step 5: Create Network Visualizations

## Insights

## Recommendations

##### As this project is part of a larger-scale research initiative (by the Institute for Public Policy), the listed insights serve as a springboard/foundation for further research. My recommendations for further research include the following: