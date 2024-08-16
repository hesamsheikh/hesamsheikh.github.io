---
layout: page
title: Creating a Synthetic Dataset with Llama 3.1
description: Using Llama 3.1 405B and Nvidia Nemotron 4 to Generate and Filter a Synthetic Data of Git Commands in Natural Language
img: assets/img/llama1.jpg
importance: 2
category: LLM
---

In this project, I used Llama 3.1 405B to generate a synthetic dataset of Git commands in natural language, leveraging Nvidia’s NIM API to access the model without the need for extensive hardware. The process involved generating subtopics related to Git, creating a set of instructions for each subtopic, and then generating concise, informative responses for these instructions. To ensure the quality of the dataset, I utilized Nvidia’s Nemotron 4 reward model to filter out low-quality responses based on helpfulness and verbosity.

Finally, the curated dataset was uploaded to HuggingFace for future fine-tuning of LLMs. This approach demonstrates how powerful tools like Llama 3.1 and Nemotron 4 can be used to efficiently create high-quality synthetic datasets, offering a practical solution for those needing specialized data without the associated costs of large-scale data collection and annotation.

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/llama2.jpg" title="AI Agent Workflow" class="img-fluid rounded z-depth-1"%}
  </div>
</div>
<div class="caption">
    Workflow of creating a synthetic data
</div>

[Read the Full Article in Detail](https://towardsdatascience.com/create-a-synthetic-dataset-using-llama-3-1-405b-for-instruction-fine-tuning-9afc22fb6eef)