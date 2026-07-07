## 🥉Kaggle AI Mathematical Olympiad Progress Prize3 Bronze (My Solution)

# Overview and goal

The AI Mathematical Olympiad - Progress Prize 3 (AIMO3) is a Kaggle competition designed to advance the mathematical reasoning capabilities of open-source large language models (LLMs). Unlike conventional NLP tasks, participants must develop AI systems capable of solving previously unseen Olympiad-level mathematics problems that require multi-step logical reasoning rather than memorized knowledge.
The objective of the competition is to predict the correct integer answer (0–99,999) for each mathematical problem written in LaTeX format. Solutions are evaluated based on the accuracy of the predicted answers while operating under limited computational resources and strict inference constraints. The competition encourages the development of efficient inference pipelines and robust mathematical reasoning techniques for open-source LLMs.

# Approach

Our solution is based on an ensemble of open-source large language models (LLMs) combined with a robust inference strategy to improve mathematical reasoning performance.
The inference pipeline first generates multiple candidate solutions for each Olympiad-level mathematics problem using carefully designed prompts. Candidate answers are then aggregated through a majority voting strategy, where the most frequently predicted integer answer is selected as the final prediction. This approach improves robustness against the stochastic nature of LLM inference.
To further enhance performance, we employed multiple prompts that encourage different reasoning behaviors. By combining diverse reasoning paths, the ensemble increases the probability of obtaining the correct answer while reducing variance between inference runs.
Since the competition imposes strict computational constraints, the inference pipeline was optimized for efficient GPU utilization and sequential evaluation through the official Kaggle evaluation API.

### Key Techniques

* Ensemble of multiple open-source LLMs<br>
* Multiple prompt templates for diverse reasoning<br> 
* Majority voting for answer aggregation<br> 
* Optimized sequential inference under resource constraints<br>

### 1. Environment Setup
