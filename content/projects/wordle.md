+++
title = "Bot or Not?"
description = "investigating how my friend keeps solving every Wordle in three guesses"
[extra]
label = "w26"
link = "https://github.com/p-rallapally/wordle-detector"
+++

(tldr; I tried to use ML to determine whether or not my friend was cheating at Wordle. still unclear.)

**What it is** 

A machine learning classifier trained on simulated Wordle game data to distinguish "invalid" games from "valid" games, using features extracted from guess patterns and entropy reduction.

**Context** 

Every day, my friend group posts their Wordle results. One friend kept solving them in two or three guesses. He claims he's "lucky", but there's genuinely no way there isn't something going on. Since Wordle only shares the emoji grid (no actual guesses), I wondered whether those little squares still contained enough information to determine if someone was cheating or not.

At the time, I was enrolled in PSTAT 231 (Statistical Machine Learning), and it seemed like a good opportunity to try something out for the final project. 

**What I did** 

1) Built a Wordle simulator engine that replicated the game's feedback mechanics, tracked the remaining candidate solutions after each guess, and computed entropy throughout the game. 
2) Designed two gameplay strategies: valid (vibes + random mistakes) and invalid conditions (maximizing information gain per turn), since real Wordle data isn't explicitly labeled as "genuine" or "cheater"
3) Simulated 3000 games each and engineered behavorial and entropy-based[^1] metrics (entropy reduction, guess efficiency, color conversion, etc.) from the data
4) Trained and compared several model types and tested the best-performing one on a large Kaggle dataset

The resulting model performed well on the synthetic games and in theory, produced reasonable classifications when applied to the real Wordle games. 

*However,*

**What I learned** 

I realized that my assumptions for generating the synthetic data were somewhat flawed. I had associated a controlled and consistent decrease in entropy with suspicious behavior (as if someone were using a solver online [like this](https://www.thewordfinder.com/wordle-solver/)); in reality, people using shortcuts or point-blank Googling the answer would likely also have giant entropy drops, which the model would perceive as “human randomness”. 

Basically, I cooked myself from the start, and the gap between assumptions and IRL was too big to definitively prove anything. Shoot.

**What was hard**

Conceptualizing the simulator engine was pretty tough; my knowledge of algorithms at that point was limited to lists, arrays, and bogosort, and I had zero clue what the code would even look like. Additionally, trying to figure out how to codify "valid" vs "invalid" strategy was incredibly difficult as a thought experiment, and was substantially more difficult than any of the ML pipeline steps, since the assumptions I make would forever be baked into the model's classifications (clearly, this didn't work as well as I would have hoped).

This was also, at the time, the most computational-heavy thing I had ever done. Besides the simulator engine itself, I had to teach myself the basics of vectorizing and parallelization when scaling the engine inevitably bricked my unsuspecting MacBook's RAM and simulations became prohibitively slow. 


**in hindsight**

I was worried that I was wasting an opportunity by not doing something public health-related for the class project; ultimately, I figured it was worth going with my gut knowing I had the intellectual momentum to do something substantial and creative rather than shoehorn a middling diabetes prediction model. 

As it happens, my professor liked my project so much they wanted to showcase it as an example project for later classes; looks like my gut won out in the end :D

**up next?**

I was planning on deploying this into a website where the user could upload an emoji grid, and the model would return a thumbs up or down based on the classification. My itch for webdev has since been scratched by the RecRec so I'm unsure where the future lies for this, especially given that the model is built off of shaky assumptions anyway.


**links**

[github](https://github.com/p-rallapally/wordle-detector)

<a href="/Final-Project.html" target="_blank">report</a>


[^1]: basically, entropy = informatics term for wiggle room
