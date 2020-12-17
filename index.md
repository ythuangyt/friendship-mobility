---
layout: page
title: Someone Like You
bigimg: img/globe.jpg
---
### Introduction

Mobility is apart of the essence of life, it has opened many new doors to mankind and has allowed society to shape itself to what it is now. As Roman Payne said:
> A person does not grow from the ground like a vine or a tree, one is not part of a plot of land. Mankind has legs so it can wander.

For these reasons, human mobility is a topic that has always drawn attention of researchers. Many studies have been lead around analyzing coarse-grained human mobility through statistical model. Today, however, we extend our horizon and study fine-grained human mobility, by looking at the evolution of human mobility on a day-to-day basis.

The dataset we used inlcudes long-term (about two years) global-scale checkins collected from the Foursquare application, as well as two snapshots of users' friendship before and after the checkin collection period. A checkin includes the User ID, the Venue ID and the time at which it was taken. For each venue, the dataset also provides the country of location, the latitude/longitude coordinates as well as the venue category. Categories include "Post Office", "Pub" or even "Paella Restaurant" for a total of around 500 different categories. Using this dataset we will analyze the effect of multiple factors on the similarity of user's mobility through.

So what exactly are those factors ? Well for example, a factor that affect mobility is how sociable a user is! According to their number of friends, how unique do you think a user's movements in regards to other users with a similar number of friends is ? The following plot represents the median cosine similarity for users with similar sociability.

<p align="center"><iframe id='similarity_sociability_mean' frameborder="no" border="0" marginwidth="0" marginheight="0" width="67%" height="367" src="plot/CS_sociability.html"></iframe></p>

As the plot shows, the more friends a person has, the (slightly) less unique she is, in the sense that their cosine similarity with people who have approximatly as much friends is higher.

An explanation that comes to mind is that there are less users with a very high number of friends, so it could be expected that the "variance" in this group will less likely be large (it is less likely to find many "unique" users if the group of users is smaller). This could also be explained by the fact that the more a person has friends, the most likely they will get influenced by their friends, so their mouvements are usually less unique (and might follow trends).

Another potential factor is the average traveling distance of a user. How similar is a group of users' mobility accoding to how far users usually travel from their house? To study this we computed a house for each users and took the average distance between the user's home and the checkin's location. The following plot shows the median cosine similarity for users with similar traveling distances.

<p align="center"><iframe id='similarity_distance_mean' frameborder="no" border="0" marginwidth="0" marginheight="0" width="66%" height="367" src="plot/CS_distance.html"></iframe></p>

The plot shows that the more a person travels, the most "unique" it is, in the sense that their cosine similarity with people who travel approximatly as much is lower the more a person travels.

This can be explained by a few things: first of all traveling somewhat obligates a person to vary its visits: a Swiss citizen won't necessarly have many occasion to eat fondue if they travel a lot! People traveling a lot won't necessarly travel in the same places so it explains that their visits are different from one another. This explication seems satisfying but it cannot explain everything: indeed a group of people traveling an average of 5km will have a much higher similarity than a group who travels in average 50km (increase of 25%), even though the difference between both average distances is not that large (50km is still probably in the same city or in a neighbor one).

Out of the many factors and relashionships between humans we study the effect of frendship and strangerhood on the similarity of mobility.

### How close are you to your friends?

How similar are you and your friends checkins' pattern? How often do you go to the same type of locations as your friends? Do you all enjoy Italian food and outdoor acticities?

We investigate two types of the checkins' similarity between users in four categories of relationships. To calculate checkins' similarity we first estimate the probablity that a user is checking in each location, and call it the location probability vector. For each user, we estimate the vector by dividing the numbers of checkins in each location over their total checkins. 

For the first type of similarity, we calculate the cosine similarity between two users' location probability vector, and estimate the empirical distribution of the similarity in each categories. The commom location similarity is computed as the size of the intersection of the two users' commom location. The commom location of each user is defined as the twenty locations that a user has the most checkins.

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

<iframe id='cosineSimilarity4Categories' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/CS_4categories.html"></iframe>

<script>
var selected1 = "cosineSimilarity_4Categories"
  
function cosineSimilarity_4Categories(){
document.getElementById(selected1).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity4Categories");
iframe.src = "plot/CS_4categories.html"
selected1 = "cosineSimilarity_4Categories"
document.getElementById(selected1).classList.add("active");
}

function mostCommon_4Categories(){
document.getElementById(selected1).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity4Categories");
iframe.src = "plot/MC_4categories.html"
selected1 = "mostCommon_4Categories"
document.getElementById(selected1).classList.add("active");
}
</script>

Unquestionably, friends should have more similar checkins than strangers, regardless of whether the friends are from different countries or not. Likewise, people from the same country shares more similarity than people from different ones due the cultural differences, living habits and etc.. As we can see in the figure, the similarity of friends from the same country is the highest among the four categories, and the similarity of strangers from different countries is the lowest. Between the two extremes are the similarity distributions of same country strangers and different counrties friends. Based on the fact that the latter is higher than the former, we conclude that the bonds between you and your cross-counrty friends are stronger than the habits that you share with the people from your country.

### How far away are the strangers?

Do you know how different are the similarity between you and your buddies from the similarity between you and some guy on the other side of the world that you have never seen before?

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

<iframe id='cosineSimilarity6Relationship' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/CS_6relationships2.html"></iframe>

<script>
var selected3 = "cosineSimilarity_6Relationship"
  
