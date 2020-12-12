---
layout: page
title: Friendship and Mobility
bigimg: img/globe.jpg
---
## How similar it is between friends' mobility pattern?
#### 

In this data story, we explore ...

## Cosine Similarity of Location Type / Most Common 20 Location Types between 4 Categories
<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosineSimilarity_4Categories" style="height:50px;width:300px" class="btn btn-outline-dark active" onclick="cosineSimilarity_4Categories()">Cosine Similarity</button>
      <button type="button" id="mostCommon_4Categories" style="height:50px;width:300px" class="btn btn-outline-dark" onclick="mostCommon_4Categories()">Most Common 20 Location Type</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>


<iframe id='cosineSimilarity4Categories' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/cosine_similarity_four_categories.html"></iframe>

<script>
var selected1 = "cosineSimilarity_4Categories"
  
function cosineSimilarity_4Categories(){
document.getElementById(selected1).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity4Categories");
iframe.src = "plot/cosine_similarity_four_categories.html"
selected = "cosineSimilarity_4Categories"
document.getElementById(selected1).classList.add("active");
}

function mostCommon_4Categories(){
document.getElementById(selected1).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity4Categories");
iframe.src = "plot/most_common_four_categories.html"
selected = "mostCommon_4Categories"
document.getElementById(selected1).classList.add("active");
}
</script>

## Cosine Similarity of Location Type / Most Common 20 Location Types Change from 2012 to 2013
<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosineSimilarity_change" style="height:50px;width:300px" class="btn btn-outline-dark active" onclick="cosineSimilarity_change()">Cosine Similarity</button>
      <button type="button" id="mostCommon_change" style="height:50px;width:300px" class="btn btn-outline-dark" onclick="mostCommon_change()">Most Common 20 Location Type</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>


<iframe id='cosineSimilarityChange' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/cosine_similarity_difference_from_2012_to_2013.html"></iframe>

<script>
var selected2 = "cosineSimilarity_change"

function cosineSimilarity_change(){
document.getElementById(selected2).classList.remove("active");
var iframe = document.getElementById("cosineSimilarityChange");
iframe.src = "plot/cosine_similarity_difference_from_2012_to_2013.html"
selected = "cosineSimilarity_change"
document.getElementById(selected2).classList.add("active");
}

function mostCommon_change(){
document.getElementById(selected2).classList.remove("active");
var iframe = document.getElementById("cosineSimilarityChange");
iframe.src = "plot/most_common_difference_from_2012_to_2013.html"
selected = "mostCommon_change"
document.getElementById(selected2).classList.add("active");
}
</script>


## Cosine Similarity of Location Type / Most Common 20 Location Types between 6 Relationship
<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="cosineSimilarity_6Relationship" style="height:50px;width:300px" class="btn btn-outline-dark active" onclick="cosineSimilarity_6Relationship()">Cosine Similarity</button>
      <button type="button" id="mostCommon_6Relationship" style="height:50px;width:300px" class="btn btn-outline-dark" onclick="mostCommon_6Relationship()">Most Common 20 Location Type</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>


<iframe id='cosineSimilarity6Relationship' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_cosine_similarity_2.html"></iframe>

<script>
var selected3 = "cosineSimilarity_6Relationship"
  
function cosineSimilarity_6Relationship(){
document.getElementById(selected3).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity6Relationship");
iframe.src = "plot/6_relationship_cosine_similarity_2.html"
selected = "cosineSimilarity_6Relationship"
document.getElementById(selected3).classList.add("active");
}
function mostCommon_6Relationship(){
document.getElementById(selected3).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity6Relationship");
iframe.src = "plot/6_relationship_most_common_2.html"
selected = "mostCommon_6Relationship"
document.getElementById(selected3).classList.add("active");
}
</script>
