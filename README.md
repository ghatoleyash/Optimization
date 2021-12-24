# Derivative Based Optimization

# Derivative Free Optimization
## Genetics Algorithm
A genetic algorithm is an optimization technique which is derivative free and based on randomization by analyzing the fitness function (objective function) of the population. The idea of genetic algorithms starts from selecting initial points at random called as initial population. Then evaluate the objective functions for the initial population, this evaluation helps in creation of new population. By delving deeper into this creation of new population there are certain manipulation/operations are performed called as cross-over and mutation. Repeating this procedure number of times until any stopping criteria (number of generations, difference of objective function between previous and current generation is small, etc) is met.

![alt text](https://github.com/ghatoleyash/TSP_GA/blob/main/Images/GA_flow.png)

### Chromosomes and Representation Schemes:
Since, genetic algorithms used for various optimization problems where real-valued optimal values are identified through iterative process. Hence, to represent the initial population of such problems there is encoding that has to be performed initially in order to understand mutation and cross-over easy. This encoding maps the real values to a set consisting of string of symbols with equal length which are termed as chromosomes, a common set used is binary string. The representation scheme identifies the length of the chromosome, once the scheme is identified initialize the population by selecting random points. However, in the case of Travelling Salesman Problem encoding is not required and each chromosome can be considered as the one of the path from origin city to the destination city by travelling each city once and this path may or may not be optimal in general, it is chosen at random and many of such random paths create initial population. 

### Evaluation:
Once the initial population is generated objective function is calculated for each of the chromosome for example in our case, it is the total distance from origin to destination city 
### Selection and Evolution:
For the first stage apply an operation of selection, where a set of mating pool is segregated equal to the initial population size based on random procedure such as for each chromosome proportion of objective function for that chromosome with total of all objective value for whole population is identified. Now, there exists two techniques for the selection of chromosome of which one is roulette wheel within, multiple chromosome are assigned to same slots and randomly from those slots chromosomes are picked and appended to the mating pool. One the other hand the other approach is tournament scheme where, select two chromosomes at random and compare their fitness value whichever is higher keep it in mating pool and similarly, perform this until the mating pool size is equal to population size.

<img src="https://github.com/ghatoleyash/TSP_GA/blob/main/Images/Selection.png" width=20% height=20%>

Next stage is the evolution where cross-over and mutation happens. The cross-over operation considers pair of chromosomes called as parents and generates a new off-spring chromosomes as given in the figure below, however the cross-over rate has to be chosen beforehand in order to cross those number of bits in the chromosome but the position may differ but number is constant.

<img src="https://github.com/ghatoleyash/TSP_GA/blob/main/Images/cross-over.png" width=50% height=50%>

Furthermore, mutation operation which takes each chromosome from the mating pool and randomly changes the order of the bits given by figure below or in the case of TSP change the order of subarray for a path and place it to different location in the whole path without having repeats since, we want to visit each city once. Here, as well there exist mutation rate which is the number of bits that can be changed and is given as an initial/static values.

![alt text](https://github.com/ghatoleyash/TSP_GA/blob/main/Images/mutation.png)

## Travelling Salesman Problem
Travelling Salesman problem can be termed as given a number of cities and their corresponding distance to travel to one another, we have to find the shortest route possible so that every city is travelled once and return back to the origin. With the brute-force approach it takes O(n!) time to find the optimal solution by taking every possible combination of routes and figuring out the optimal path.
