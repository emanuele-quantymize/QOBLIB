# iECO submission for sloane_1zc_128

This directory contains a sanitized QOBLIB submission for the `sloane_1zc_128` maximum independent-set instance. iECO stands for iterative efficient correlated optimization.

- Submitter: Emanuele Dalla Torre
- Affiliation: QuantyMize Quantum Advance Ltd
- Reference: https://www.quantymize.com/

## Result

- Best objective: 18
- Independent repetitions: 5
- Feasible runs after the declared workflow: 5
- Successful runs at epsilon 0: 5
- Quantum iterations per run: 1
- Shots per run: 2,024
- Mean QPU execution-span window: 2.0102 seconds
- Mean CPU runtime for the instance-specific workflow: 0.2631 seconds
- Median CPU runtime for the instance-specific workflow: 0.2590 seconds
- Mean total runtime excluding protocol setup, compilation, provider communication, and queue time: 2.2733 seconds

Only aggregate benchmark information and one verified final solution are included. Shot-level samples, count dictionaries, provider job payloads, job identifiers, private bitstrings, and per-run traces are deliberately excluded.

## Model and workflow

The 128-vertex, 1,120-edge MIS instance is represented by the integer-coefficient QUBO

`minimize -sum_v x_v + 2 sum_(u,v in E) x_u x_v`.

The circuits use Qiskit optimization level 0, with gate twirling and dynamical decoupling disabled. Each circuit is sampled 2,024 times. Measured candidates undergo the disclosed classical post-processing, and the best feasible result obtained is reported. Classical post-processing is therefore an essential, disclosed part of the workflow.

## Hardware and software

- QPU: IBM Quantum `ibm_kingston`
- CPU: Intel Core Ultra 7 155U
- Python 3.14.4
- Qiskit 2.4.0
- qiskit-ibm-runtime 0.46.1
- NumPy 2.4.4

QPU runtime is the mean duration of the IBM Sampler execution-span metadata, excluding queue time. CPU runtime covers the instance-specific classical workflow: hardware-topology-aware mapping, circuit construction, greedy conflict repair, maximal independent-set expansion, and selection of the best feasible result obtained. A generic mapping of the QPU topology is pre-established as part of the protocol; its one-time preparation is excluded. Circuit compilation, provider communication, and queue time are also excluded.

## Disclosure boundary

The `.sol` file is the required processed final answer used by the QOBLIB feasibility checker; it is not a raw QPU sample. No raw experimental data is part of this submission package.
