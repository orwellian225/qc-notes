# Annotated Bibliography

## Strengths and Weakness of Quantum Computing

__Authors__: Charles H. Bennet, Ethan Berstein, Gilles Brassard, Umesh Vazirani

### Aim

To show that Quantum Computers do not exhausitvely address the classical computing class of NP problem, and there exists a set of intractable problems in both quantum and classical computing.

### Style

### Cross references

### Summary

## Ramsey numbers and adiabatic quantum computing

__Authors__: Frank Gaitan, Lane Clark

### Aim

To demonstrate the encoding a Ramsey number computation into a quantum system decision problem and to show an adiabatic quantum optimisation algorithm that can then decide that problem.

### Style

### Cross references

This report develops the quantum system encoding required for the AQO algorithm in the report and for the improved algorithm from Wang. This algorithm works on a quantum computer because Lloyd explains how any quantum system can be simulated by a quantum computer with tractability.

### Summary

## Universal Quantum Simulators

__Authors__: Seth Lloyd

### Aim

To showcase the capability and efficacy of a Universal Quantum Simulator as a Quantum Computing mechanism to solve classically hard computational problems.

### Style

Journal Article, Theoretical

### Cross references

This article shows that the algorithms in Gaiten and Wang are tractable with a quantum computer as they both convert the computation of Ramsey numbers into a decidability problem use quantam systems.

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
