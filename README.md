# Fine-tune-Layoutlmv3-on-SROIE

### Task
A toy code for LayoutLMv3 fine-tuning. The goal of this project is to extract entities from a given document image (key-value extraction). Key-value extraction will be done using the SROIE dataset which comprises of scanned receipts in English language.

### SROIE 2019 dataset: 
Introduced by Huang et al. in ICDAR2019 Competition on Scanned Receipt OCR and Information Extraction. Consists of a dataset with some scanned receipt images and annotations for the competition on scanned receipts OCR and key information extraction (SROIE). 

Train the model with a dataset from Hugging Face: [arvindrajan92/sroie_document_understanding](https://huggingface.co/datasets/arvindrajan92/sroie_document_understanding), which is an enriched version of SROIE 2019 dataset with additional labels and precise bounding box coordinates for OCR and layout understanding.

### Model: LayoutLMv3

The LayoutLMv3 model was proposed in [LayoutLMv3: Pre-training for Document AI with Unified Text and Image Masking](https://arxiv.org/abs/2204.08387) by Yupan Huang, Tengchao Lv, Lei Cui, Yutong Lu, Furu Wei. LayoutLMv3 is one of the strongest models in multimodal document understanding.

### Training detail:

Use Hugging Face Trainer to finetune this model.

Dataset:
- training set: 527 examples
- validation set: 59 examples
- test set: 347 examples

Output: (saved to local)
- Token classification result on test set (for online competition submission!)
- Image with inferenced labels (for debug and bad case analysis!)

### Result:

1. Token classification result on test set: (saved as "output.csv")

2. Inference example:

Prediction:
![image](https://github.com/fjljlzy/Fine-tune-Layoutlmv3-on-SROIE/blob/master/sroie_inference_data/X00016469670.jpg)

***python
Ground truth:
{
    "company": "OJC MARKETING SDN BHD",
    "date": "15/01/2019",
    "address": "NO 2 & 4, JALAN BAYU 4, BANDAR SERI ALAM, B1750 MASAI, JOHOR",
    "total": "193.00"
}
***

