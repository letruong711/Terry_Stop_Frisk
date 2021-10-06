
<h1 align="center"> Seattle Police Department's Racial Bias, Terry Stops, and Frisking </h1> <br>
<p align="center">
  
### Background:

<p>When you talk about injustices, the topic of race forces itself into the forefront of most discussions. In recent times, due to the advancement of social media, civil injusticies have caught the attention of the public due increasing rates of police related deaths. As a result of social media exposure, these moments of police brutality have been captured and as a result, has been recognized by the public and local governments as a issue of racial injustice. As a life long Washingtonian, I wanted to investiage whether or not there is a racial bias here in the blue state of Washington. </br></p>
<p>Using Seattle's Open Data Program, I was able to obtain data on Terry Stops from 2014 until September of this year. Using machine learning and exploratory analysis, and with a goal of using a model that would predict features of a subject, can we predict whether or not a subject will get frisked?</p>

<h3> Exploratory Findings:</h3>
<ul style="list-style-type:circle;">
  <li> Overall trend in Terry Stops in Seattle has been slowly decreasing over time.
    ![](Terry_Stop_Frisk/images/Stops_per_Month.png)

  <li> White subjects make up 66% of the census population in Seattle and are 51% of the Terry Stop population.
  <li> Black subjects make up 7% of the census population but are 31% of the Terry Stop population.
  <li> American Indian/Alaskan Native subjects make up less than 1% of the census population but are 3% of Terry Stop population.
  <li> Male Subjects are three times likely to be stopped compared to female subjects.
  <li> ~1/3 Terry Stops result in a frisk.
  <li> White subjects are less likely to get frisked compared to other races.
</ul>

### Overview:
<p>Seattle Police Department (SPD), like other police departments across the country, has a long history of a generous use of force. Each officer has been trained to maintain the peace and enforce law by anymeans necessary. If they suspect illegal behavior, they have the right to stop a subject and perform a Terry Stop.
    
A **Terry Stop** is when an officer can stop and detain a subject based on suspcion of criminal behavior. If the officer suspects the subject to be armed or the officer feels like they are in danger, they have right to frisk the subject. A **frisk** is a search that requires a justified stop. It involves patting of the subjects outer layer of clothing to make sure the subject isn't holding a concealed weapon.   
    
Both stops must be justifiable under lawful and safety justifications. 
    
When looking at seeing whether we could predict when a Terry Stop subject was frisked, we looked at many features. We looked at the subject's characteristics (race, gender), the officer's characteristics (age, race, gender), and situational features (weapon type, stop resolution, call_type, etc). 

### Methods
  
Using Pandas, Numpy, Seaborn, Matplotlib, and Sklearn, we were able to create multiple models to help us identify what factors could help us predict a frisk. We used StandardScaler to scale and normalize the data. We encode the data using OneHotEncoder to convert our categorical data variables to help improve our predictions. Afterwards, we split our data into a train and test group and used a 20% testing size. 

The models we used were multiclass classification models. They were created with Logistric Regression, K-Nearest Neighbors (KNN), Support Vector Machines (SVM), Decision Tree, and RandomForest Classifier. 
  
We created a function that would give us the accuracy score for the above models. After we ran the function for our models, we were giving accuracy percentages to see how accurate they were. 
  
### Results
  
By running the function and then inputing our data into a Confusion Matrix, we were able to see that using an SVM model gave us an 83% accuracy rating with 79% precision but a 30% recall. Using a RandomForest Classifier, we were able to see the most important features to predicting a frisk were Officer Age, Stop Resolution, and Weapon Type. 

### Conclusions
  
With an 83% percent accuracy rate and 79% precsion rate, we can say our model can help us get an idea of when a frisk can be made. It showed us that while there is a racial bias, when a terry stop is made and a frisk is happening, race doesn't matter. Our top features were an officer's age, the stop resolution, and weapon type. When looking at the most important futures to our model, we notice that it would be difficult to create an algorithm to predict a frisk and that is reflected with our 30% recall. Officer Age is plays an important role beacuse experience matters when you're out in the field; An experienced officer will react differntly to a situation than a newer officer on the field. This shows us that a frisk depends on the subjectivity of the officer during the time of the Terry Stop. We cannot accurately predict subjectivity especially since we don't have all the information about the situation. We don't know if the officer has any subconscious bias or any preconceived idea of what is going to happen when a stop has been made. We also don't know if the subject themselves were dangerous or not.

While have evidence to support a frisk is subjective and situational, we must also mention that our data came with a lot of missing data that could have impacted our results. 
  
### Future Steps

While our data came with a decent accuracy and precision score, our recall left more to be desired. However, as stated previously, it is difficult to predict a frisk as it is situational and dependant on the subjectivity of the officer. If Seattle's Open Data policy allows, hopefully we are able to expand on the timeframe of this data to see if there are patterns in the frisks to help us improve our recall score. There should hopefully also be policy changes to help improve how much missing data is reported and acceptable. If this is changed, our recall percentage could improve. 
  
Our analysis did show race doesn't matter after the Terry Stop has been made, there is evidence to show an initial racial bias. Further training to undue subconscious bias about specific races will make society a safer place for both officer and public. 
  
In addition to the future improvements in training and data collection, improvements need to be made to the hyperparameters of our model. Due to the length of time required to run a GridSearch on SVM models, we were unable to update our model with the proper parameters. In addition, we were unable to use our model to give us our most important features so we used our RandomForest model to provide that information. Future improvements to our model will provide more accurate feature importance.
