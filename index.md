---
layout: page
title: Friendship and Mobility
bigimg: img/globe.jpg
---
## How similar it is between friends' mobility pattern?
#### 

In this data story, we explore ...

## Cosine Similarity of Location Type / Most Common 20 Location Types between 6 Relationship
<button style="height:200px;width:200px"></button>

<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="redmeat" class="btn btn-outline-dark active" onclick="cosineSimilarity()">Cosine Similarity</button>
      <button type="button" id="whitemeat" class="btn btn-outline-dark" onclick="mostCommon()">Most Common 20 Location Type</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>

<iframe id='cosine-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_cosine_similarity_2.html"></iframe>

<script>

function cosineSimilarity(){
var iframe = document.getElementById("cosine-similarity");
iframe.src = "plot/6_relationship_cosine_similarity_2.html"
}
function mostCommon(){
var iframe = document.getElementById("cosine-similarity");
iframe.src = "plot/6_relationship_most_common_2.html"
}
