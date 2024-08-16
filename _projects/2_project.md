---
layout: page
title: A Performance Comparison Between KAN and MLP on the MNIST Dataset
description: How well do Kolmogorov–Arnold Networks perform on image classification?
img: assets/img/kan_2.jpg
importance: 1
category: Research
---

### Kolmogorov–Arnold Networks on Image Classification

I have written a [comperhensive guide](https://medium.com/towards-data-science/kolmogorov-arnold-networks-kan-e317b1b4d075) on Kolmogorov–Arnold Networks also known as KANs. As an extention of my fascination with the novel idea of KANs, I have explored if they also perform surprisingly well on image classification.

Despite the theoretical promise of KAN for handling complex functional approximations, the results were underwhelming. Using a network structure of [49,10,10] with grid 4, the best accuracy I could achieve was around 85%.

Comparing KAN with MLP
To put this in perspective, a simple MLP with only 3000 more parameters achieved over 90% accuracy on the same dataset. This significant difference raises questions about KAN's practicality in image recognition tasks, where MLPs and CNNs typically excel.

Potential Reasons for Lower Performance
The results suggest several potential causes for KAN’s underperformance on MNIST:

- Network Fit: KAN may lack the necessary complexity or depth for this task.
- Hyperparameter Tuning: Optimizers, learning rates, and epochs might not be well-suited for KAN.
- Data Preprocessing: The preprocessing techniques optimized for MLPs might not align with KAN’s requirements.
- Theory vs. Practice: The theoretical advantages of KAN don’t fully translate to practical tasks like image recognition.
- Loss Function Mismatch: Current loss functions might be biased toward MLP structures.
- Regularization Needs: KAN may require specific regularization methods that were not applied.
Conclusion
While KAN shows potential in theory, its practical application on tasks like MNIST may be limited. Further experimentation and refinement are needed to better understand its capabilities.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/kan_2.jpg" title="KAN vs. MLP on MNIST" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


[KAN Evaluation Repo on GitHub](https://github.com/hesamsheikh/kan_mnist)