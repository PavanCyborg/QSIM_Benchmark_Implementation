This repository is **DM_Simulator** based implementation of **QC-Application Oriented Benchmarks** framework. Aim of this repository is to benchmark the performance of algorithms mentioned in the **Application oriented Benchmark Suite** with the QSIM (Simulator) which works on the basis of dm_simulator.

# References :

To view that repository please go through the following link :
&nbsp;&nbsp;&nbsp;&nbsp;[QC-Application-Oriented-Benchmark-Suite](https://github.com/SRI-International/QC-App-Oriented-Benchmarks)

To Know more about this benchmarking framework please go through the following papers :

&nbsp;&nbsp;&nbsp;&nbsp;[Application-Oriented Performance Benchmarks for Quantum Computing](https://arxiv.org/abs/2110.03137)

&nbsp;&nbsp;&nbsp;&nbsp;[Optimization Applications as Quantum Performance Benchmarks](https://arxiv.org/abs/2302.02278)

&nbsp;&nbsp;&nbsp;&nbsp;[Quantum Algorithm Exploration using Application-Oriented Performance Benchmarks](https://arxiv.org/abs/2402.08985)

All the algorithms in the framework are benchmarked in **qiskit**, **cirq**, **bracket** environments.

Instructions for setting up the repository and further information regarding the benchmarks are already provided in &nbsp;&nbsp;&nbsp;&nbsp;[this Repository](https://github.com/SRI-International/QC-App-Oriented-Benchmarks)

# For DM_Simulator (QSIM):

For Using DM_Simulator kindly clone the following repository :
```bash
https://github.com/indian-institute-of-science-qc/qiskit-aakash/tree/terra_upgrade
```

**Note :** Use the hash id -> **bea98fbff86c234c0b1990add17493a1e86917cb** while cloning the above repository.

In this repository we have changed the &nbsp;&nbsp;&nbsp;&nbsp;[QC-Application-Oriented-Benchmark-Suite](https://github.com/SRI-International/QC-App-Oriented-Benchmarks) framework and made it into a single **.ipynb** file (for each algorithm) so that there will be no need dependencies.

All the algorithms of Benchmarking Suite are categorized into three types **Tutorial**, **Sub-routine** and **Functional**. So the same flow is maintained in this repository.

```text
The status of every algorithm in each category will be maintained in their corresponding directory.
```

# Installation Procedure :

1. Create an environment in Anaconda.
```bash
conda create -y -n QSIM python=3.8
```

2. Activate the environment
```bash
conda activate QSIM
```
(***Optional***) To deactivate the environment run the following command in terminal. 
```bash
conda deactivate
```

3. Clone the repository :
```bash
git clone -b terra_upgrade https://github.com/indian-institute-of-science-qc/qiskit-aakash.git
```

4. Go to the specified hash-id:
```bash
cd QSIM
git checkout -b dmsim bea98fbff86c234c0b1990add17493a1e86917cb
git log -n1
```

5. Installation of requirements :
Install ipython-genutils :
```bash
python -m pip install ipython-genutils
```
or
```bash
conda install -c conda-forge ipython_genutils
```
Install rustup :
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
python -m pip install setuptools-rust
```

Install requirements : If you want to run tests or linting checks, install the developer requirements.
```bash
pip install -r requirements-dev.txt

```
Install Qiskit-Aakash :
```bash
pip install .
```