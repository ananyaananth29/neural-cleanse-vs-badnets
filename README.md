
---

## 🚀 Results Summary

| Metric | Description | Result |
|--------|--------------|--------|
| **Clean Accuracy** | Accuracy on unpoisoned test set | 0.9901 |
| **Attack Success Rate (ASR)** | % of triggered images classified as target | 1.0000 |
| **Neural Cleanse Detection** | Detected anomalous class via MAD analysis | **Class 2 flagged (true target was 0)** |
| **Interpretation** | Neural Cleanse correctly identified the model as backdoored, though with slight target mismatch due to small trigger and fixed λ. |

---

## 🖼️ Visualization

**Example: BadNets attack**

| Clean Image | Triggered Image |
|--------------|----------------|
| ![clean](assets/clean_example.png) | ![triggered](assets/triggered_example.png) |

**Example: Neural Cleanse recovered mask & pattern**

| Recovered Mask | Recovered Pattern |
|----------------|-------------------|
| ![mask](assets/mask_example.png) | ![pattern](assets/pattern_example.png) |

---

## 🧠 Key Learnings

- Backdoor attacks like **BadNets** can stealthily compromise a model’s predictions with minimal visual changes.
- **Neural Cleanse** is effective in detecting anomalous backdoor patterns using statistical outlier analysis.
- Small triggers and fixed hyperparameters may lead to near-target anomalies rather than exact label detection.

---

## 📚 References

- **BadNets:** Gu et al., *BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain* (2017).  
- **Neural Cleanse:** Wang et al., *Neural Cleanse: Identifying and Mitigating Backdoor Attacks in Neural Networks* (IEEE S&P 2019).

---

## 🧑‍💻 Author
**[Your Name]**  
Graduate Student – Machine Learning Security  
University of [Your University Name]  
Course: CS 6958 / CS 4960 – Fall 2025  
