# References :

All the references for the theoritical concept of the Bernstein-Vazirani Algorithm are taken from this [link](https://medium.com/quantum-untangled/grovers-algorithm-mathematics-circuits-and-code-quantum-algorithms-untangled-c4aa47d506e5).

The theoritical concepts and step-by-step approach of Grover's Search Algorithm is mentioned in the file Grovers_Algorithm.ipynb file.

- Before performing benchmarks please go through that file for better understanding of Algorithm.
- There are some changes in circuit implementation when we compare Benchmark circuit with the one which is implemented in Algorithm explaination.
- Base concept of both implementations remain same, but only differs as circuit.
- For better understanding of circuit in Benchmarking Program go through this [link](https://github.com/SRI-International/QC-App-Oriented-Benchmarks/tree/master/grovers).

# Benchmark Statistics :

These values are bounded according to my PC's Hardware capabilities, may vary according to your PC's configurations.

**Minimum number of Qubits for Quantum Ckt:** 3 (There is no implementation for using minimum qubits <3 in this commit).

**Maximum number of Qubits for Quantum Ckt:** 14 (We have got Kernel-died error when going beyond this limit)

**Max-Circuits used :** Depends on how many secret integers we need to find out. (we have tested upto 10 circuits)

**Options_noisy :** It is the dictionary that has the error or noise values which might occur in physical Quantum computers. These can be adjusted as per user's requirements. Performed benchmarking in both ways (with and without noise parameters).

```text
    Fidelity values (without using noise parameters) should be equal to 1.0
```

**Basis_Selector :** Checked all the prescribed basis which mainly effects the circuit depth and transpiled depth values.

|Parameter |Status|Remarks|
|----------|------|-------|
|min_qubits|3 qubits|
|max_qubits|14 qubits| Kernel-died after 14 Qubits|
|max_circuits|20||
|Noise Parameters|without noise|options_noisy = { }|
||with noise|options_noisy = {"decoherence_factor": 0.9,"depolarization_factor": 0.9,"bell_depolarization_factor": 0.9,"decay_factor": 0.9}|
|Basis Selector|All possible basis are checked|By default executed on Hardware Agostnic Basis|
|mcx_shim|Flase|All the average fidelities are above **0.9** (without any noise)|
||True| Average fidelity at 2 qubits drops to **0.8** for both Polarization and Hellinger Fidelities (without any noise)|