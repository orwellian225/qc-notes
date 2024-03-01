# Annotated Bibliography

## Strengths and Weakness of Quantum Computing

__Authors__: Charles H. Bennet, Ethan Berstein, Gilles Brassard, Umesh Vazirani

### Aim

To show that Quantum Computers do not exhausitvely address the classical 
computing class of NP problem, and there exists a set of intractable problems 
in both quantum and classical computing.

### Style

### Cross references

### Summary

* Quantum Turing Machines (QTM) can solve problems in polynomial time, that would take a Classical Turing Machine (CTM)
exponential time.
* $BPP \neq BQP$
    * BPP -> Bounded-error Probabilistic Polynomial Time - The set of problems considered reasonably solvable on a CTM
    * BQP -> Bounded-error Quantum Polynomial Time - The set of problems considered reasonably solvable by a QTM.
    * QTM's are therefore more powerful then CTM's. Eg. Shor's quantum algorithm for factorising.
* Oracle - A Black Box TM that can solve a decision problem (any problem, including NP or undecidable)
    * Cost is one time unit, on arbitary input
    * The role of an oracle, is to be a tool that allows for developing efficient compuation analysis by assuming some
    NP Problem is efficiently solvable. Example: using the Oracle $O^{SAT}$, any TM can use $O^{SAT}$ to show that if $SAT$
    is P, then it's problem is P.
* A BQP TM can be used as a subroutine, because it is equivalent to a _tidy_ BQP TM that almost entirely holds the superposition of 
input and the single bit answer on the Tape.
* Non-determinism cannot be simulated on a QTM.
    * No such infinite parallism, constraints exist from quantum mechanics.
    * Quantum Inference: Quadratic speed up for NP problems.
    * If o($2^n) in classical, then at most o($\sqrt{2^n}$) in quantum
* Accuracy of a simulation:
    * calculating Euclidean distance from target superposition to simulation superpositions.
    * $\left|\phi\right> = \Sigma_{x}\alpha_x\left|x\right>$ & $\left|\psi\right> = \Sigma_{x}\beta_{x}\left|x\right>$
    have Euclidean distane $d_{\phi\psi} = \Sigma_x(\left|\alpha_x - \beta_x\right|^{2})^{1/2}
* QTM Primitives
    * QTM:
        * $\Sigma$ - finite alphabet with identified blank symbol
        * $Q$ - finite set of states, with $q_0$ as start, and $q_f$ as final.
        * $\delta$ - transition functions $\delta : Q\times\Sigma\rightarrow \overset{C}{~}^{\Sigma\times Q\times {L,R}}$
        * $\overset{C}{~}$ - set of complex numbers whith real and img part approximated to within $2^{-n}$ in time polynomial in $n$
    * Final Configuration: the configuration when in $q_f$.
    * Final Superposition: The superposition of $M$ at time $T$ when $M$ halts at $T$
    * Polynomial QTM: Well formed QTM which halts on input $x$ in time polynomial in the length of $x$


## Ramsey numbers and adiabatic quantum computing

__Authors__: Frank Gaitan, Lane Clark

### Aim

To demonstrate the encoding a Ramsey number computation into a quantum system 
decision problem and to show an adiabatic quantum optimisation algorithm that 
can then decide that problem.

### Style

### Cross references

This report develops the quantum system encoding required for the AQO algorithm in the report and for the improved 
algorithm from Wang. This algorithm works on a quantum computer because Lloyd explains how any quantum system can be 
simulated by a quantum computer with tractability.

### Summary

* Problem: Threshold value $R(m,n)$ exists for graph $N$ so that when $N \geq R(m,n)$, the graph will have $n$-cliques or
$m$ independent sets. (Two Colour Ramsey Numbers)
    * Simple graphs
    * Only 9 values known for two-colour ramsey numbers
    * Checking if $N=R(m,n)$ requires checking all $2^{N(N-1)/2}$ graphs
