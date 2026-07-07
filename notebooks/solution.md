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

* Import required libraries.<br>
* Configure GPU settings and runtime environment.<br>
* Load the competition evaluation API.

### 2. Model Loading

* Load multiple open-source LLMs.<br>
* Initialize tokenizer and inference configuration.<br>
* Optimize memory usage for efficient GPU inference.

### 3. Prompt Engineering

* Design prompts to encourage step-by-step mathematical reasoning.<br>
* Apply multiple prompt templates to increase reasoning diversity.<br>
* Format outputs to return only the final integer answer.

### 4. Candidate Generation

* Generate multiple candidate solutions for each mathematical problem.<br>
* Control decoding parameters to balance diversity and stability.

### 5. Answer Aggregation

* Extract integer answers from generated responses.<br>
* Aggregate predictions using Majority Voting.<br>
* Select the most frequent integer as the final prediction.

### 6. Evaluation API

* Receive test problems sequentially through the official Kaggle evaluation API.<br>
* Perform inference for each problem individually.<br>
* Return predictions to the evaluation server.

### 7. Resource Optimization

* Reduce GPU memory consumption.<br>
* Optimize inference speed under competition constraints.<br>
* Process test samples efficiently within the runtime limit.

### 8. Submission

* Generate the final submission through the official evaluation API.<br>
* Verify that all predictions are successfully returned.
