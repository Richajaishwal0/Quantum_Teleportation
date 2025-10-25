# Quantum Teleportation

A small Qiskit-based quantum teleportation simulation and demonstration contained in `implementation.ipynb`.

This repository contains a Jupyter Notebook that builds and simulates the standard 3-qubit quantum teleportation circuit (Alice → Bob) using Qiskit and the Aer simulator. It also computes and visualizes the teleported qubit on a Bloch sphere and displays measurement histograms.

## What this project does

- Prepares an arbitrary single-qubit state on Alice's qubit.
- Creates an entangled Bell pair between Alice and Bob.
- Performs Alice's Bell-basis measurement and applies classical corrections to Bob's qubit.
- Simulates the circuit with Qiskit Aer and plots measurement outcomes.
- Computes the final statevector for verification and plots Bob's teleported qubit on the Bloch sphere.

## Files

- `implementation.ipynb` — The Jupyter notebook with the full code and visualizations.

## Requirements

The notebook was written to run in Google Colab or a local Jupyter environment. It relies on these Python packages:

- qiskit
- qiskit-aer
- matplotlib
- pylatexenc

(Exact versions are not pinned in this repo; the notebook includes inline `pip` commands for Colab.)

## Quick start — run locally (Windows PowerShell)

1. Create and activate a virtual environment (recommended):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2. Install required packages:

```powershell
pip install qiskit qiskit-aer matplotlib pylatexenc
```

3. Start Jupyter Lab / Notebook and open `implementation.ipynb`:

```powershell
jupyter notebook
# or
jupyter lab
```

4. Run the notebook cells. The notebook contains `!pip install ...` cells that are safe to run in Colab; for local runs you should install packages once as above.

## Quick start — run in Google Colab

Open a new Colab notebook and either upload `implementation.ipynb` or copy the code. The notebook includes `!pip install qiskit qiskit-aer pylatexenc --quiet` cells which make Colab execution straightforward.

# Deployement 
The ui based on this project is deployed at https://claude.ai/public/artifacts/df5c5c4e-9fc0-4fa6-bc11-eae47c906566
## Notebook highlights

- Circuit construction uses `QuantumCircuit(3, 2)` and prepares the state to teleport using `h` and `t` gates.
- Entanglement created with `h` and `cx`, Bell-measurement performed with `cx` / `h` and `measure`.
- Bob's corrections use `cx` and `cz` controlled by Alice's measurement bits.
- Simulation via `AerSimulator()` and `transpile(...)`.
- Verification via `Statevector.from_instruction(...)` and `partial_trace` to obtain Bob's reduced state. Bloch vector is computed and displayed.

## Expected outputs

- A histogram of Alice's measurement outcomes (classical bits).
- A Bloch-sphere rendering of Bob's teleported qubit (or printed Bloch-vector components).
- Printed density matrix for Bob's qubit (optional in the notebook).

## Notes & troubleshooting

- If you see LaTeX rendering issues when drawing circuits, the notebook sets `PYLATEXENC_LATEX_RUN=0` and suggests installing `pylatexenc` to avoid external LaTeX runs.
- Qiskit has changed APIs across major versions; the notebook was written to work with Qiskit 0.39+ / 0.40+ style imports and `qiskit-aer`. If you encounter import errors, ensure you have a recent Qiskit and that `qiskit-aer` is installed.

## Author

Repository Contributors:
`Richajaishwal0`
`NiteshSah `
`AniketSingh`
