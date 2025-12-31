# Probabilistic Localization & ML-Guided Search

This project studies how an autonomous agent can localize itself in an unknown environment
under uncertainty using probabilistic reasoning, search, and machine learning.

The work is organized into three phases, corresponding to increasing levels of uncertainty
and sophistication.

---

## Phase 1: Deterministic Localization (Search-Based Planning)

In this phase, the localization problem is formulated as a **deterministic search task**
in a fully known environment with no sensing uncertainty.

### Problem Setting
- The agent starts at an unknown location within a known grid map
- The environment layout is fully known
- Actions have deterministic outcomes

### Approach
- Represented possible agent locations as a discrete state space
- Formulated localization as a **state-space search problem**
- Applied optimal and heuristic search techniques to identify the agent’s true location

### Search Strategy
- Used systematic exploration to eliminate inconsistent locations
- Applied admissible heuristics to guide search efficiently
- Guaranteed convergence to a unique agent location

### Evaluation
- Measured number of actions required to localize the agent
- Analyzed worst-case and average-case performance
- Compared optimal strategies with heuristic-based approaches

### Key Takeaways
- Deterministic search provides a strong baseline for localization
- Search complexity grows rapidly with environment size
- Efficient heuristics are critical even without uncertainty

## Phase 2: Probabilistic Localization (Bayesian Inference)

In this phase, the localization problem is extended to settings with **uncertain sensing**.
The agent no longer receives perfect information about its location and must reason
probabilistically using noisy observations.

### Problem Setting
- The agent may be located in any free cell of the environment
- A noisy sensor provides binary observations (beep / no-beep) based on distance
- The true agent location is hidden and must be inferred

### Approach
- Maintained a **belief distribution** over all possible agent locations
- Updated beliefs after each action using a **Bayesian transition model**
- Incorporated sensor observations using **Bayes’ rule**
- Ensured belief normalization after every update

### Action Strategy
- Alternated between sensing actions and movement actions
- Selected actions to reduce uncertainty while minimizing total cost
- Balanced exploration (information gain) with exploitation (moving toward likely locations)

### Evaluation
- Measured total number of actions (movement + sensing)
- Evaluated performance across varying sensor noise parameters (α)
- Compared against baseline deterministic strategies

### Key Takeaways
- Bayesian belief tracking enables localization under uncertainty
- Noisy sensing significantly increases planning complexity
- Intelligent sensing strategies can greatly reduce localization time
  
## Phase 3: ML-Guided Search (Learning Heuristics)

In this phase, machine learning is used to **accelerate belief-space search**
by learning heuristics that estimate the remaining cost-to-localization.

### Motivation
- A* search in belief space is optimal but computationally expensive
- Hand-crafted heuristics struggle to capture belief uncertainty
- Learned heuristics can exploit structure in belief distributions

### Dataset Generation
- Enumerated belief states encountered during optimal searches
- Computed true cost-to-go values for each belief state
- Extracted belief features such as:
  - Entropy of belief distribution
  - Distance statistics
  - Concentration of high-probability cells

### Model Training
- Trained supervised ML models to predict cost-to-go from belief features
- Used regression-based learning to approximate admissible heuristics
- Evaluated prediction accuracy and generalization

### Integration with A*
- Replaced hand-crafted heuristic with ML-predicted heuristic
- Used learned heuristic to guide A* search in belief space
- Ensured solution quality remained optimal or near-optimal

### Results
- Significantly reduced number of belief-state expansions
- Improved planning efficiency without sacrificing correctness
- Demonstrated practical benefits of learning-guided search

### Key Takeaways
- ML-based heuristics can dramatically improve search efficiency
- Learning complements classical AI planning rather than replacing it
- Hybrid AI systems outperform purely symbolic or purely learned approaches

---

## Technologies
Python, A* Search, Bayesian Inference, Machine Learning, NumPy, Scikit-learn, PyTorch

---

## Results
- Learned heuristics reduced search expansions while preserving near-optimal solutions
- Performance evaluated across different sensor noise levels

---

## Authors
- Chakradhar Punur
- Mohammed Najeebuddin Quadri
- MS Computer Science, Rutgers University
