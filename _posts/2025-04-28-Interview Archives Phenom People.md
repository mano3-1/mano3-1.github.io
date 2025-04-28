---
title: Interview Experience for Product Developer Engineer I | Phenom People
tags: [Interview archives]
style: fill
color: secondary
comments: true
description: This explains my interview experience for Product Developer Engineer I role at Phenom People in detail.
---

## General Questions

### Round 1

1. Introduce yourself
2. Why do you want to switch?
3. What are different RAG systems?
4. How does LightGBM work?
5. Boosting vs Bagging
6. Why do we need activation functions in neural networks? Different types of activation functions? Why is ReLU more effective than sigmoid for intermediate layers?
7. How to mitigate overfitting?
8. Does batch size affect accuracy?
9. What is the vanishing gradients problem and how do we handle it?
10. How does attention work in transformers?
11. Drawbacks of transformers
12. Positional encoding in transformers
13. If a model is developed and tested, but fails in production, what could be the possible reasons?
14. If two models perform similarly, how do you decide which one to deploy (beyond inference time)?

#### Coding Questions:

- **First non-repeating character in a stream**

    ```python
    def solution(x):
        non_repeating_chars = [x[0]]
        solution = "a"
        for _ in x[1:]:
            if _ not in non_repeating_chars:
                non_repeating_chars.append(_)
                solution += non_repeating_chars[0]
                continue
            else:
                non_repeating_chars = [character for character in non_repeating_chars if character != _]
            if len(non_repeating_chars) == 0:
                solution += "#"
                continue
            solution += non_repeating_chars[0]
        return solution
    ```

- **Minimum number of coins to make a sum**

    ```python
    def solution(n, sum_):
        if sum_ == 0:
            return 0
        if sum_ < 0:
            return None
        sols = [solution(n, sum_ - _) for _ in n]
        sols = [_ for _ in sols if _ is not None]
        return min(sols) + 1

    solution([5, 1], 0)
    ```

### Round 2

1. Introduce yourself
2. Why do you want to switch?
3. Your best work in the past 1.5 years
4. How does LoRA work, particularly for large models like Jais-75B?
5. Azure Machine Learning
6. What is attention?
7. Architectural difference between T5 and GPT/Llama models
8. Evolution from RNNs to LSTMs to Transformers
    - How does LSTM solve the vanishing gradient problem?
    - How does decoding happen in transformers?
    - What is GRU, and which is better: GRU or LSTM?
9. Difference between BERT and GPT
10. How is BERT trained?
11. How is GPT trained?
12. Designing a neural network for a classification problem with text, categorical, and numerical features
13. Handling imbalanced datasets
14. Metrics for performance evaluation on imbalanced datasets
15. Interpretation of train/validation/test accuracies (80/70/60)
16. How to fix overfitting?
17. What is an agent?

### Round 3

1. Introduce yourself
2. Benefits of ChromaDB and comparison with its peers
3. How to censor data retrieval based on user access
4. Where do you see yourself in the next 5 years?
5. One mistake you have made in a project and how you fixed it
6. Why do you want to switch?
7. How does RAG work?


## Project-Specific Questions (Gov AI POC, Confluence Chatbot, etc.)

- Explain your current project (Gov AI - RAG Bot)
- Specifics about RAG:
  - What chunking strategies did you use?
  - What chunking strategies do you know?
  - How can you improve chunking?
  - Which framework did you use? (LangChain) and what class for chunking?
- Deployment Specifics:
  - Chainlit framework
  - Azure App Service
- What other components would you use if Azure infra isn't available?
- Confluence chatbot:
  - How to restrict document retrieval based on user access

