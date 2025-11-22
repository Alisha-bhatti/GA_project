1. Introduction 
In modern communication infrastructures, designing an efficient and reliable 
network topology is critical. As networks scale, the challenge becomes balancing the 
cost of building and maintaining connections with ensuring robustness against 
failures. Redundant paths are necessary for fault tolerance, but they come with 
added costs. This paper explores a solution using Genetic Algorithms (GA) to evolve 
network topologies that are both cost-effective and fault-tolerant. 
Genetic Algorithms are a class of evolutionary algorithms inspired by natural 
selection. They are particularly suitable for solving complex optimization problems 
with multiple constraints. This study applies GA to generate optimized network 
graphs that minimize total cost while maintaining high fault tolerance and 
acceptable communication performance. 
2. Problem Statement and Objectives 
The objective is to design a network topology for a set number of nodes that: 
• Minimizes the total cost of network links. 
• Ensures the network remains connected and fault-tolerant. 
• Maintains low communication delay (average path length). 
The problem is modeled as a graph, with vertices being routers or devices and 
edges being communication links with weights. The solution should be a connected graph 
with redundant paths for fault tolerance. 
3. Methodology: Genetic Algorithm Design 
The proposed GA-based method follows these steps: 
3.1 Chromosome Representation: Each individual (solution) is represented as a graph 
encoded using an edge list. Each gene is a link between two nodes, with a binary state 
indicating whether the link is active. 
3.2 Initialization: A population of random, connected network topologies is generated. 
Each topology includes nodes and a randomly selected set of edges. 
3.3 Fitness Function: The fitness of each topology is evaluated using: 
Fitness = (1 / Cost) + Redundancy + (1 / Average Path Length) 
• Cost: Sum of all active edge weights. 
• Redundancy: Average node connectivity (measuring fault tolerance). 
• Average Path Length: Efficiency of communication. 
3.4 Genetic Operators: 
• Selection: Top individuals based on fitness are selected. 
• Crossover: Edges from two parents are merged to form a child. 
• Mutation: Randomly adds or removes edges to introduce variation. 
• Repair: Ensures resulting graph remains connected. 
3.5 Termination Criteria: The algorithm runs for a fixed number of generations or until          
there is no improvement in the best solution. 
4. Implementation and Output 
The algorithm was implemented in Python using the NetworkX library. A population of 10 
network topologies was evolved over 50 generations. Each network consisted of 6 nodes. 
4.1 Output Description: 
• Nodes are visualized as blue circles. 
• Links are gray lines with cost values labeled. 
• The best graph reflects a topology that balances low total cost, short average path 
length, and high redundancy. 
4.2 Sample Output Metrics: 
• Total Cost: 28 (sum of selected link costs). 
• Redundancy: 2.3 (average number of disjoint paths). 
• Average Path Length: 1.8 hops. 
• Fitness Score: ~2.89 
This confirms that the GA successfully evolved a network design that maintains performance 
and fault tolerance within cost constraints.
