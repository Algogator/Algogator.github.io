---
layout: post
title: "Greedy Algorithms"
---

# Greedy Algorithms

 - Pick the option that seems the "best" at the moment. 
 - Usually involves sorting on second endpoint

A classic greedy algorithm is Activity selection. Where you sort the lists according to finish times and pick the first activity to be printed. 

Then you check if the start time of the current activity is larger than the finish time of the previous one. If true you can add that too. 

![enter image description here](http://ycpcs.github.io/cs360-spring2015/lectures/images/lecture14/actselexample.png)

def find_max_activites(start_time, finish_time):

    indexes = range(len(start_time))
    indexes.sort(key=finish_time.__getitem__)

    start_time = map(start_time.__getitem__, indexes)
    finish_time = map(finish_time.__getitem__, indexes)
    
    count = 1
    curr = 0

    for i in range(1, len(start_time)):
        if start_time[i] >= finish_time[curr]:
            count += 1
            curr = i

    return count
