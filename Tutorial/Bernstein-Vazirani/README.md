# References :

All the references for the theoritical concept of the Bernstein-Vazirani Algorithm are taken from this [link](https://medium.com/quantum-untangled/the-bernstein-vazirani-algorithm-quantum-algorithms-untangled-67e58d4a5096).

[Using Bernstein-Vazirani algorithm to attack block ciphers](https://link.springer.com/epdf/10.1007/s10623-018-0510-5?sharing_token=gTXm7VcOiSGDCeskJ-2vkve4RwlQNchNByi7wbcMAY4Pyjo41wSmZYy88ywP9pbRXF6-t04GEmUt30INRktvTmtLRFDdy8cW0sVjM1n6lqdobGd1aK1YGetG0_dOCl1sCBRZ1Bs3H6tO_Uj9jItHAFNmhzyDrA2hAzi1M9SCorM%3D) 

The theoritical concepts and step-by-step approach of Bernstein-Vazirani Algorithm is mentioned in the file **Bernstein-Vazirani_Notes.ipynb** file.
- Before performing benchmarks please go through that file for better understanding of Algorithm.

## Benchmark Statistics : 
These values are bounded according to my PC's Hardware capabilities, may vary according to your PC's configurations.

**Minimum** number of Qubits for Quantum Ckt: **3** (There is no implementation for using minimum qubits **<3** in this commit).

**Maximum** number of Qubits for Quantum Ckt: **14** (We have got Kernel-died error when going beyond this limit)

**Max-Circuits** used : Depends on how many secret integers we need to find out. (we have tested upto **10** circuits)

**Options_noisy** : It is the dictionary that has the error or noise values which might occur in physical Quantum computers. These can be adjusted as per user's requirements. Performed benchmarking in both ways (with and without noise parameters). 

```text
    Fidelity values (without using noise parameters) should be equal to 1.0
```

**Basis_Selector** : Checked all the prescribed basis which mainly effects the **circuit depth** and **transpiled depth** values.

|Parameter|Status|Remarks|
|---------|------|-------|
|min_qubits|3 qubits||
|max_qubits|14 qubits| Got error "Kernel-Died" for **max_qubits>14**|
|Max_circuits|10| Can be changed accordingly|
|Noise Parameters|Without Noise|options_noisy = { }|
||With noise |options_noisy = {"decoherence_factor": 0.9,"depolarization_factor": 0.9,"bell_depolarization_factor": 0.9,"decay_factor": 0.9}|
|Basis Selector|All possible Basis are checked||
|Methods| Method-1| **partial_probability** gives the correct result of measurements|
|| Method-2| **Partial_probability** fails here as there are no implementations for measurement of **<=2**. **Method-2** performs multiple measurements  and stores them to same classical bit repeatedly. So **Ensemble_probability** is used (but fidelity values *without noise* $\neq$ 1).|