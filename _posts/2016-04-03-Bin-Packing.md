---
layout: post
title: Bin Packing
desc: A bin packing web app intended to demonstrate the effectiveness of bin packing approximation algorithms.
proj-url: https://frigidrain.github.io/bin-packing
proj-num: 01
thumb: BinPacking.png
---

## Bin Packing

This is a bin packing web application intended to demonstrate the effectiveness of bin packing approximation algorithms. In the classic [bin packing problem](https://en.wikipedia.org/wiki/Bin_packing_problem), we want to pack a set of items of various weights into bins of equal size by using the least number of bins. It is very difficult to find the exact solution to this problem because it belongs to the set of [NP complete](https://en.wikipedia.org/wiki/NP-completeness) problems.

Instead, there are a set of [approximation algorithms](https://en.wikipedia.org/wiki/Approximation_algorithm) that will not find the optimal solution but will find a solution that is close to the optimal solution. In my web application, I explore the performance of two different algorithms named **first fit** and **first fit descending** through a simple game.

### First Fit

The first fit algorithm is the simplest algorithm that one can think of for solving the bin packing problem. For each item, we put it in the first bin that fits. If there are no bins where this item fits, we open a new bin and we put the item there. It can be shown that this algorithm produces a solution that is at most two times the optimal solution. That means if the optimal solution uses X bins then this solution uses at most 2X bins.

### First Fit Descending

The first fit descending algorithm is an improvement upon the first fit algorithm. We first sort our items in decreasing order and then we pack them in the same way that we pack them in first fit. It can be shown that this algorthm produces a solution that is at most one-and-a-half (3/2) times the optimal solution.

## Game

In this simple game, the player is a worker in a factory that is presumably in the business of packing boxes. Blue squares representing items of various sizes are generated to the left, with each square containing a number that indicates the weight of each box. The player's objective is to pack these items into each bin using the least amount of bins. The computer will run first fit and first fit descending described above to solve the problems. The player's aim is to solve the problem using less bins than the computer.

## Purpose

The purpose is to show that the approximation algorithms which do not find the exact solution perform quite well in practice. The player may have difficulty beating the computer's "dumb" approach to solving the problem. It is possible that the computer sometimes finds the optimal solution, in which case there is no way for the player to beat the computer.

To make the task of beating the computer simpler, the computer will take the worse solution out of first fit and first fit descending. The reason is that although first fit descending seems to be a better algorithm, it sometimes finds a worse solution than first fit in practice. This is also to make it less likely that the computer finds the optimal solution, in which case the user cannot do better.

## Technology

The web application was coded mainly in Javascript. I used the libraries [jQuery UI](https://jqueryui.com/) for the drag/drop functionality and [React.js](https://facebook.github.io/react/) for updating the user interface.

