# Quantum Artificial Intelligence

A research-grade, six-week masterclass on the mathematics and practice of quantum computing for
machine learning, built from first principles. In the spirit of building understanding from the
ground up, the course begins with **pure NumPy**: qubits are complex vectors, gates are unitary
matrices, and measurement is the Born rule applied by hand. Once the mechanics are transparent, the
course bridges to **PennyLane**, a production quantum-machine-learning framework with automatic
differentiation, so that the same concepts scale to real variational algorithms and hardware
back-ends.

The goal is not to take quantum software on faith. By the end, a reader will have implemented a
state-vector simulator, the canonical quantum algorithms (Deutsch–Jozsa, Grover, the quantum Fourier
transform), and a complete variational quantum classifier and quantum-kernel method — understanding
each at the level of the underlying linear algebra, and able to read a quantum-machine-learning paper
and reproduce its core experiment.

## Prerequisites

The material assumes comfort with linear algebra (complex vector spaces, inner products,
eigendecomposition, tensor/Kronecker products), basic probability, and Python with NumPy. Prior
exposure to classical machine learning (gradient descent, classifiers, kernels) is helpful for the
second half but is reintroduced from the quantum viewpoint where needed. No prior quantum physics is
required — the postulates are developed from scratch.

## Course structure

The course spans six weeks in three movements.

**Part I — Quantum foundations (Weeks 1–2).** The qubit as a complex unit vector, single- and
multi-qubit gates as unitaries, superposition, the Born rule for measurement, entanglement, and the
Bell states — all implemented as a from-scratch state-vector simulator.

**Part II — Quantum algorithms (Weeks 3–4).** The oracle/query model and quantum parallelism through
Deutsch–Jozsa; amplitude amplification in Grover search; the quantum Fourier transform; and the
crossover to variational circuits and the parameter-shift rule, where quantum computing meets
optimization. This is where we bridge to PennyLane.

**Part III — Quantum machine learning (Weeks 5–6).** Variational quantum classifiers and data
encoding (the feature map), the role of expressivity and barren plateaus, quantum kernel methods, and
a capstone comparing quantum and classical models on a shared task.

## Notebooks

| Week | Notebook | Topic |
|------|----------|-------|
| 1 | `01_qubits_states_gates.ipynb` | Qubits, the Bloch sphere, single-qubit gates, a from-scratch simulator |
| 2 | `02_entanglement_measurement.ipynb` | Multi-qubit states, tensor products, measurement, Bell states, CHSH |
| 3 | `03_quantum_algorithms.ipynb` | Oracles, Deutsch–Jozsa, Grover search, the quantum Fourier transform |
| 4 | `04_variational_circuits_pennylane.ipynb` | Parameter-shift rule, VQE, the bridge to PennyLane |
| 5 | `05_quantum_machine_learning.ipynb` | Data encoding, variational quantum classifiers, training and barren plateaus |
| 6 | `06_quantum_kernels_capstone.ipynb` | Quantum kernels, quantum vs classical comparison, capstone project |

Each notebook is self-contained: it develops the theory with full derivations, implements the method
from scratch (and/or in PennyLane), validates it against analytical results, and closes with graded
exercises.

## Tooling

Part I and the algorithmic core of Part II use **NumPy** only, so the reader sees every amplitude and
every unitary. Where variational training and automatic differentiation are essential — the
parameter-shift rule, VQE, quantum classifiers, quantum kernels — the course uses **PennyLane** with
its `default.qubit` simulator. The PennyLane circuits are written to mirror the from-scratch
implementations, making the bridge explicit.

## Getting started

```bash
git clone <repository-url>
cd quantum_artificial_intelligence
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Open the notebooks in order; later weeks build on the simulator and intuitions established earlier.

## License

Released for educational use. See repository settings for the applicable license.
