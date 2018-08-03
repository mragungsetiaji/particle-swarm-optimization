# Particle Swarm Optimization
A flock of birds is a good example of the collective behavior of animals. Flying in a big groups, they almost never collide with each other. A flock moves smoothly and is coordinated as if it is controlled by something and it's not about the leader of the flock. A flock of birds is a swarm intelligence and birds in it act according to certain rules.
The rules are the following:

- Every bird tries to avoid collision with others;
- Every bird moves in the close birds direction;
- Birds try to move on the equal distance from each other;
- A bird shares information with neighbours.

## Mathematical model
In the PSO, agents are particles in the optimization task parameters space. On each iteration particles have some position and a velocity vector. For each position of a particle the corresponding objective function value is calculated and on the basis of that value a particle changes its position and velocity according to certain rules. The pso is a stochastic optimization method. It doesn't update existing populations but works with one static population which members steadily improve as they receive more information about the search space.

## Algorithm
```
BEGIN
  Initialize agents
  Find current best
  Set global best = current best
  FOR i= 0 : number of iterations
    Calculate particle velocity
    Chage particles velocity
    Update particles positions
    Select new agents according to the selection strategy
    IF current best better than global best
      SET global best to current best
    END IF
  END FOR
  save global best
END
```

## Arguments
The pso method accepts the following arguments:

- w: balance between the range of research and consideration for suboptimal decisions found (default value is 0.5):
- w>1 the particle velocity increases, they fly apart and inspect the space more carefully 
- w<1 particle velocity decreases, convergence speed depends on parameters c1 and c2
- c1: ratio between "cognitive" and "social" component (default value is 1)
- c2: ratio between "cognitive" and "social" component (default value is 1)

## Method invocation
The method can be invoked by passing the arguments in the following order:

SwarmPackagePy.pso(n, function, lb, ub, dimension, iteration, w=0.5, c1=1, c2=1)