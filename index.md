---
layout: page
title: Friendship and Mobility
bigimg: img/globe.jpg
---
### How similar are you and your friends? 

### The Data

### Similarity of checkins' location

We investigate two types of the checkins' similarity between users in four categories of relationships. To calculate checkins' similarity we first estimate the probablity that a user is checking in each location. We call the vector the location probability vector, and estimate it by the numbers of checkins in each location over the total checkins. 

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





## Cosine Similarity of Location Type / Most Common 20 Location Types Change from 2012 to 2013
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


## Cosine Similarity of Location Type / Most Common 20 Location Types between 6 Relationship
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

## Most Common Check-in Location Types in Different Countries
<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/wordcloud.html"></iframe>

## Periodic behaviors in Different Countries
<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/periodic.html"></iframe>

## High / Low Similarity Location Type Between None-friend 
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

<iframe id='high-low-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/cosineSimilarity_locations.html"></iframe>

<script>
var selected4 = "cosine-Similarity-Location"
  
function cosineSimilarity_Location(){
document.getElementById(selected4).classList.remove("active");
var iframe = document.getElementById("high-low-similarity");
iframe.src = "plot/cosineSimilarity_locations.html"
selected4 =  "cosine-Similarity-Location"
document.getElementById(selected4).classList.add("active");
}
function mostCommon_Location(){
document.getElementById(selected4).classList.remove("active");
var iframe = document.getElementById("high-low-similarity");
iframe.src = "plot/mostCommon_locations.html"
selected4 =  "most-Common-Location"
document.getElementById(selected4).classList.add("active");
}
</script>
