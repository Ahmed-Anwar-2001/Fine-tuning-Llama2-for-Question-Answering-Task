# Fine-tuning-Llama2-for-Question-Answering-Task



## Model

For the purpose of context driven Question Answering, I chose the model- _**'meta-llama/Llama-2-7b-chat-hf'**_ of Llama2 as it gives better results for the purpose.

Huggingface Hub- [link](https://huggingface.co/meta-llama/Llama-2-7b-chat-hf)


## Dataset

The dataset used for fine-tuning the model is **'SQuAD2.0'**. 

### About the Dataset
Combining the 100,000 questions in SQuAD1.1 with over 50,000 unanswerable questions written adversarially by crowdworkers to look similar to answerable ones. To do well on SQuAD2.0, systems must not only answer questions when possible, but also determine when no answer is supported by the paragraph and abstain from answering.

Kaggle- [link](https://www.kaggle.com/datasets/thedevastator/squad2-0-a-challenge-for-question-answering-syst)
Huggingface Hub- [link](https://huggingface.co/datasets/rajpurkar/squad_v2)


# Methodology

1. Install necessary libraries

2. Import necessary libraries

3. Loading the dataset

4. Preprocessing
  - Perform preprocessing wherever necessary. Such as the 'answers' required preprocessing as there were gibberish data that needed to be removed.
  - Identifying the necessary columns of data\(information) and removing the unnecessary ones like- 'id' 
  - Creating Relevant Prompts for training.

 5. Declaring the necessary parameters of:
    - QLoRA parameters
    - bitsandbytes parameters
    - TrainingArguments parameters
    - SFT parameters

 6. Configuring bitsandbytes for 4-bit quantization.

 7. Loading the Llama 2 model in 4-bit precision on a GPU with the corresponding tokenizer.

 8. Finally, Loading configurations for QLoRA, regular training parameters, and passing everything to the SFTTrainer. The training can finally start!
