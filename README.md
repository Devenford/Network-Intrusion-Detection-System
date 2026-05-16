# Network-Intrusion-Detection-System
Network intrusion detection system using Logistic Regression, LSTM, and Transformer models on NSL-KDD dataset

A comparative study of machine learning approaches for network intrusion detection, culminating in the implementation of the FlowTransformer framework — a modular, attention-based architecture for classifying network traffic as normal or malicious.

# Results

## Summary

| Model | Accuracy | Macro F1 | Weighted F1 |
|---|---|---|---|
| Logistic Regression | 0.75 | 0.75 | 0.75 |
| LSTM | 0.49 | 0.49 | 0.48 |
| FlowTransformer1 (Threshold 0.50) | 0.79 | 0.79 | 0.79 |
| **FlowTransformer2 (Threshold 0.40)** | **0.81** | **0.81** | **0.81** |
| FlowTransformer3 (Threshold 0.35) | 0.81 | 0.81 | 0.81 |

## Per-Class Breakdown

**Logistic Regression**
| Class | Precision | Recall | F1 |
|---|---|---|---|
| Normal (0) | 0.65 | 0.93 | 0.77 |
| Attack (1) | 0.93 | 0.62 | 0.74 |

**LSTM**
| Class | Precision | Recall | F1 |
|---|---|---|---|
| Normal (0) | 0.43 | 0.61 | 0.51 |
| Attack (1) | 0.57 | 0.39 | 0.46 |

**FlowTransformer1 (Threshold 0.50)**
| Class | Precision | Recall | F1 |
|---|---|---|---|
| Normal (0) | 0.69 | 0.92 | 0.79 |
| Attack (1) | 0.92 | 0.69 | 0.79 |

**FlowTransformer2 (Threshold 0.40) — Best Model**
| Class | Precision | Recall | F1 |
|---|---|---|---|
| Normal (0) | 0.71 | 0.97 | 0.82 |
| Attack (1) | 0.97 | 0.70 | 0.81 |

**FlowTransformer3 (Threshold 0.35)**
| Class | Precision | Recall | F1 |
|---|---|---|---|
| Normal (0) | 0.71 | 0.96 | 0.81 |
| Attack (1) | 0.96 | 0.70 | 0.81 |

## Key Takeaways

- **FlowTransformer2** is the best model — highest accuracy (0.81) with attack precision of **0.97**, meaning it raises very few false alarms when flagging malicious traffic.
- **Logistic Regression** (0.75) comfortably outperformed **LSTM** (0.49), showing that artificial sequence construction on NSL-KDD introduces noise rather than useful temporal signal.
- FlowTransformer2 and FlowTransformer3 are nearly identical overall, but FT2's marginally higher attack precision makes it the safer choice for deployment.
