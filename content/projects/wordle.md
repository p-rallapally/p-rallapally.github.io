+++
title = "Bot or Not?"
description = "investigating how my friend keeps solving every Wordle in three guesses"
[extra]
label = " w26"
link = "https://github.com/p-rallapally/wordle-detector"
+++

(tldr; I built a machine learning model to determine whether my friend was cheating at Wordle and I'm still unsure if he is.)

**What it is** 

A machine learning classifier trained on simulated Wordle game data to distinguish "invalid" games from "valid" games, using features extracted from guess patterns and information gain.

**Context** 

Every day my friend group posts their Wordle results. One friend kept solving them in two or three guesses. He claims he's "lucky", but there's genuinely no way there isn't something going on. At the time, I was enrolled in PSTAT 231 (ML), and it seemed like a good opportunity to try something out for the final project. 

**What I did** 

Real Wordle data isn't labeled as fake/genuine, so I created a synthetic dataset by simulating both optimal (bot) and realistic (human) Wordle strategies, deriving behavorial and entropy-based[^1] metrics from those games, training a random forest classifier, and testing it on a public dataset from Kaggle. On synthetic test data, the model performed well and later identified a substantial subset of real Wordle games as exhibiting unusually solver-like behavior.

**What I learned:** 

I realized that my assumptions for generating the synthetic data were somewhat flawed. I had associated a controlled and consistent decrease in entropy with suspicious behavior (as if someone were using a solver online [like this](https://www.thewordfinder.com/wordle-solver/)); in reality, people using shortcuts and Googling the answer point-blank would likely also have giant entropy drops, which the model would perceive as “human randomness”. Basically, I cooked myself from the start.

This was also, at the time, the most computational-heavy thing I had ever done; throughout the process, I had to figure out how to design the valid vs invalid algorithms, implement that in code, and then subsequently teach myself parallelization when scaling inevitably bricked my unsuspecting MacBook's RAM.

**in hindsight**

I was worried that I was missing out by not doing something public health-related for the class project; ultimately, I figured it was worth going with my gut knowing I had the intellectual momentum to do something substantial and creative rather than shoehorn something like a middling diabetes prediction model. 

As it happens, my professor liked my project so much they wanted to showcase it as an example project for later classes; looks like my gut won out in the end :D

**up next?**

I was planning on deploying this into a website where the user could upload an emoji grid, and the model would return a thumbs up or down based on the classification. My itch for webdev has since been scratched by the RecRec so I'm unsure where the future lies for this, especially given the somewhat shaky assumptions the model is built off of.


**links**

[github](https://github.com/p-rallapally/wordle-detector)

<a href="/Final-Project.pdf" target="_blank">report</a>



[^1]: basically, entropy = amount of wiggle room
