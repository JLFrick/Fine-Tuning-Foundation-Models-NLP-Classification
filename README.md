# Fine-Tuning Foundation Models for NLP Tasks

This repository explores various techniques for fine-tuning large language models (LLMs) on NLP tasks like sentiment classification. The primary goal is to experiment with **parameter-efficient fine-tuning (PEFT)** methods such as **LoRA (Low-Rank Adaptation)** and compare their performance against baseline models and other fine-tuning techniques.

Fine-tuning large language models traditionally requires significant computational resources and time. PEFT techniques like LoRA enable efficient adaptation by only updating a subset of parameters while keeping the majority of the model frozen. This makes fine-tuning accessible even on limited hardware.

---

## **What This Repository Covers**
### **Current Status**
1. **Baseline Model:**
   - A pre-trained GPT-2 model was evaluated on the IMDb dataset for sentiment classification without any fine-tuning.
2. **LoRA Fine-Tuning:**
   - The GPT-2 model was fine-tuned using LoRA to adapt it to the IMDb dataset, improving its task-specific performance significantly.
3. **Results Comparison:**
   - The performance of the baseline and LoRA fine-tuned models was measured and saved for easy reference.

### **Future Goals**
- Add more fine-tuning methods such as:
  - Full fine-tuning
  - Prompt tuning
  - Adapters
  - Prefix tuning
- Expand the repository to include other NLP tasks like text summarization, named entity recognition, and machine translation.
- Compare the performance of various fine-tuning techniques on different datasets.

---

## **Project Structure**

```
FINE-TUNING-FOUNDATION-MODELS/
│
├── notebooks/
│   ├── baseline-results/               # Notebooks for evaluating baseline models
│   ├── results/                        # Notebooks for analyzing results of fine-tuned models
│   └── finetuning_lora.ipynb           # Main notebook for LoRA fine-tuning
│
├── results/
│   ├── baseline_results.json           # Baseline model evaluation results
│   ├── fine_tuned_lora_results.json    # Fine-tuned LoRA model evaluation results
│
├── saved_models/
│   └── lora_finetuned/                 # Directory for saving the fine-tuned LoRA model
│       ├── adapter_config.json         # Configuration file for LoRA adapter
│       └── adapter_model.safetensors   # Saved LoRA model weights
│
├── .gitignore                          # Files and directories to be ignored by Git
├── .gitattributes                      # Git settings for text file handling
└── README.md                           # Project documentation
```

---

## **Models and Comparisons**

| **Model**         | **Task**                | **Dataset** | **Metric**       | **Performance**     |
|--------------------|-------------------------|-------------|------------------|---------------------|
| GPT-2 Baseline     | Sentiment Classification | IMDb        | Accuracy         | `49.88%`            |
| GPT-2 + LoRA       | Sentiment Classification | IMDb        | Accuracy         | `75.50%`            |
| _Upcoming Models_  | _To be added..._        | _TBD_       | _TBD_            | _TBD_               |

**Observations:**
- 	The baseline GPT-2 model performs significantly below expectations for sentiment classification, with accuracy close to random guessing (50%), highlighting its lack of task-specific adaptation.
- The LoRA fine-tuned GPT-2 model achieves an accuracy of 75.50%, demonstrating the effectiveness of parameter-efficient fine-tuning in improving task-specific performance without retraining the entire model.
- This substantial improvement shows that LoRA is a powerful method for adapting pre-trained models to new tasks efficiently, even with limited computational resources.
---

