+++
title = "Bot or Not?"
description = "investigating how my friend keeps solving every Wordle in three guesses"
[extra]
label = " w26"
link = "https://github.com/p-rallapally/wordle-detector"
+++

**What it is:** A machine learning classifier trained on simulated Wordle game data to distinguish "invalid" games from "valid" games, using features extracted from guess patterns and information gain.

**Why:** There is literally no way my friend isn't cheating. At the time, I was enrolled in PSTAT 231 (ML), and it seemed like a good opportunity to try something out. 

**What I did:** Real Wordle data isn't labeled as fake/genuine, so I created synthetic dataset by simulating both optimal (bot) and realistic (human) Wordle strategies, deriving behavorial and entropy-based metrics, and training a random forest classifier.

**What I learned:** I realized that my assumptions for generating the synthetic data were somewhat flawed. I had associated a controlled and consistent decrease in entropy (wiggle room) with suspicious behavior (as if someone were using a solver online [like this](https://www.thewordfinder.com/wordle-solver/)); in reality, people using shortcuts and Googling the answer point-blank would likely also have giant entropy drops, which the model would perceive as “human randomness”. 