* Encoding:
    * Each simple graph $G$ has some (undirected $\Rightarrow$ symmetrical) adjacency $N\times N$ matrix $A(G)$
    * Taking the column-wise then row-wise concatanation of each $A(G)$ element below the diagonal, we build a binary
    string $(g(G))$ encoding of length $L=N(N-1)/2$ for any graph size $N$.
        * $N=3\Rightarrow g(G)=111\vee101\vee011\vee110\vee100\vee010\vee001\vee000
* Optimisation Problem construction:
    * Determining $m$-cliques: 
        1. Choose a subset of vertices (size $m$) $V_m$ from $V(G)$
        2. $V_m$ is a $m$-clique if $\Pi_{v\in V_m} = 1$
        4. $C(G)=\Sigma^{N}_{m=0} N \choose m*\Pi_{v\in V_m}$
        5. $C(G)$ is the number of $m$-cliques in $G$
    * Determining $n$-independent sets:
        1. Choose a subset of vertices (size $n$) $V_n$ from $V(G)$
        2. $V_n$ is a $n$-independent set if $\Pi_{v\in V_n} = 0$
        4. $I(G)=\Sigma^{N}_{n=0} N \choose n*(1 - \Pi_{v\in V_n})$
        5. $I(G)$ is the number of $n$-independent sets in $G$
    * $h(G) = I(G) + C(G)$
        * $h(G)$ is the cost function of an optimisation problem
        * Iff $h(G) = 0$ then $G$ has no cliques or independent sets
        * Globally minimise $h(G)$ to determine if $G$ has any cliques or independent sets
        * Via Ramsey Theory: If $|V(G_*)| = N$ and $N < R(m,n)$ then $h(G_*)=0$


## Universal Quantum Simulator

__Authors__: Seth Lloyd

### Aim

To showcase the capability and efficacy of a Universal Quantum Simulator as a Quantum Computing mechanism to solve 
classically hard computational problems.

### Style

Journal Article, Theoretical

### Cross references

This article shows that the algorithms in Gaiten and Wang are tractable with a quantum computer as they both convert 
the computation of Ramsey numbers into a decidability problem use quantam systems.

### Summary

* Quantum Computers can be used as a simulator for quantum systems.
    * An $N$-qubit computer can simulate an $N$-spin$\frac{1}{2}$ quantum system over time $t$
* Simulations work by applying Hamiltonians onto a system by a controlled distance, allowing for system dynamics to be modified in a controlled fashion.
    * Fixed distances are required because Hamiltonians evolve in fixed directions, requiring repeated operator combinations to modify the direction.
* Simulations appear to provide a exponential compression for an arbitary $m\times m$ $U$ unitary operator when compared to classical computing
  * This is false, as the same number of elementary operations by gate (logic or quantum) are required to construct $U$ for both classical and quantum computing.
  * Any large operator therefore has the same order of magnitude in complexity for both classical and quantum computing
* However, quantum computing is more efficient for local interaction systems, not arbitary systems
  * All systems consistent with general and special relativity evolve by local interactions.
  * Quantum simulation requires resources proportional to the system for simulation, whereas classical computers require exponential resources.

## Determine Ramsey numbers on a quantum computer

__Authors__: Hefeng Wang

### Aim

To present an improved quantum algorithm, compared to Gaiten, that decides if a given graph of size $n$ has atleast one $x$-clique or $y$-independent set within its structure via Ramsey Theory.

### Style

Theoretical, Report

### Cross references

Gaiten supplies a combinatorics and optimisation algorithmic solution to solving Ramsey numbers with an Adiabatic Quantum Optimisation algorithm. Using the same encoding as Gaiten to turn the computation of a Ramsey number into a decision problem, the report's alternate algorithm is able to evaluate the
same decision problem but avoids a probable degenerate ground state that is reached by the end of Gaiten's AQO algorithm.

### Summary
