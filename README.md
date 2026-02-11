# TinyMLFL_Privacy_Healthcare
The code is organised into modular Python scripts and includes:

Synthetic dataset generator – creates realistic EHR data with 16 clinical + 2 demographic features and a binary target, following the paper’s statistical characteristics.

TinyML model – a three‑layer neural network (16→8→4→2) suitable for resource‑constrained devices.

Adaptive Noise Injection (ANI) – gradient clipping and Gaussian noise addition with sensitivity‑aware scaling.

Authenticated Homomorphic Encryption (AHE) – CKKS encryption/decryption (via TenSEAL) plus RSA digital signatures for authentication.

Federated Learning simulation – server and clients with FedAvg, supporting IID / non‑IID data distribution.

Privacy attacks – membership inference attack to evaluate privacy leakage.

Performance evaluation – accuracy, privacy budget, attack success rate, latency, energy consumption, and convergence plots.

Baseline comparisons – FedAvg (no privacy), DP‑FedAvg (standard DP), SecureFed (only HE), and LocalTinyML.
All experiments can be reproduced by running main_experiment.py.
The code is self‑contained; dependencies are listed in requirements.txt
Project Structure
.
├── requirements.txt
├── dataset_generator.py          # Synthetic EHR generation + preprocessing
├── models.py                    # TinyML neural network
├── privacy_mechanisms.py       # ANI and AHE (CKKS + RSA)
├── fl_client.py               # Federated learning client
├── fl_server.py               # Federated learning server
├── attack.py                  # Membership inference attack
├── utils.py                   # Energy estimator, metrics, plotting
├── main_experiment.py        # Main experiment runner
└── README.md                 # Setup and execution instructions
