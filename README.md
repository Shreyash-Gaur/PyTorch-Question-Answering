
---

# Pytorch Question Answering (QA) using SQuAD Dataset

This project demonstrates a workflow for exploring and filtering the Stanford Question Answering Dataset (SQuAD) using PyTorch and the Hugging Face `datasets` library. The notebook provides a framework for working with question answering tasks, focusing on data exploration, filtering, and example analysis.

## Project Overview

The main goal of this project is to load, explore, and manipulate the SQuAD dataset, which consists of context-question-answer triples. This project allows users to:
- Load and examine the structure of the dataset.
- Explore examples from both the training and validation sets.
- Perform basic filtering and transformations on the dataset.

## Key Features

1. **Dataset Loading**:
   The SQuAD dataset is loaded using the Hugging Face `datasets` library, which includes the following features:
   - **Context**: A paragraph from which the question is derived.
   - **Question**: The question associated with the context.
   - **Answer**: The correct answer extracted from the context.

2. **Data Exploration**:
   - View sample questions, contexts, and answers from both the training and validation sets.
   - Examples include historical and geographical contexts with corresponding questions and answers.

3. **Filtering Data**:
   - A filtering step is applied to remove examples where the list of answers is either empty or contains more than one answer. This is helpful for tasks that require a single correct answer.

4. **Answer Analysis**:
   - The notebook showcases specific answers from the dataset, such as entities like `Denver Broncos` and `Levi's Stadium`.
   - Contextual relationships between answers and their positions within the text are displayed.

## Example Data Exploration

### Dataset Features:
- **id**: Unique identifier for each example.
- **title**: Title of the source from which the context is drawn.
- **context**: The paragraph of text in which the answer to the question is found.
- **question**: The question that is being asked based on the context.
- **answers**: The correct answer(s) to the question, including the starting position within the context.

### Example:
**Context**:  
*Architecturally, the school has a Catholic character. Atop the Main Building's gold dome is a golden statue of the Virgin Mary...*

**Question**:  
*To whom did the Virgin Mary allegedly appear in 1858 in Lourdes, France?*

**Answer**:  
*Saint Bernadette Soubirous*``

## Dataset Filtering

One of the key operations in the notebook is the filtering of the dataset based on the number of answers. For example, filtering is performed to ensure that every entry has exactly one answer. The following code snippet demonstrates this filtering:

```python
filtered_dataset = raw_datasets["train"].filter(lambda x: len(x["answers"]["text"]) == 1)
```

## Insights

- The SQuAD dataset is rich with diverse contexts and questions, making it ideal for building machine learning models in the domain of question answering.
- By filtering for specific answer conditions, we can tailor the dataset to meet various training needs, such as single-answer models.
- Exploring the dataset reveals its versatility, with contexts spanning topics from sports to historical events.

## Future Work

This project lays the groundwork for more advanced tasks, such as:
- Fine-tuning a pre-trained model (like BERT or DistilBERT) for question-answering tasks using PyTorch.
- Implementing additional data augmentation techniques to enrich the dataset.
- Training and evaluating QA models on the filtered datasets.

## Conclusion

The notebook offers a streamlined approach to exploring the SQuAD dataset and setting up a basic pipeline for question-answering tasks. With further development, this can serve as a starting point for building sophisticated models that can understand and answer questions based on provided contexts.

---
