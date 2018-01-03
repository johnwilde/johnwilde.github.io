---
layout: default 
title: Pack
site_nav_category_order: 202 
---
# Pack
The weekly group ride is something that most competitive cyclists participate in either occasionaly, or with fanatical regularity.  Living in San Francisco, I have the good fortune to be able to choose from a range of fun, fast and social weekly rides.  On Tue evenings during the summer months, there's TNPR (Tue Night Park Ride); every Tue and Thu morning there's the Palo Alto Morning Ride; on weekends there's the Roaster's ride in Marin and other rides in the East Bay. And there are many, many more here, and throughout the world.  These rides typically leave at a set time and place on a particular day of the week - and there is typically a Strava Segment that covers the interesting part of the ride.  For example: [Palo Alto Morning Ride](https://www.strava.com/segments/609552).

![Pack]({{ "/assets/pack-tmr.png" | absolute_url }})

I built this tool to reveal interesting information and trends about group rides and runs.  The user enters a Segment and the time and day at which the ride occurs and a chart similar to the one above is generated.  This example shows the Palo Alto Morning Ride, which departs every Thursday at 6:30 AM from Sand Hill Road.

There have been 301 occurances of the ride, going back to 2011 (there have been more, but this is as far back as Strava data extends).  The leader of the pack is Bill Lloyd, who particpated in 221 of the rides.  Hovering on the peloton-inspired [bubble chart](https://github.com/d3/d3-force) reveals other athletes, with the most frequent particpants at the front of the pack.  The bar chart shows the number of athletes on the ride (in blue) and the winning time (in red).  In general a larger group means a faster time, since there is more opportunity for drafting. Hovering on a bar shows the athlete with the fastest time on that day.  A data scrubber below the chart lets you explore further in the past.

![Pack]({{ "/assets/pack-roasters.png" | absolute_url }})

This example is from the [Roasters Ride](https://www.strava.com/segments/7091019), leaving Fairfax around 9 AM.  It shows the peloton chart filtered down to just the most-recent occurance, with other riders on the ride arranged further behind.


The backend is hosted in a Scala Play app that allows access to Strava databases, using MySql queries and the Slick library. The app is hosted using our [Mesos/Marathon/Docker ecosystem](https://medium.com/strava-engineering/mesos-at-strava-5ac98d00dacf) which allowed for rapid deployment and iteration.  The frontend was deployed on an internal-only Strava Labs site and makes liberal use of various [d3 libraries](https://d3js.org/).  

