---
layout: page
title: Someone Like You
cover-img: img/background_warm.JPG
---

Mobility is a part of the essence of life. It has opened many new doors to mankind and has allowed society to shape itself to what it is now. As Roman Payne said:
> A person does not grow from the ground like a vine or a tree, one is not part of a plot of land. Mankind has legs so it can wander.

For these reasons, human mobility is a topic that has always drawn attention of researchers. Many studies have been led around analyzing coarse-grained human mobility through statistical model. In this datastory, we extend our horizon and study **fine-grained** human mobility by looking at the evolution of human mobility on a day-to-day basis.

The dataset we used inlcudes long-term (2012.04-2014.01) global-scale checkins collected from the Foursquare application, as well as two snapshots of users' friendship before and after the checkin collection period. A checkin includes the User ID, the Location ID and the time at which it was taken. For each location, the dataset also provides the country of it, the latitude/longitude coordinates as well as the location type, which include "Post Office", "Pub" or even "Paella Restaurant" for a total of around 500 different categories. Using this dataset we will analyze the effect of multiple factors on the **similarity** of user's mobility.

### How to define similarity?
We use two criteria to estimate checkins' similarity, which are cosine similarity and intersection of most common visited location types. 
1. **Cosine Similarity**: We first estimate the probablity that a user is checking in each location, and call it the location probability vector. Namely, for each user, we calculate the vector by dividing the numbers of checkins in each location over the total number of checkins. The cosine similarity between two users is the normalized dot product of two users' location probability vector.
2. **Intersection of Most Common Visited Location Types**: We first find 20 locations that a user has the most checkins, then calculate the size of the intersection of the two users' commom locations.

### So, what could be the factors that influence the mobility?
Well for example, a factor that affect mobility is how **sociable** a user is! According to their number of friends, how unique do you think a user's movements in regards to other users with a similar number of friends is ? The following plot represents the median cosine similarity for users with similar sociability.

<p align="center"><iframe id='similarity_sociability_mean' frameborder="no" border="0" marginwidth="0" marginheight="0" width="67%" height="367" src="plot/CS_sociability.html"></iframe></p>

As the plot shows, in the group who has more friends, their cosine similarity with people who have approximatly as much friends is higher. Namely, people with higher sociability migh prefer to visit similar location types.

Another potential factor is the **average traveling distance of a user**. How similar is a group of users' mobility accoding to how far users usually travel from their house? The following plot shows the median cosine similarity for users with similar traveling distances.

<p align="center"><iframe id='similarity_distance_mean' frameborder="no" border="0" marginwidth="0" marginheight="0" width="66%" height="367" src="plot/CS_distance.html"></iframe></p>

The plot shows that on a smaller distance scale, the more a person travels, the less similar they are. This can be explained by a few things: first of all traveling somewhat obligates a person to vary its visits. People traveling a lot won't necessarly travel in the same places, which explains that their visits are different from one another. This explication seems satisfying but it cannot explain everything: indeed a group of people traveling an average of 5 km will have a much higher similarity than a group who travels in average 50 km, even though the difference between both average distances is not that large (50 km is still probably in the same city or in a neighbor one). 

Another thing worth notice is that, for much higher distances the similarity goes back up. This can be explained by the fact that users traveling very long distances will probably all check-in at a hotel or a restaurant, but not at their home!

After looking into this high-level investigation on similarity of two of people's features: sociability and average traveling distance, we are going to study fine-grained level human mobility in the following. Out of the many factors and relationships between humans, we study the effect of friendship (or strangerhood) on the similarity of mobility. In particular, we study the similarity from people around the world, to people living in the same country, then to pairs of friends.

### How close are you to your friends?

How similar are you and your friends' checkins' pattern? How often do you go to the same type of locations as your friends? Do you all enjoy Italian food and outdoor acticities?

We investigate two kinds of checkins' similarity between users in four categories of relationships and show the empirical distribution of the similarity in each categories.

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
As we expect, friends have more similar checkins than strangers, regardless of whether the friends are from different countries or not. Likewise, people from the same country shares more similarity than people from different ones due to cultural differences, living habits, etc...

As we can see in the figure, the similarity of friends from the same country is the highest among the four categories, and the similarity of strangers from different countries is the lowest. What gives us more information is that, different countries friends are more similar than same countries strangers. We conclude that the bonds between you and your cross-country friends are stronger than strangers living in the same country, even though he or she might share the same living habits with you, or you two have some visiting location types limits (unquestionably, it is harder to find a ramen shop in Switzerland than in Japan).

