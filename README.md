# Business Concepts Tutor — LoRA Fine-Tuning

A beginner-friendly machine learning project exploring how Low-Rank Adaptation (LoRA) can be used to fine-tune a small language model for explaining business concepts.

## Project Overview

This project fine-tunes **HuggingFaceTB/SmolLM2-135M-Instruct** to answer business-related questions using four sections:

- **Definition:** A simple explanation of the concept.
- **Example:** A practical business example.
- **Why it matters:** Why the concept is important.
- **Common mistake:** A frequent misunderstanding.

The goal is to make business explanations clearer and more consistent for beginners.

## Technologies Used

- Python
- Google Colab
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- PEFT (LoRA)
- Pandas
- Matplotlib

## Dataset

The custom training dataset contains **24 question-and-answer examples** covering business topics such as customer retention, market segmentation, value proposition, competitive advantage, profit margin, and cash flow.

## Fine-Tuning Configuration

| Parameter | Value |
|---|---|
| Base model | SmolLM2-135M-Instruct |
| Fine-tuning method | LoRA |
| Training examples | 24 |
| LoRA rank | 8 |
| LoRA alpha | 16 |
| Epochs | 5 |
| Learning rate | 0.0002 |
| Training steps | 30 |
| Training runtime | 10.77 seconds |

## Experimental Results

Training completed successfully, and logged training loss generally decreased from **3.3431 at step 5** to **2.8684 at step 30**.

However, the model did not consistently follow the requested four-section format.

| Evaluation Metric | Before Fine-Tuning | After Fine-Tuning |
|---|---|---|
| Questions tested | 4 | 4 |
| Correctly formatted responses | 0 | 0 |
| Format accuracy | 0% | 0% |

The experiment demonstrates that decreasing training loss does not automatically guarantee improvement in a specific task.

## Key Learnings

- How to prepare and tokenize a custom instruction dataset.
- How to fine-tune a small language model using LoRA.
- How to evaluate model responses before and after fine-tuning.
- Why training loss and task performance should be evaluated separately.
- How dataset size and training settings may affect model behavior.

## Future Improvements

- Expand the dataset with more varied business concepts.
- Test additional unseen questions.
- Experiment with training hyperparameters.
- Improve format-following evaluation.

## Project Files

- `Business_Concepts_Tutor_LoRA (1).ipynb` — Colab notebook containing the experiment.
- `training_data.json` — Custom training dataset.

## Conclusion

This project was a practical introduction to parameter-efficient fine-tuning. Although the desired response format was not achieved, the experiment provided useful insights into model training, evaluation, and the limitations of small datasets.
