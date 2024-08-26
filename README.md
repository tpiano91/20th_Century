# Building a Historical Network Analysis: International Relations in the 20th Century

###### This project was completed as a requirement for the course, Data Visualizations with Python, by CareerFoundry as part of their Data Analytics Certificate Program.

## Project Objective

##### As a freelance analyst contracted by the Institute for Public Policy, the objective is to give an analytical overview and visualization of the interrelations between countries throughout the twentieth century. Given the volatility of world politics, the Institute is looking for historical ties between different countries to inform its research.

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

###### Create virtual environment and install necessary libraries (see in "Tools/Skills Used" Section)

### Step 2: Data Collection (Text Data)

###### Using Beautiful Soup, scrape data from web page
###### Save scraped file as "20th_Century_Scrape.txt"

### Step 3: Text Mining: Data Cleaning and Initial Exploration (Notebook 1.5)

###### Tokenization of Words: Remove stop words and punctuation
###### Create lists according to parts of speech
###### Plot bar chart of top words for each POS: nouns, verbs and adjectives
###### Create and save dataframe of countries and how many times they are mentioned in the text
###### Plot bar chart of how many times each country is mentioned in text 

### Step 4: NLP and Network Analysis (Notebook 1.6)

###### Create NER Object from Text
###### Split sentence entities, and get named entity list per sentence (two columns)
###### Using countries list (from separate csv file of country names), filter the entities from the text, retrieving only country names (as a third column)
###### Define relationships between countries: if countries are mentioned within five sentences of each other, there is an interaction
###### Summarize the interactions between countries in a new dataframe: save data frame as "countries_relationships.csv"

### Step 5: Create Network Visualizations

#### Create static network graph (NetworkX)

![Network Graph Static](Files/networkx_plt_countries.png)

#### Create interactive network graph using pyvis

#### ![Network Graph Interactive](Images/countries.png)

#### [View HTML File](Files/countries.html)

#### Apply the Leiden algorithm to detect any communities - visualize the new network graph and record initial insights

#### ![Network Graph Interactive](Images/countries_communities_leiden.png)

#### [View HTML File](Files/countries_communities_leiden.html)

#### Calculate and visualize the degree, closeness, and betweenness centrality measures and record insights (See in next section)

## Insights

### Leiden Algorithm

#### Communities: The Leiden algorithm split the listed countries into six communities, indicated by the six different colors of the edges. 
###### The communities seem to largely be based off of geographical locations of each country: for example, the pink community consists of Scandinavia and Benelux; the blue community contains most of the "key players" in Europe associated with the two world wars (such as Germany, France, Russia, and Italy). 
###### The red, orange and purple groups contain mostly non-European countries, though there are some curious findings in these communities: for example, in the red group, why is Mongolia grouped with Cuba, Canada, Australia and the USA? In the orange group, Cambodia seems to act as a link between Asian and African countries.

#### Bridges: Specific countries acted as "bridges" or "links" between different communities. 
###### The United States and Russia act as bridges between the "red" and "blue" neighborhoods. 

#### Thickness of the Edges: displays which countries played particularly imporant roles. 
###### In this case, Germany has five of the visibly thickest edges to Italy, Poland, Russia, France and Japan (which makes sense given the context of the two world wars). 
###### Other thick edges can be seen in other communities: India to Japan and Pakistan (orange); and Libya and Egypt (purple).

### Degree Centrality

#### ![Degree Centrality](Images/degree_centrality.png)

###### Germany ranks first in all three degrees of centrality. With regards to degree centrality, this means that Germany has the highest number of connections (edges) to other countries (nodes). Japan, Russia, France, India and Italy also have high degrees of centrality. India's connections are mostly in the orange community, whereas Japan has connections to both the orange and blue communities.

### Closeness Centrality

#### ![Closeness Centrality](Images/closeness_centrality.png)

###### Germany ranks the top of the list again, though in this case, its closeness centrality measure is higher (closer to 0.4) than the degree centrality (which was closer to 0.25). This indicates that Germany is in close proximity to other countries, displayed by the thickness of its edges to other nodes. This makes sense as Germany was arguably the most active or powerful country in both World Wars.

###### Japan, Russia, France and Italy once again rank higher here as well. India ranks lower than the aforementioned countries in terms of closeness indicating that while it has a similar number of connections, India's ability to communicate or control information through their networks is not as strong as Japan and the aforementioned European countries.

### Betweenness centrality

#### ![Betwenness Centrality Interactive](Images/betweenness_centrality.png)

###### The ranking in this Betweenness Centrality graph is a bit different compared to the other two. Germany again ranks at the top, indicating that the paths and connections they have make it easy for them to connect with other countries outside of their communities, funcitoning as a bridge. The next most efficient "bridge" countries on the list include Japan, Russia, the Philippines and Cambodia - the latter two did not rank as highly on the other two graphs.

## Recommendations for Further Research

#### As this project is part of a larger-scale research initiative (by the Institute for Public Policy), the listed insights serve as a springboard/foundation for further research. My recommendations for further research include the following:

###### 1. The visualizations display which countries played important roles in international relations in the 20th century overall, but does not display a timeline of events. Depending on the objectives of the initiative, I recommend considering the years/times certain important global events took place. 

###### 2. Centrality Mesaures: the betweenness centrality measure provided the slightly different results/rankings as the other two - I recommend further study on the roles that high-ranking countries in this category played, both within their assigned community and on a global scale. Of the countries that ranked high here, I also recommend making a distinction between those that also ranked highly in the other two centrality measures and those that did not (such as the Philippines). Can any trends be uncovered there? I also recommend researching countries that scored high in the other two categories but low in betweenness centrality (such as France).

###### 3. The Leiden algorithm classified six communities, which mostly correspond to countries within the same geographic location. However, there are some anomalies within the communities. Within the red group (consisting of countries in the Americas), why is Mongolia here? The orange group contains mostly countries in Africa and Southeast Asia - however, why does South Africa seem to have closer ties to the Asian countries in this group?