### How far away are the strangers?

Do you know how large are the similarity difference between you and your buddies, and between you and some guy on the other side of the world that you have never seen before?

Actually, they are not that different.

Consider each user as a node in a graph, and edges represent the friendship between users. 1-edge friends are those who are direct friends. 2-edges friends of one user are those whose distance to that user are 2-edges in the graph. The same rule applies to 3-5 edges friends.

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

For people from same and different countries, we measure the similarity distribution of 1 to 5-edges friends and pairs of strangers. Undoubtedly, as the edge number of the friends grows, the similarity decreases. Among all, we noticed that the similarity of pairs of strangers falls approximately between the similarity of 4-edges and 5-edges friends.

To see how far away the strangers are, let's first look into 5-edges friends. As we can see in the figure, distribution of cosine similarity and most common location types show that one is really far away from 5-edges friends, and even further away from the ones in a different country. Distribution difference of people from the same and different countries results from the diversity of cultures and lifestyles. As the number of edges decreases, the similarity between friends grows, and the gap between the same and different countries decreases. Surprisingly, the gap of same and different countries is barely recognizable between 1-edge friends! It appears that as the friendship is getting closer and closer, the bond that ties you and your cross-counrty friends will be stronger than the cultural differnce between two of you.


###  Is your friendship fading?

What about the variation of friendship over time? As you are making new friends, are you still hanging out with your old ones?

It seems not, does it?

For friendships being captured **after** all check-in data were collected (2014.01), we seperate them into two groups. Old friends are those who were already friends **before** check-in data were collected (2012.04). New friends are new connections within the collection periods. Between each pair of users, we calculate similarity change of them from 2012 to 2013, and report the histogram in the following.

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

Observed from the figure, the distribution of the similarity change of old friendships puts more weights on negative values, while changes in new friends tend toward positive values. On average, you and your old friends seem to not visit as many commom place as before. 

### Why do I keep bumping into you?

Do you ever feel that, you see a person at a certain place, say your yoga class, then keep on bumping into him or her at other unrelated places? Does that actually have any statistical sense? We focus on **local** check-in behaviors in this question, so we only look into the check-ins in one specific country. (We take US as our example, since check-in data amount in US are the most.) 

The following plot shows the quantile box plot for cosine similarity and common location similarity between non-friend users who check in at certain places, for quite a few location types.

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

In this figure, cosine similarity makes more sense than most common visited locations since the former captures ones' visiting **frequency** while the latter doesn't.

As the plot shows, those who are accustomed to yoga studios, gym, bar or nightclub will resemble each other more, even if they are total strangers! Also, who goes to hospital more frequently will be similar to each other since they might receive long-term treatment. On the contrary, people you meet in the restaurant and scenic lookout will be more like a random stranger pass by your life.

From above analyses, we see that people from different countries indeed visit different location types, due to many factors such as culture. How does that translate in practice? In the following, we study the periodic and non-periodic behaviors difference between countries.

### Do you know where people go in Japan?

Let's look at the most 50 common checkin location types for 10 major countries through the following word clouds. (You can choose the countries at dropdown button.)

<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/countries_most_visited.html"></iframe>

In US wordcloud, you can see the words with more American Style, such as "Burgers", "Steakhouse", "Mexican", "BBQ". In Japan, you can see the words with more Japanese style, such as "Ramen", "Noodle", "Train Station", "Shrine".

*Scenic Lookout* in Switzerland, *Hockey* in Canada, *Bakeries* in France and *Pub* in Great Britain? Sounds about right!

### What do you have planned for the winter?

How much do you think a user's movements depends on the season? 

Actually, quite a lot! 

<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/seasonality.html"></iframe>

It was to be expected, parks, outdoor activites, beach, ice cream shop experience a real drought in the winter. No one wants to walk around Hyde Park or sit on the beach in the freezing cold, right *mate*? Rather, shrines and temples in Japan are popular in winter since Japanese would visit these two places at the new year's eve to wish for happiness for the following year.

### And you, at what time do you go to work?

In addition to non-periodic behaviors, periodic behavior also demonstrate the cultural difference. For instance, is it likely that a Swiss resident and a Chinese resident follow the same working hours ?

Well not really! Let's look at the probability of checking-in office at different periods around the world.

<iframe id='mostCommon-countries' frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="550" src="plot/periodic.html"></iframe>

There indeed is a clear difference between the western world where most employees follow a 9-to-5 job, and the eastern world where it is more likely to start working later, but also stay working later!
