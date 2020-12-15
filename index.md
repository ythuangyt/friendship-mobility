---
layout: page
title: Someone Like You
bigimg: img/globe.jpg
---
### How similar are you and your friends? 

### The Data

### How close are you to your friends?

How similar are you and your friends checkins' pattern? How often do you go to the same type of locations as your friends? Do you all enjoy Italian food and outdoor acticities?

We investigate two types of the checkins' similarity between users in four categories of relationships. To calculate checkins' similarity we first estimate the probablity that a user is checking in each location, and call it the location probability vector. For each user, we estimate the vector by dividing the numbers of checkins in each location over their total checkins. 

For the first type of similarity, we calculate the cosine similarity between two users' location probability vector, and estimate the empirical distribution of the similarity in each categories. The commom location similariity is computed as the number of same locations among two users' commom location. The commom location of each user is defined as the twenty locations that a user has the most checkins.

<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosineSimilarity_4Categories" style="height:40px;width:230px" class="btn btn-outline-dark active" onclick="cosineSimilarity_4Categories()">Cosine Similarity</button>
      <button type="button" id="mostCommon_4Categories" style="height:40px;width:230px" class="btn btn-outline-dark" onclick="mostCommon_4Categories()">Common Location</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>

<iframe id='cosineSimilarity4Categories' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/cosine_similarity_four_categories.html"></iframe>

<script>
var selected1 = "cosineSimilarity_4Categories"
  
function cosineSimilarity_4Categories(){
document.getElementById(selected1).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity4Categories");
iframe.src = "plot/cosine_similarity_four_categories.html"
selected1 = "cosineSimilarity_4Categories"
document.getElementById(selected1).classList.add("active");
}

function mostCommon_4Categories(){
document.getElementById(selected1).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity4Categories");
iframe.src = "plot/most_common_four_categories.html"
selected1 = "mostCommon_4Categories"
document.getElementById(selected1).classList.add("active");
}
</script>

Unquestionably, friends should have more similar checkins than strangers, regardless of whether the friends is from different countries or not. Likewise, people from the same country shares more similarity than people from different ones due the cultural differences, living habits and etc.. As we can see in the figure, the similarity of friends from the same country is the highest among the four categories, and the similarity of strangers from different countries is the lowest. Between the two extremes are the similarity distributions of same country strangers and different counrties friends. Based on the fact that the latter is higher than the former, we conclude that the bonds between you and your cross-counrty friends are stronger than the habits that you share with the people from your country.

### How far away are the strangers?

Do you know how different are the similarity between you and your buddies from the similarity between you and some guy on the other side of the world that you have never seem before?

Actually, they are not that different.

<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosineSimilarity_6Relationship" style="height:40px;width:230px" class="btn btn-outline-dark active" onclick="cosineSimilarity_6Relationship()">Cosine Similarity</button>
      <button type="button" id="mostCommon_6Relationship" style="height:40px;width:230px" class="btn btn-outline-dark" onclick="mostCommon_6Relationship()">Common Location</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>

<iframe id='cosineSimilarity6Relationship' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/6_relationship_cosine_similarity_2.html"></iframe>

<script>
var selected3 = "cosineSimilarity_6Relationship"
  
function cosineSimilarity_6Relationship(){
document.getElementById(selected3).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity6Relationship");
iframe.src = "plot/6_relationship_cosine_similarity_2.html"
selected3 = "cosineSimilarity_6Relationship"
document.getElementById(selected3).classList.add("active");
}
function mostCommon_6Relationship(){
document.getElementById(selected3).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity6Relationship");
iframe.src = "plot/6_relationship_most_common_2.html"
selected3 = "mostCommon_6Relationship"
document.getElementById(selected3).classList.add("active");
}
</script>