function cosineSimilarity_6Relationship(){
document.getElementById(selected3).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity6Relationship");
iframe.src = "plot/CS_6relationships2.html"
selected3 = "cosineSimilarity_6Relationship"
document.getElementById(selected3).classList.add("active");
}
function mostCommon_6Relationship(){
document.getElementById(selected3).classList.remove("active");
var iframe = document.getElementById("cosineSimilarity6Relationship");
iframe.src = "plot/MC_6relationships2.html"
selected3 = "mostCommon_6Relationship"
document.getElementById(selected3).classList.add("active");
}
</script>

For friends from both same and different countries, we measure the similarity distribution of 1 to 5-edges friendships and the strangers. Undoubtedly, as the edge of the friendships grows, the similarity decrease. Among all, we noticed that the similarity of strangers falls approximately between the similarity of 4-edges and 5-edges friendship.

To see how far away the strangers are, let us start discussing from your 5-edges friends. As we can see in the figure, both distributions show that you are really far away from your 5-edges friends, and you are even further away from the ones ones in a different country. The difference between the two distributions lies the diversity of cultures and lifestyles. Then as the number of edges decreases, the similarity between friends grows, and the gap between the same and different countries friendship decrease. Surprisingly, the gap is barely recognizable between the two categories of 1-edges friends! It appears that as the friendship is getting closer and closer, the bond that ties you and your cross-counrty friends together will the cultural differnce between you.


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


<iframe id='cosineSimilarityChange' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/hist_friends_diff_CS.html"></iframe>

<script>
var selected2 = "cosineSimilarity_change"

function cosineSimilarity_change(){
document.getElementById(selected2).classList.remove("active");
var iframe = document.getElementById("cosineSimilarityChange");
iframe.src = "plot/hist_friends_diff_CS.html"
selected2 = "cosineSimilarity_change"
document.getElementById(selected2).classList.add("active");
}

function mostCommon_change(){
document.getElementById(selected2).classList.remove("active");
var iframe = document.getElementById("cosineSimilarityChange");
iframe.src = "plot/hist_friends_diff_MC.html"
selected2 = "mostCommon_change"
document.getElementById(selected2).classList.add("active");
}
</script>

For each pair of friends in 2014, we calculate difference between the similarity in 2013 and 2012 and group it by whether the friendship is a old one that exists in 2012 or it is a new one just made in these two years.

Compared with new friendships, the distributiion of the difference in similarity of old friendships puts more weights on negative values. According to the figure, on average, you and your old friends seem to have less commom place to go. Just like you to start to be fond of eating burgers and make new friends in fast food restaurant but your old friends are still having pizzas.


### Why do I keep bumping into you?

Does it ever feel like you see a person at a certain place, say your yoga class, then keep on bumping into them at other unrelated places ? Does that actually have any statistical sense ? The following plot shows the quantile box plot for cosine similarity and common location similarity between non-friend users who check in at certain places, for quite a few location types.

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

<iframe id='high-low-similarity' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="650" src="plot/CS_nonefriends.html"></iframe>

<script>
var selected4 = "cosine-Similarity-Location"
  
function cosineSimilarity_Location(){
document.getElementById(selected4).classList.remove("active");
var iframe = document.getElementById("high-low-similarity");
iframe.src = "plot/CS_nonefriends.html"
selected4 =  "cosine-Similarity-Location"
document.getElementById(selected4).classList.add("active");
}
function mostCommon_Location(){
document.getElementById(selected4).classList.remove("active");
var iframe = document.getElementById("high-low-similarity");
iframe.src = "plot/MC_nonefriends.html"
selected4 =  "most-Common-Location"
document.getElementById(selected4).classList.add("active");
}
</script>

As the plot shows, if you are accostumed to yoga studios, your movements are most likely very similar to any person that takes yoga classes too, even if that person is a total stranger! On the other hand if you meet a stranger at a diner, it is less likely that you two have similar preferences when it comes to visiting places. After all this makes sense: your passion for yoga could be the consequence (or the cause) of other hobbies, which is likely also the case for other yoga passionates. However, the fact that you often go to the diner won't reveal much about you as a person!


## Most Common Check-in Location Types in Different Countries

As mentioned before, having two persons in different countries makes a difference in places they visit, due to many factors such as culture. How does that translate in practice ? Let us look at the most common checkin location types for 10 major countries, through the following word clouds.

<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/countries_most_visited.html"></iframe>

Noodle places in Japan, bakeries in France and *soccer* fields in Great Britain? Sounds about right!


## Periodic behaviors in Different Countries

Another big cultural difference between countries lies in the periodic behavoir of the society. For example, is it likely that a Swiss citizen and a Chinese citizen follow the same work hours ?

Well not really! Let us look at the distribution of checkins at the office throughout the world, as a function of time.

<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/periodic.html"></iframe>

There indeed is a clear difference between the western world where most employees follow a 9-to-5 job, and the eastern world where it is more likely to start working later, but also stay working later!

## Seasonality of Check-in Location Types in Different Countries

A person's movements is very complex to understand, as it includes many factors, one of which is the time of the year! How much do you think a user's movements depends on the season? Actually, quite a lot! The following plots show the distribution of checkins for some location type in 4 major countries.

<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/seasonality.html"></iframe>

As it was to be expected, parks in Great Britain experience a real drought in the winter! This makes sense, no one wants to walk around Hyde Park in the freezing cold, right *mate*? It seems, however, that other locations do not follow this pattern. Shrines in Japan see their popularity doubled since almost all the Japanese gather to the shrines to wish for happiness for the following year at the new year's eve.
