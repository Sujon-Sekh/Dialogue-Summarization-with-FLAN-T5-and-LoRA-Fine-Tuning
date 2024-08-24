# Dialogue-Summarization-with-FLAN-T5-and-LoRA-Fine-Tuning
This repository contains an advanced dialogue summarization system using FLAN-T5, optimized with LoRA (Low-Rank Adaptation) for enhanced performance. It features both extractive and abstractive summarization approaches, leveraging fine-tuning techniques to improve the quality of summaries generated from customer support conversations.


## Project Overview

### 1. Extractive Summarization (Notebook 1)
**Objective**: To summarize dialogues using an Extractive Summarization approach.  
**Model Used**: Word Frequency-based Extractive Summarization.

**Key Tasks**:
- **Implement Word Frequency**: Extract key sentences from dialogues based on word frequency to generate summaries.

### 2. Abstractive Summarization (Notebook 2)
**Objective**: To summarize dialogues using an Abstractive Summarization model.  
**Model Used**: FLAN-T5 (Fine-tuned using PEFT with LoRA).

**Key Tasks**:
- **Summarize Dialogue without Prompt Engineering**: Basic summarization using FLAN-T5.
- **Summarize Dialogue with an Instruction Prompt**:
  - **Zero Shot Inference**: Using an instruction prompt without prior training on the dataset.
  - **Prompt Template from FLAN-T5**: Applying a specific prompt template for inference.
- **Summarize Dialogue with One Shot and Few Shot Inference**:
  - Zero Shot Inference with an Instruction Prompt
  - Zero Shot Inference with the Prompt Template from FLAN-T5
- **Generative Configuration Parameters for Inference**: Fine-tuning the generative parameters for optimal performance.

### 3. Fine-Tuning and Evaluation (Notebook 3)
**Objective**: To fine-tune and evaluate the FLAN-T5 model on a domain-specific dataset.

**Key Tasks**:
- **Full Fine-Tuning**:
  - **Preprocess the Dialog-Summary Dataset**: Preparing the dataset for training.
  - **Fine-Tune the Model**: Training the model on the preprocessed dataset.
  - **Evaluate the Model Qualitatively**: Human evaluation of the generated summaries.
  - **Evaluate the Model Quantitatively (ROUGE Metric)**: Using the ROUGE metric to measure the quality of the summaries.
  
- **Parameter Efficient Fine-Tuning (PEFT)**:
  - **Setup the PEFT/LoRA Model**: Configuring the model for efficient fine-tuning.
  - **Train PEFT Adapter**: Training the adapter using PEFT.
  - **Evaluate the Model Qualitatively**: Human evaluation of the fine-tuned model.
  - **Evaluate the Model Quantitatively (ROUGE Metric)**: Comparing the fine-tuned model with the baseline and calculating the percentage improvement.
  
## Dataset

- **[SAMSum Dataset](https://huggingface.co/datasets/samsum)**:
  - The SAMSum dataset contains approximately 16,000 messenger-like conversations with corresponding summaries.
    

## Evaluation and Improvement Analysis

[ROUGE Metrics](https://en.wikipedia.org/wiki/ROUGE_(metric)) are used to evaluate the quality of summaries by comparing them to reference summaries. Below are the stats on ROUGE score being achieved with fine-tuning on FLAN-T5 model on samsum datasets:

| Model                      | ROUGE-1 | ROUGE-2 | ROUGE-L | ROUGE-Lsum |
|----------------------------|---------|---------|---------|------------|
| **Baseline FLAN-T5 Model** | 0.38  | 0.014  | 0.31  | 0.31     |
| **PEFT (LoRA Fine-Tuned)** | 0.44  | 0.17  | 0.34  | 0.34     |

The fine-tuning process using PEFT resulted in significant improvements across all ROUGE metrics:

| Metric    | Absolute Percentage Improvement |
|-----------|---------------------------------|
| ROUGE-1   | 5.38%                          |
| ROUGE-2   | 2.22%                           |
| ROUGE-L   | 3.41%                          |
| ROUGE-Lsum| 3.35%                          |

The improvements in ROUGE scores indicate that the PEFT (LoRA fine-tuned) model significantly enhances the quality of the generated summaries compared to the baseline FLAN-T5 model.


## Conclusion
This project successfully demonstrates the implementation of both Extractive and Abstractive Summarization techniques for customer support dialogues. Fine-tuning the Flan-T5 model with PEFT has shown significant improvements in generating high-quality summaries. The results highlight the potential of NLP models in automating and enhancing the efficiency of customer support operations.


## Acknowledgements

- **Hugging Face**: For providing the FLAN-T5 model and the Transformers library, which were essential for implementing and fine-tuning the summarization models.
- **The creators of the SAMSum** dataset: For their valuable contributions to dialogue summarization research, which enabled us to develop and evaluate our models effectively.

