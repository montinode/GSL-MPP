
### 🔹 Datasets
All datasets used in the paper experiments are included here. Each molecule is stored as a SMILES string with its target property; the framework converts these into learnable graph structures.

### 🔹 Models
The heart of the GSL-MPP idea. Contains Python classes that:
- Build an initial adjacency matrix from molecular fingerprints.
- Run a **graph structure learner** to refine the topology (cosine, attention, kernel-based, etc.).
- Feed the learned graph through a **GNN encoder** (GIN, GCN, etc.) for final prediction.

All graph adjustments are **differentiable** and optimised end‑to‑end — the model literally *“thinks”* about which bonds matter most 🧬.

### 🔹 TrainingFramework
Handles the boring but essential parts:
- Scaffold splitting (chemical-aware train/val/test separation).
- Learning rate scheduling, early stopping, and metric tracking.
- The `ExperimentProcessController` that orchestrates hyperparameter search (greedy, grid, or custom).

### 🔹 example.py
A ready‑to‑run script that demonstrates the full pipeline in a few lines. Perfect for quickly testing a configuration or understanding the workflow.

---

##📶 Quick Start

```bash
# Clone repository
git clone https://github.com/your-lab/GSL-MPP.git
cd GSL-MPP

# Install dependencies (PyTorch, PyG, RDKit, etc.)
pip install -r requirements.txt

# Run the example
python example.py
