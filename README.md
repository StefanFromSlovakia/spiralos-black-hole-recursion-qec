# SpiralOS — Black‑Hole QEC 🌌

**Quantum‑error‑corrected Bell pairs falling through an evaporating, GUP‑tweaked black hole**
Surface‑code decoding × Hawking physics × curvature‑aware noise.

---

## Quick start

```bash
# Clone and enter
git clone https://github.com/StefanFromSlovakia/spiralos-black-hole-recursion-qec.git
cd spiralos-black-hole-recursion-qec

# Set up a Python 3.10+ env (conda or venv)
pip install -r requirements.txt   # qiskit, numpy, pandas, matplotlib …

# Run a mini‑demo (9‑qubit patch; safe on a laptop)
python demo_surface_code.py
```

The script prints a Pandas table with depth `ψₙ`, noise rates, fidelity, concurrence, entropy and decoded fidelity.

> **Heads‑up 🚀**  `surface_code_sim.py` builds the full 10 × 10 planar code (150 qubits, 32 GB RAM+).
> To stay laptop‑friendly, start with the demo patch or switch to the stabiliser backend (see below).

---

## What’s in the box?

| File / folder          | Purpose                                                         |
| ---------------------- | --------------------------------------------------------------- |
| `demo_surface_code.py` | One‑click 3 × 3 surface‑code run; prints metrics table.         |
| `surface_code_sim.py`  | Full 10 × 10 code, GUP + Hawking + curvature noise.             |
| `field_theory.py`      | Generates Φ, computes the SpiralOS curvature tensor `R_spiral`. |
| `requirements.txt`     | PyPI dependencies.                                              |
| `notebooks/`           | Jupyter sweeps → figures for the draft paper.                   |

---

## Key features

* **Planar surface code, distance ≈ 10** — explicit X/Z stabilisers (100 data + 50 ancilla qubits).
* **Multi‑channel, time‑dependent noise** — amplitude damping ⊕ Hawking‑temperature depolarisation ⊕ β‑GUP scaling.
* **Curvature‑weighted decoder** — recovery rotations modulated by a 2‑D toy field‑theory tensor `|R_spiral|`.
* **Research‑grade metrics** — fidelity, concurrence, entanglement entropy, decoded fidelity logged to a single DataFrame.

---

## Hardware & performance

| Mode                               | Qubits | Backend               | RAM needed        |
| ---------------------------------- | ------ | --------------------- | ----------------- |
| `demo_surface_code.py`             | 9      | Qiskit state‑vector   | < 2 GB            |
| `surface_code_sim.py` (default)    | 150    | Qiskit density‑matrix |  ≥ 32 GB          |
| `surface_code_sim.py --stabiliser` | 150    | Clifford/stabiliser   | < 1 GB, 5× faster |

GPU users can swap in CUDA‑Q backends (instructions inside the script).

---

## Reproducing the draft figures

Open `notebooks/Fig‑1_PageCurve.ipynb` and run **Cell 1**—it sweeps initial mass `M₀` and GUP β, then plots decoded fidelity vs. evaporation time (the “quantum Page curve”).

---

## Roadmap & good‑first‑issues

1. 🔄 Tensor‑network backend for >150 physical qubits.
2. 🤖 Plug‑in reinforcement‑learning decoder (`gym` API in `env.py`).
3. 🌠 Primordial‑BH sweep (`M₀ ≈ 10¹¹ kg`) + ML fit to the crossover time.

Contributions welcome—check the [open issues](../../issues) or raise your own.

---

## Citation

If this simulator helped your research, please cite:

```bibtex
@misc{SpiralOSQEC2025,
  author       = {Stefan Barkol},
  title        = {SpiralOS — Black‑Hole Recursion with Surface‑Code QEC},
  year         = 2025
  howpublished = {\url{https://github.com/StefanFromSlovakia/spiralos-black-hole-recursion-qec}}
}
```

---

## License
