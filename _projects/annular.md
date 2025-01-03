---
layout: page
title: Annular Structures in NetLogo Inspired by Brood Sorting in Ant Colonies
description: Distributed Artificial Intelligence project 2020/2021
img: assets/img/annular.png
importance: 1
category: university
related_publications: false
---
<div class="mb-4">
    <a href="https://github.com/apanariello4/annular-structures-netlogo" class="btn btn-primary me-2" target="_blank">
        🔗 View Code
    </a>
     <a href="https://github.com/apanariello4/annular-structures-netlogo/blob/main/Annular%20Structures%20in%20NetLogo%20Inspired%20by%20Brood%20Sorting%20in%20Ant%20Colonies.pdf" class="btn btn-info" target="_blank">
        📊 Slides
    </a>
</div>

This project is a simulation of the annular structures that emerge from the *Lepthotorax* ants behaviors which is an example of swarm intelligence.


## Ant-like annular sorting

*Leptothorax* ants, sort their larvae in an annular structure. This is because they evolved to live in the narrow cracks in rocks, thus having almost a two dimensional environment. Different brood stages are arranged in concentric rings, in a single cluster around the eggs and micro-larvae.



<div class="row">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="https://github.com/apanariello4/annular-structures-netlogo/blob/main/images/annularsorting.png?raw=true" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Theories

*Wilson et. al* (2004) were the first to study and implement such mechanisms. They followed two
different theories.

- **Theory 1**: brood structures form simply because objects are of different size. This is called “muesli effect” where the small particles percolate to the bottom of the packet (Barker and Grimson, 1990).
- **Theory 2**: ants deliberately introduce spacing between brood items with the amount of spacing influenced by the size of the brood, detected by the amount of waste gas the brood produces.

## NetLogo Setup

- Robots are turtles which move in approximately straight lines, turning around when hitting a wall or another turtle.
- Arena is square without warping.
- 6 robots and 15 objects per type.

## Performance Metrics

- **Separation**: computed by calculating the radial distance from the centre of the structure for each object. Sorting these according to the type provides a lower and upper quartile for each type. The distance between an object type lower and upper quartile defines the type’s “home zone”.

- **Compactness**: the ideal structure should be perfectly compact so that it fits into the smallest possible circular area. Finding the dimension of the circle is a complex geometrical problem, but the values for few object is known, so we take these to compare with our structure.
- **Shape**: we compute a clustering performance component that describes the central cluster and then we add the sum of the performances for each band.

## Mechanism 1: Object Clustering using Objects of Different Size

```
Rule 1: If (carrying object and obstacle ahead) then
        Make random turn away from obstacle.

Rule 2: If (carrying object and hit another object) then
        Reverse a small set distance which causes the object to be dropped.
        Make random turn left or right.

Rule 3: If (Not carrying any object) then
        Go forward
```

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="https://github.com/apanariello4/annular-structures-netlogo/blob/main/images/method1.png?raw=true" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Mechanism 2: Extended Differential Pullback
```
Rule 1: If (carrying object and obstacle ahead) then
        Make random turn away from obstacle and drop the object.

Rule 2: If (carrying object and hit another object) then
            If (carrying Type 1 object) then
                Drop the object.
            Else
                Pullback a distance relative to the object type
                and drop the object.

Rule 3: If (Not carrying any object) then
        Go forward
```
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="https://github.com/apanariello4/annular-structures-netlogo/blob/main/images/method2.png?raw=true" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Mechanism 3: Mechanism 3: Combined Leaky Integrator
```
Rule 1: If (carrying object and obstacle ahead) then
        Make random turn away from obstacle.

Rule 2: If (carrying object and hit another object) then
            If (carrying Type 1 object) then
                Drop the object and add 15 units to Type 1 integrator.
            Else If (carrying Type f object) then
                Pullback a distance relative to the sum of integrators 1 to f.
                Add 15 units to the Type f integrator.

Rule 3: If (Not carrying any object) then
        Go forward

Rule 4: If (Time counter reaches threshold) then
        Deduct 1 unit from all integrators and reset time counter.
```
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="https://github.com/apanariello4/annular-structures-netlogo/blob/main/images/method3.png?raw=true" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Conclusions

The Wilson et al study and my simulation, show that is indeed possible to have some sort of annular like sorting exploiting the behaviors of Leptothorax ants. We have seen that with simple algorithms, inspired by these ants, it is possible to reach good performances in the metrics that have been defined.

We have also found that the shape of the structure is influenced by the shape of the arena, thus it would be interesting to analyze this algorithm with different arena types.

In the future a probabilistic placement score, based on size and on the number of neighbors, for each object could be introduced, in order to let the agents to understand if it is beneficial to pick up or put down the objects.

## References

- Wilson, Matt, et al. "Algorithms for building annular structures with minimalist robots inspired by brood sorting in ant colonies." Autonomous Robots 17.2 (2004): 115-136.
- Franks, Nigel R., and Ana B. Sendova-Franks. "Brood sorting by ants: distributing the workload over the work-surface." Behavioral Ecology and Sociobiology 30.2 (1992): 109-123.
- Barker, G. C., and M. Grimson. "Physics of muesli: the science of powders." New Scientist 126 (1990): 37-40.
- Camazine, Scott. "Self-organizing pattern formation on the combs of honey bee colonies." Behavioral ecology and sociobiology 28.1 (1991): 61-76.
