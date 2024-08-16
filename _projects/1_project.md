---
layout: page
title: Flappy GPT
description: Using ChatGPT as a Game Engine to Run Flappy Bird
img: assets/img/flappy.jpg
importance: 1
category: LLM
related_publications: False
---

### Can ChatGPT Run Flappy Bird?

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="Flappy GPT setup" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Flappy Bird is a classic game where a bird (named Faby) avoids pipes by moving up and down. After seeing others attempt to use ChatGPT as a game engine for Flappy Bird, I took on the challenge to see if it could be done using LangChain and some prompt engineering. The goal was simple: use ChatGPT to generate the game state frame by frame without manually coding the game mechanics.

Setting Up the Project
Using LangChain, I designed a prompt system where the game state is represented in text, with the bird as > and pipes as |. The user could issue two commands: UP (bird moves up) and NEXT (advance the game with gravity pulling the bird down). The game logic and prompts were managed in a structured LangChain environment, relying on GPT-4-turbo.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/flappy.png" title="Flappy GPT visualization" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The output of GPT4 visualized for simulating the game. 
</div>

Challenges and Results
Despite setting clear rules and examples, GPT-4 struggled to maintain consistent game states and often ignored key mechanics, leading to incorrect or illogical outputs. This highlighted the importance of precise prompt engineering when working with LLMs.

Next Steps
Further refinement is necessary. Ideas for improvement include enhancing the system prompt, adding more few-shot examples, and possibly simplifying the game by removing the "DEAD" scenario.

Can You Do Better?
The project is available on GitHub, and I encourage others to try improving the prompt and see if they can succeed.

[GitHub - hesamsheikh/flappy-gpt: GPT as Game Engine to Run Flappy Bird](https://github.com/hesamsheikh/flappy-gpt)