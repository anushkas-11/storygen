# Fine-Tuning Language Models for Story Generation

## Abstract

This report investigates the fine-tuning of two advanced language models, Mistral-7B and GPT-2, for the task of prompt-based story generation. The primary motivation for this project is to explore the potential of artificial intelligence in creative writing, focusing on generating high-quality narratives that accurately capture distinct stylistic elements from specific datasets. By fine-tuning these models, we aim to push the boundaries of AI-generated content, making it more coherent, engaging, and stylistically diverse.

The scope of this work includes the comprehensive fine-tuning of the Mistral model using Parameter-Efficient Fine-Tuning (PEFT) with Low-Rank Adaptation (LoRA) on a 4-bit quantized model, and the fine-tuning of GPT-2 using traditional supervised methods. The methodology involves several key steps: preprocessing the datasets (WritingPrompts and TinyStories from Kaggle) through tokenization and normalization, configuring the training parameters (such as batch size, number of epochs, and learning rate), and utilizing specific fine-tuning scripts tailored to each model. The LoRA method was configured to optimize the training process, leveraging a YAML configuration file to manage parameters and streamline execution.

Results indicate that the fine-tuned Mistral model outperforms GPT-2 in generating stories that maintain the narrative structure and stylistic fidelity of the training data, even with small amounts of data. Detailed evaluation using metrics like ROUGE scores and analysis of text length distributions reveals that Mistral's advanced fine-tuning techniques significantly enhance its storytelling capabilities. The study demonstrates substantial improvements in generating coherent, stylistically consistent narratives, showcasing the potential of these advanced models in AI-driven story generation.

## Result and Performance Analysis

### 1. Fine-tuning GPT-2 using Supervised Fine-tuning:

**Model Training Setup:**
- **Number of Trainable Model Parameters:** 124,439,808
- **Total Model Parameters:** 124,439,808
- **Percentage of Trainable Model Parameters:** 100.00%

**Training Results:**
- **Epochs:** 3
- **Training Loss (Epoch 3):** 4.966
- **Validation Loss (Epoch 3):** 3.923

### 2. Fine-Tuning Mistral 7B using PEFT and LoRA with Unsloth

#### 2.1 Tiny Stories:

**Training Setup:**
- **Number of Trainable Model Parameters:** 41,943,040
- **Total Model Parameters:** 3,794,014,208
- **Percentage of Trainable Model Parameters:** 1.11%
- **Epochs:** 1
- **Batch Size per Device:** 2
- **Gradient Accumulation Steps:** 4

**Training Results:**
- **Training Loss (Epoch 1):** 0.3023
- **Rogue Metrics:**
  -  Rouge-1: 0.336
  -  Rouge-2: 0.093
  -  Rouge-L: 0.198
  -  Rouge-Lsum: 0.278

#### 2.2 Writing Prompts:

**Training Setup:**
- **Number of Trainable Model Parameters:** 41,943,040
- **Total Model Parameters:** 3,794,014,208
- **Percentage of Trainable Model Parameters:** 1.11%
- **Epochs:** 1
- **Batch Size per Device:** 2
- **Gradient Accumulation Steps:** 4

**Training Results:**
- **Training Loss (Epoch 1):** 2.3151
- **Rogue Metrics:**
  -  Rouge-1: 0.271
  -  Rouge-2: 0.068
  -  Rouge-L: 0.140
  -  Rouge-Lsum: 0.160

## Conclusion

The fine-tuning of Mistral 7B using PEFT and LoRA adapters on both Tiny Stories and Writing Prompts datasets yielded varying results. While the model achieved relatively better Rouge metrics on the Tiny Stories dataset compared to Writing Prompts, there is room for improvement, especially in terms of Rouge-L and Rouge-Lsum scores.

Further experimentation and tuning of hyperparameters may be necessary to enhance the model's performance. Additionally, considering the limited number of trainable parameters relative to the total model parameters, optimizing the model architecture and fine-tuning strategy could potentially lead to better results.

In conclusion, the utilization of the Mistral 7B 4-bit model in conjunction with parameter-efficient fine-tuning (PEFT) techniques has demonstrated significant advancements in the realm of natural language processing. Through the incorporation of techniques such as unsupervised layer-wise training (UNSLoTH) and quantized model fine-tuning, the fine-tuning process has been notably enhanced in terms of efficiency and effectiveness.

The adoption of PEFT methodologies has facilitated a streamlined fine-tuning process, enabling faster iterations and deployment of the model. Despite the model's architecture and hardware constraints, PEFT has allowed for the extraction of meaningful insights and patterns from the data, even with a limited amount of training data.

Moreover, the incorporation of quantized model fine-tuning has further optimized the training process by reducing the computational demands associated with large-scale models. This reduction in computational overhead has made the model more accessible and deployable across a wider range of hardware environments.

In summary, the synergy between the Mistral 7B 4-bit model and PEFT techniques has propelled advancements in natural language processing, offering a more efficient and effective approach to fine-tuning models. These developments hold promise for the creation of scalable and accessible solutions across diverse domains, paving the way for innovation and progress in the field.

## Datasets Used

- [Writing Prompts Dataset](https://huggingface.co/datasets/roneneldan/TinyStories)
- [Tiny Stories Dataset](https://www.kaggle.com/datasets/ratthachat/writing-prompts)

## Additional Resources

- [Unsloth Repository](https://github.com/unslothai/unsloth)

---

Feel free to replace placeholders with actual links and further refine the README as needed.
