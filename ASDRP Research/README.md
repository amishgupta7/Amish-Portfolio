# ASDRP Research: Transformer-Based Fragment Prediction in Drug Discovery
**Status:** Manuscript Under Review (2025)

## Research Overview
My research at the **Aspiring Scholars Directed Research Program (ASDRP)** focuses on accelerating Fragment-Based Drug Discovery (FBDD). The goal was to determine if changing the "language" used to represent molecules could help AI models predict the best chemical fragments for a specific biological target more accurately than standard methods.

## Technical Methodology
Because the manuscript is currently under review, I have summarized my specific contributions and the technical pipeline below:

* **Target Selection (mTOR Kinase):** We built a custom dataset of 34,000 drug–fragment pairs targeting the mTOR kinase, chosen for its pharmacological importance and complex inhibitor landscape.
* **Dataset Engineering:** I worked with the **RECAP fragmentation algorithm** and a structured heuristic to score fragments based on molecular weight, logP limits (Rule-of-Three), and docking-based binding affinity.
* **The Representation Hypothesis:** We tested whether **DeepSMILES** (a syntactically robust molecular string) performed better than standard **SMILES**. I helped implement parallel transformer pipelines: **ChemBERTa** (for SMILES) and a custom **DeepBERTa** (for DeepSMILES).
* **Training & Guardrails:** I supported the implementation of a custom penalty term in the loss function. This ensured the model didn't just guess strings, but prioritized **chemical validity** (using RDKit checks) and **Tanimoto similarity**.
* **Optimization:** We used **Optuna** for hyperparameter tuning (learning rates, batch sizes, etc.) to ensure our results were reproducible and not just a result of "lucky" settings.

## Key Results & Findings
Our hybrid approach, which combined the strengths of both SMILES and DeepSMILES, showed significant improvements over baseline models:
* **Tanimoto Similarity:** The hybrid model reached a similarity score of **0.43**, significantly outperforming the individual SMILES (0.29) and DeepSMILES (0.36) models.
* **Chemical Validity:** Validity improved from 43.5% in standard models to **65.3%** in our combined method.

## My Contributions
* Supported model training runs and inference testing.
* Conducted evaluation workflows comparing predicted fragments using **Morgan fingerprints**.
* Validated output quality by reviewing cases where specific representations preserved key pharmacophoric elements better than others.
* Contributed to the editing and formatting of the technical manuscript.

---
*Note: Visualizations of the pipeline and results are included for verification.*
