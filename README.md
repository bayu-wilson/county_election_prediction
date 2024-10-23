# Predicting County Flips in U.S. Presidential Elections
Bayu Wilson

### Disclaimer
I am not a political scientist and I have not rigorously tested my approach nor have I done an exhaustive literature review. This project is mainly an exercise to practice machine learning, data integration, and geospatial visualization on real, relevant, and current datasets. 

### Overview
The goal of this project is to predict county flips in U.S. presidential elections. First, I created an integrated dataset of election and demographic data over time from the MIT Election lab, the Decennial Census, and the American Community Survey. I then performed feature engineering in order to extract useful predictors for flipped counties. I trained an XGBoost classifier to predict county flips and **achieved a 71% and 98% true positive rate** (recall) for  predicted county flips to democratic and republican candidates respectively. I use the geospatial visualization Python library, [Folium](https://python-visualization.github.io/folium/latest/), to make interactive leaflet maps showing these flipped counties for 2016, 2020, and a prediction for 2024. See figure 1 below or [click here](https://nbviewer.org/github/bayu-wilson/county_election_prediction/blob/main/map.html) to view the map. I purposefully do not try to use this model to predict the winner of the 2024 election. I plan to compare my county-level predictions to the true outcome after the election.

<p align="center">
   <a href="https://nbviewer.org/github/bayu-wilson/county_election_prediction/blob/main/map.html">
    <img src="https://github.com/user-attachments/assets/c2112483-d0fb-4557-8f28-b25a0aa2a476" alt="Description" width="700"/>
    </a>
</p>
<p align="center">Figure 1. Counties predicted to flip in the 2024 U.S. Presidential Election using an XGBoost Classifier on an integrated dataset from the MIT Election lab, the Decennial Census, and the American Community Survey. This is a screenshot of a publically available interactive map, built with <a href="https://python-visualization.github.io/folium/"> Folium</a>, that can be accessed by clicking the map or <a href="https://nbviewer.org/github/bayu-wilson/county_election_prediction/blob/main/map.html"> this link </a> The blue and red icons represent the three most populous counties predicted to flip to democratic and republican presidential candidates respectively.
  </p>

  
### Background
As of October 22, 2024, presidential election polling between Donald Trump and Kamala Harris are razor-thin and many people are saying it is a [toss-up](https://thehill.com/homenews/4947735-harris-trump-travel-state-of-race/). The main battleground areas appear to be the [7 swing states](https://www.usnews.com/news/elections/articles/7-swing-states-that-could-decide-the-2024-presidential-election) and within them are various "swing" counties that can easily flip from one presidential election to the next. The goal of this project is to predict county flips in U.S. presidential elections. Other than for the sake of curiosity, potential stakeholders could be political campaigns or issue advocacy organizations.

Many studies have already been done to develop [demographic profiles of republican and democratic voters](https://www.pewresearch.org/politics/2023/07/12/demographic-profiles-of-republican-and-democratic-voters/). Therefore it would not be very interesting or useful to do a machine learning project to predict the political affiliation of U.S. counties. What is more interesting is predicting counties that change political affiliation (flipped counties). Perhaps there exists trends and predictors in publically available county data that could enable this prediction to be made. For example, in [this article](https://eig.org/rural-america-is-not-all-trump-country/), they explored the qualities of rural counties won by Joe Biden in the 2016 election. They state that Biden's success was associated by factors like: demographics, economic distress, migration, and population growth. In this work, I take this another step forward and try to use these factors (and more) as predictors.


### Where did I get this data?
|  data | source |
|----------|----------|
| Election data   | https://electionlab.mit.edu/data   | 
| County polygons   | https://gist.github.com/sdwfrost/d1c73f91dd9d175998ed166eb216994a  | 
| American Community Survey | https://www.census.gov/programs-surveys/acs |
| Decennial Census| https://www.census.gov/decennial-census |

### For those interested in running my notebooks
|  Notebook | description |
|----------|----------|
| integration_and_model_training.ipynb | Here is where I integrate the datasets, engineer predictors, and train the model.   | 
| geospatial_map_visualization.ipynb  | Here is where I use Folium to geospatially visualize the county flips in 2016, 2020, as well as the prediction for 2024  | 

