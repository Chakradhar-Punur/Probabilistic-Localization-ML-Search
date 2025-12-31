# Probabilistic Localization & ML-Guided Search

This project studies how an autonomous agent can localize itself in an unknown environment
under uncertainty using probabilistic reasoning, search, and machine learning.

The work is organized into three phases, corresponding to increasing levels of uncertainty
and sophistication.

---

## Phase 1: Deterministic Localization (Search-Based)
- Formulated localization as a state-space search problem
- Implemented optimal and heuristic search strategies
- Analyzed worst-case and average-case action complexity

## Phase 2: Probabilistic Localization (Bayesian Inference)
- Maintained a belief distribution over possible agent locations
- Updated beliefs using Bayesian inference after actions and noisy sensing
- Designed strategies balancing movement and sensing cost

## Phase 3: ML-Guided Search (Learning Heuristics)
- Generated datasets of belief states and optimal cost-to-go values
- Trained ML models to predict heuristic cost-to-go from belief features
- Integrated learned heuristics into A* search
- Achieved significant reductions in belief-state expansions

---

## Technologies
Python, A* Search, Bayesian Inference, Machine Learning, NumPy, Scikit-learn, PyTorch

---

## Results
- Learned heuristics reduced search expansions while preserving near-optimal solutions
- Performance evaluated across different sensor noise levels

---

## Author
Chakradhar Punur  
MS Computer Science, Rutgers University
