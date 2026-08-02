+++
title = "HexSim"
description = "the sims! for frogs! name unrelated!"
weight = 2

[extra]
label = "f24-s25"
type = "🤓"
+++

(tldr; used hexagons and matrices to vanquish the pestilent bullfrog)

**What it is** 

A spatially explicit simulation model to predict invasive bullfrog populations and disease dynamics in Pleasanton Ridge Regional Park.

**Context**

- American bullfrogs are invasive and incredibly difficult to exterminate[^1]; simulation modeling provides a way to study population dynamics without relying on resource-intensive fieldwork
- First substantial on-campus research experience 

**What I did** 
1) Combed through every documentation of the [HexSim](https://www.hexsim.net/) software
2) Taught myself qGIS and parameterized the model using GIS data, field census data, and ecological literature
3) Built and refined life-history and movement processes with HexSim to simulate bullfrog population dynamics across Pleasanton Ridge 
4) Used simulation outputs[^2] to visualize individual trajectories and identify likely population + disease hotspots
5) Presented work at EEMB URS (won Best Poster), UCSB Undergrad Slam (was a Finalist), and RACA-CON (a CCS-exclusive research event)

**What was hard**
- HexSim as a software is incredibly feature-rich and comprehensive; it took me a while to figure out how to find the functionality I needed
- qGIS was a hill to climb
- Bullfrog parameters are surprisingly hard to come by; the few papers that had real measurements were straight from the 70s

**What I learned**

- Spatial modeling is awesome and easy on the eyes despite GIS software being hard on the brain
- I wanted to learn more about the behind the scenes behind how the modeling worked; I was hoping to be more involved with the mechanisms (versus plugging in values and hoping for the best). There's some very cool math going on in the underlying Leslie matrix models.
- I liked having a clear application; in this case, the obvious benefit of HexSim was that it allowed the (currently underfunded) park rangers to allocate manpower based on the model's predicted hotspots. I got to be on some very cool Zoom calls with the East Bay Parks Dept  
- The importance of marketing; making math-averse audiences care about simulation modeling 🤓 was initially a herculean task; framing HexSim like a video game (my go to was "the Sims for frogs") and slandering bullfrogs as insidious hellspawn had everyone eating out of the palm of my hand. I quite liked this part.


**In hindsight**

- Yet another push towards math and modeling 
- My lively presentation at the poster symposium ended up costing me at the Undergrad Slam for being "too theatrical"; the lesson learned here is to know your audience

**Links**

<a href="/urs copy.jpg" target="_blank">poster</a>



[^1]: Real things people have tried in the field include: catching by hand (too fast), crushing their eggs (easily replaceable), relocating them (they come back), putting up fences (they go over), shooting them with a gun (sounds hard because it is)

[^2]: How the simulations work: the map is split up into a grid of hexagons, each of with has its own environmental data gleaned from map photos with a collective habitability score. Based on the biological frog data, the software walks through time stages that predict where each individual will move throughout the map, repeated for a custom amount of organisms. 



