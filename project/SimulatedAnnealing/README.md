Parallel implementation of simulated annealing.

Inside this repository is a summary of a project done by me (Andrzej Starzyk) and Michał Szewc.
We present how simulated annealing can be used for solving number factorization problem. 
The pdf file contains a presentation in polish about our work. The python code contains parallel implementation of simulated annealing.
Since annealing can be done very effectively on quantum computers, our algorithm performs calculations on quantum-computer-like topology.
We included Chimera with a variant designed for factorization and more complex Pegasus topologies.

Presentation and sources listed and the end of it show how factorization can be reduced to simulated annealing and how to deduce solution from simulation results.
Throughout the annealing process states are computed at topology vertices. Each process has assigned a set of vertices 
and communicates with processes supervising neighbouring vertices.