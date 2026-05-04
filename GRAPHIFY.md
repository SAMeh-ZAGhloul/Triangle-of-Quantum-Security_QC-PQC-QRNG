# Graphified Overview

This file turns the project into a set of quick visual graphs so the architecture, workflow, and deliverables are easy to scan.

## 1. Triangle Architecture

```mermaid
graph TD
    QRNG[QRNG<br/>Quantum Random Number Generator]
    PQC[PQC<br/>Post-Quantum Cryptography]
    QKD[QKD / QC<br/>Quantum Key Distribution]
    APP[Protected Application Data]

    QRNG -->|entropy for keys, nonces, seeds| PQC
    QRNG -->|random basis and bit selection| QKD
    PQC -->|encrypts session material| APP
    QKD -->|protects key delivery and detects Eve| APP
    QRNG -->|foundation of unpredictability| APP

    QRNG --- PQC
    PQC --- QKD
    QKD --- QRNG
```

## 2. Security Workflow

```mermaid
flowchart LR
    A[Quantum Superposition] --> B[QRNG Output]
    B --> C[Key Material / Seeds]
    C --> D[PQC KEM]
    C --> E[BB84 QKD]
    D --> F[Shared Secret]
    E --> G[Sifted Secret Key]
    F --> H[Encrypted Payload]
    G --> H
    H --> I[Secure Quantum-Resilient Communication]
```

## 3. Assessment Tooling

```mermaid
graph LR
    QSRI[QSRI<br/>Readiness Assessment]
    QARS[QARS<br/>Risk Assessment]
    ORG[Organization]
    PLAN[Quantum Migration Plan]

    ORG --> QSRI
    ORG --> QARS
    QSRI -->|maturity gaps| PLAN
    QARS -->|asset risk priority| PLAN
```

## 4. Repo Deliverables

```mermaid
graph TD
    NB[triangle_of_quantum_security.ipynb]
    README[README.md]
    QSRIHTML[QSRI_Quantum-Security-Readiness-Index.html]
    QARSHTML[QARS_Quantum-Adjusted-Risk-Score.html]
    IMAGES[images/*]

    NB --> IMAGES
    NB --> README
    README --> QSRIHTML
    README --> QARSHTML
    README --> IMAGES
```

## 5. Reading Order

1. Start with the architecture graph to understand how QRNG, PQC, and QKD reinforce one another.
2. Follow the workflow graph to see how randomness becomes practical communication security.
3. Use QSRI and QARS together to map readiness and prioritize migration risk.
4. Open the notebook and images for the implementation-level walkthrough.