For friends from both same and different countries, we measure the similarity distribution of 1 to 5-edges friendships and the strangers. Undoubtedly, as the edge of the friendships grows, the similarity decrease. Among all, we noticed that the similarity of strangers falls approximately between the similarity of 4-edges and 5-edges friendship.

To see how far away the strangers are, let us start discussing from your 5-edges friends. As we can see in the figure, both distributions show that you are really far away from your 5-edges friends, and you are even far away from your different country ones. The difference between the two distributions lies the diversity of cultures and lifestyle of all the countries. Then as the number of edges decreases, the similarity between friends grows, and the gap between the same and different countries friendship decrease. Surprisingly, the gap is barely recognizable in the 1-edges friends plot! It appears that as the friendship is getting closer and closer, the bond that ties you and your cross-counrty friends together will the cultural differnce between you.


###  Is your friendship fading?

What about the variation of friendship over time? As you are making new friends, are you still hanging up with your old ones?

It seems not, does it?

<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosineSimilarity_change" style="height:40px;width:230px" class="btn btn-outline-dark active" onclick="cosineSimilarity_change()">Cosine Similarity</button>
      <button type="button" id="mostCommon_change" style="height:40px;width:230px" class="btn btn-outline-dark" onclick="mostCommon_change()">Common Location</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>


<iframe id='cosineSimilarityChange' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/cosine_similarity_difference_from_2012_to_2013.html"></iframe>

<script>
var selected2 = "cosineSimilarity_change"

function cosineSimilarity_change(){
document.getElementById(selected2).classList.remove("active");
var iframe = document.getElementById("cosineSimilarityChange");
iframe.src = "plot/cosine_similarity_difference_from_2012_to_2013.html"
selected2 = "cosineSimilarity_change"
document.getElementById(selected2).classList.add("active");
}

function mostCommon_change(){
document.getElementById(selected2).classList.remove("active");
var iframe = document.getElementById("cosineSimilarityChange");
iframe.src = "plot/most_common_difference_from_2012_to_2013.html"
selected2 = "mostCommon_change"
document.getElementById(selected2).classList.add("active");
}
</script>

For each pair of friends in 2014, we calculate difference between the similarity in 2013 and 2012 and group it by whether the friendship is a old one that exists in 2012 or it is a new one just made in these two years.

Compared with new friendships, the distributiion of the difference in similarity of old friendships puts more weights on negative values. According to the figure, on average, you and your old friends seem to have less commom place to go. Just like you to start to be fond of eating burgers and make new friends in fast food restaurant but your old friends are still having pizzas.


### Why do i keep bumping into you?
<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosine-Similarity-Location" style="height:40px;width:230px" class="btn btn-outline-dark active" onclick="cosineSimilarity_Location()">Cosine Similarity</button>
      <button type="button" id="most-Common-Location" style="height:40px;width:230px" class="btn btn-outline-dark" onclick="mostCommon_Location()">Common Location</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>

<iframe id='high-low-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="650" src="plot/cosineSimilarity_locations_boxplot.html"></iframe>

<script>
var selected4 = "cosine-Similarity-Location"
  
function cosineSimilarity_Location(){
document.getElementById(selected4).classList.remove("active");
var iframe = document.getElementById("high-low-similarity");
iframe.src = "plot/cosineSimilarity_locations_boxplot.html"
selected4 =  "cosine-Similarity-Location"
document.getElementById(selected4).classList.add("active");
}
function mostCommon_Location(){
document.getElementById(selected4).classList.remove("active");
var iframe = document.getElementById("high-low-similarity");
iframe.src = "plot/mostCommon_locations_boxplot.html"
selected4 =  "most-Common-Location"
document.getElementById(selected4).classList.add("active");
}
</script>


## Most Common Check-in Location Types in Different Countries
<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/wordcloud.html"></iframe>

## Periodic behaviors in Different Countries
<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/periodic.html"></iframe>

## Seasonality of Check-in Location Types in Different Countries
<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/seasonality_differentCountries.html"></iframe>

