# References :

All the references for explaining ***Deustch-Jozsa*** Algorithm are taken from this [link](https://medium.com/quantum-untangled/the-deutsch-jozsa-algorithm-math-circuits-and-code-quantum-algorithms-untangled-f3b28be4cfd3).

The theoritical concepts and step-by-step approach of **Deustch-Jozsa** Algorithm is mentioned in the file **DJ_Algorithm.ipynb** file.

- Before performing benchmarks please go through that file for better understanding of Algorithm.

## Benchmark Statistics : 
These values are bounded according to my PC's Hardware capabilities, may vary according to your PC's configurations.

**Minimum** number of Qubits for Quantum Ckt: **3** (There is no implementation for using minimum qubits **<3** in this commit).

**Maximum** number of Qubits for Quantum Ckt: **14** (We have got Kernel-died error when going beyond this limit)

**Max-Circuits** used : **2** one for constant oracle and other for Balanced oracle.

**Options_noisy** : It is the dictionary that has the error or noise values which might occur in physical Quantum computers. These can be adjusted as per user's requirements. Performed benchmarking in both ways (with and without noise parameters). 

```text
    Fidelity values (without using noise parameters) should be equal to 1.0. So if we are not using any noise parameters for executing circuits then Polarization and hellinger fidelity values will be 1.
```

**Basis_Selector** : Checked all the prescribed basis which mainly effects the **circuit depth** and **transpiled depth** values.

|Parameter|Status|Remarks|
|---------|------|-------|
|min_qubits|3 qubits||
|max_qubits|14 qubits| Got error "Kernel-Died" for **max_qubits>14**|
|Max_circuits|2| One Circuit for Constant Oracle and one for Balanced Oracle|
|Noise Parameters|Without Noise|options_noisy = { }|
||With noise |options_noisy = {"thermal_factor": 0.9,"decoherence_factor": 0.9,"depolarization_factor": 0.9,"decay_factor": 0.9} *rest remain same*|
|Basis Selector|All possible Basis are checked||
|Methods| Method-1| **partial_probability** gives the correct result of measurements|