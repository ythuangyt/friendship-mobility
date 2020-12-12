---
layout: page
title: Friendship and Mobility
bigimg: img/globe.jpg
---
## How similar it is between friends' mobility pattern?
#### 

In this data story, we explore ...

## Cosine Similarity of Location Type between 6 Relationship

<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm">
    <div class="btn-group" role="group" aria-label="Basic example" style="margin-top: 2em;">
      <button type="button" id="redmeat" class="btn btn-outline-dark active" onclick="redMeat()">Red Meat</button>
      <button type="button" id="whitemeat" class="btn btn-outline-dark" onclick="whiteMeat()">White Meat</button>
    </div>
  </div>
  <div class="col-sm"></div>
</div>

<iframe id='cosine-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_cosine_similarity_2.html"></iframe>

<script>
var selected = "redmeat"
document.getElementById(selected).onclick = function() {
{
    var iframe = document.getElementById("cosine-similarity");
    if (iframe.src == "http://www.w3schools.com/") {
        iframe.src = "http://agar.io/";    
    }
    else {
        iframe.src = "http://www.w3schools.com/"
    }
}
</script>

<!-- <iframe id='cosine-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_cosine_similarity_2.html"></iframe>
<iframe id="most-common" frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_most_common_2.html"></iframe> -->

## Most Common 20 Locations Type between 6 Relationship

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_most_common_1.html"></iframe>
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="120%" height="550" src="plot/6_relationship_most_common_2.html"></iframe>
