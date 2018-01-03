---
layout: default 
title: Roster
site_nav_category_order: 201 
---
# Strava Roster
Going for a ride or run is always more fun when you have company.  A [study](https://www.nytimes.com/2017/04/19/well/move/running-may-be-socially-contagious.html) even validated the idea that having active friends can spur you to be more active yourself. I built the [Roster](https://labs.strava.com/roster) to allow any Strava athlete to visualize who they work out with the most.

![Roster]({{ "/assets/roster-top.png" | absolute_url }})
After authenticating the user, the athlete's workout history is retrieved, along with the activities of the athletes they were "matched" with. The total number of unique Strava athletes that the user has matched with is shown, along with a bar chart summarizing whether they tend to work out alone or with another person.  The user's Top Training Partners, broken down by sport type, are also shown. This view can then be shared via a [link](https://goo.gl/n8DHk3). Next, the user can explore their full workout history, organized by who they were with:

![Roster]({{ "/assets/roster.png" | absolute_url }})
Toggles allow filtering by year and sport and the d3 [tree layout](https://github.com/d3/d3-hierarchy/blob/master/README.md#tree) is used to group your workouts together with the athlete you were with. After expanding an athlete node, the timeline bar chart highlights the activities in which you were paired with that athlete. Hovering on an activity shows other athletes that also participated.  

The backend is hosted in a Scala Play app that allows access to Strava databases, using MySql queries and the Slick library. The app is hosted using our [Mesos/Marathon/Docker ecosystem](https://medium.com/strava-engineering/mesos-at-strava-5ac98d00dacf) which allowed for rapid deployment and iteration.  The frontend is deployed on Strava Labs and makes liberal use of various [d3 libraries](https://d3js.org/).  Check it out on [https://labs.strava.com/roster](https://labs.strava.com/roster). 

