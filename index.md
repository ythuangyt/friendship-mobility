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

<iframe id='cosine-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/cosine_similarity_four_categories.html"></iframe>

<script>

function cosineSimilarity_4Categories(){
var iframe = document.getElementById("cosine-similarity");
iframe.src = "plot/cosine_similarity_four_categories.html"
}
function mostCommon_4Categories(){
var iframe = document.getElementById("cosine-similarity");
iframe.src = "plot/most_common_four_categories.html"
}


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

<iframe id='cosine-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_cosine_similarity_2.html"></iframe>

<script>

function cosineSimilarity_6Relationship(){
var iframe = document.getElementById("cosine-similarity");
iframe.src = "plot/6_relationship_cosine_similarity_2.html"
}
function mostCommon_6Relationship(){
var iframe = document.getElementById("cosine-similarity");
iframe.src = "plot/6_relationship_most_common_2.html"
}
