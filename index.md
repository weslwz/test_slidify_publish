---
title       : ProjTracj -- an app for plotting the tracjectory of a projectile
subtitle    : 
author      : Luwei Zhou
job         : 
framework   : revealjs      # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## 1. What is ProjTracj?

1. ProjTracj stands for Projectile Trajectory.

2. ProjTracj is an educational tool for middle school students to learn simple physics concept.

--- .class #id 

## 2. How is ProjTracj used? 

1. ProjTracj is an application that plots the trajectory of a projectile in a frictionless envirnoment.

2. User can change the initial configuration of the projectile and a new trajectory is immediately updated.

--- .class #id 
## 3. How are the calculations done?


```r
    # Set up the initial condition
    g   <- 9.81              # gravity
    x0  <- 0                 # initial x position
    y0  <- 30                # initial y position
    s0  <- 30                # initial speed
    a0  <- 70                # initial angle
    vx0 <- s0*cos(a0/180*pi) # initial x velocity
    vy0 <- s0*sin(a0/180*pi) # initial y velocity

    # Calculate the time until the projectile hits ground
    t_hit <- (sqrt(vy0^2 + 2*g*y0) + vy0) / g

    print(t_hit)
```

```
## [1] 6.665
```


--- .class #id
 
## 4. How are the calculations done?


```r
    # Computes and plot the trajectory
    T <- seq(0, t_hit, length.out=300)
    X <- vx0 * T
    Y <- -0.5*g*T^2 + vy0*T + y0
    plot(X, Y, type="l", xlab="distance (m)", ylab="height (m)")
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2.png) 

--- .class #id 
## 5. Questions? Suggestions?

1. Application link: http://weslwz.shinyapps.io/projectile/

2. GitHub link: https://github.com/weslwz/DevelopingDataProductsProject.git

3. This presentation is done using slidify (http://ramnathv.github.io/slidify/)


 




