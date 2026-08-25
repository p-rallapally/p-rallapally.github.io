+++
title = "RecRec"
description = "please stop making me wake up at 6am"
weight = 2

[extra]
label = "s26"
type = "🤡"
+++

(tldr; selfish forecasting model became a recommender for the people)

**What it is**

A web application that predicts Rec Cen occupancy and generates personalized workout schedules based on a user's availability, workout goals, and crowd preferences.

**Context**

Like at many schools, the Rec Cen at UCSB has a tendency to be full during peak hours. Unfortunate for many reasons, the bigger ones being: 
1) Workouts take longer than they need to
2) I hate asking or being asked "how many sets do you have left?"

Luckily, the Rec Cen website [publicly displays](https://recreation.ucsb.edu/facilities/livecount) how many people are in each part of the gym. My initial pet project was to scrape the data and build a prediction model for myself to identify low/high-occupancy times (was eventually offloaded to my good friend and roommate [Erik](https://www.linkedin.com/in/erod298/)). Preliminary results, affirming common sense, revealed that the emptiest time —always and everywhere— was 6am.

No :)

This quarter, Erik and I were in PSTAT 134 (Stat. Data Science), so we figured we could build off our scraped data and prediction model to build a tiered recommender system that would incorporate workout preferences and preferred time slots to generate the ideal workout schedule. 

Going beyond the project requirements, I wanted to try making something the average person would actually use; specifically, a deployed + fully developed simple frontend.  

**What I[^1] did**

1) Built an automated data collection pipeline that scraped the UCSB Rec Cen API every five minutes
2) Engineered temporal/occupancy features (time of day, weekday, % filled, etc.) and trained multiple predictive models to predict facility occupancy
3) Designed a weighted scoring rec system that balanced predicted attendance vs timing/workout preferences
4) Helped build + deploy a full-stack web app that inputs a survey and outputs an ideal + alternate weekly schedule, with time + location

**What I learned**

- A lot about how deployment and frontend integration works 
- People can be incredibly finicky with data transparency 
- Claude is scary[^2]

**What was hard**

- I was beyond my depth past the modeling steps and was leaning hard on my CS major groupmates to guide me through the deployment process
- Storing the scraped data quickly became untenable; our solution was to use Erik's abandoned Android since we didn't have access to any free cloud services

**In hindsight**

- I would have been more aggressive at finding out how the attendance was determined; the Rec Cen department basically stonewalled all of our attempts at investigating the data sources and it adds a considerable question mark on the attendance counts
- I wish I made more commits to the Github repo; the repo's contribution graph is not looking great for me
- I ended up quickly caving to the 6am gym life anyway[^3]

**Up next?**

- As it turns out, there is an entire bustling [subfield](https://catalog.ucsb.edu/courses/PSTAT%20174) of statistics that deals specifically with forecasting; using those models would likely yield more robust results than the ML models we were familiar with
- Incorporating Rec Cen fitness classes into the occupancy predictions
- Reach out to the Rec Cen themselves to allow them to allocate staffing based on predicted occupancies

**Links**

[try it out!](https://rec-rec.gauchohosting.com/)

[github](https://github.com/ErikRodriguez29/Rec-Rec)


[^1]: this time, "I" = "we", being Erik, me, two German exchange students, and [Matthew](https://www.linkedin.com/in/matthew-zhang-1b3b23272/)
[^2]: Our group had initially put in our design into a single Claude prompt, and its frontend output was so good that we had disregard it entirely (else we wouldn't have learned anything meaningful)
[^3]: that said, it had several unexpected benefits, including forcing me to be more productive during the day and ensuring the best consistent sleep I've had in years. Sucked initially, but now it only sucks for my roommates who hear my 5:30 alarm (sorry not sorry, fellas).