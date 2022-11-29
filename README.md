# Fine-tune-Layoutlmv3-on-SROIE

### Task
This repo will record my toy code for LayoutLMv3 fine-tuning. The goal of this project is to extract entities from a given document image (key-value extraction). Key-value extraction will be done using the SROIE dataset which comprises of scanned receipts in English language.

### SROIE 2019 dataset: 
Introduced by Huang et al. in ICDAR2019 Competition on Scanned Receipt OCR and Information Extraction. Consists of a dataset with 1000 whole scanned receipt images and annotations (training set: 652, testing set: 347) for the competition on scanned receipts OCR and key information extraction (SROIE). 

In this code, I trained the model with a dataset from Hugging Face: [arvindrajan92/sroie_document_understanding](https://huggingface.co/datasets/arvindrajan92/sroie_document_understanding), which is an enriched version of SROIE 2019 dataset with additional labels and precise bounding box coordinates for OCR and layout understanding. Split this dataset into training part and evaluation part with a ratio 9:1. 

### Model: LayoutLMv3

The LayoutLMv3 model was proposed in [LayoutLMv3: Pre-training for Document AI with Unified Text and Image Masking](https://arxiv.org/abs/2204.08387) by Yupan Huang, Tengchao Lv, Lei Cui, Yutong Lu, Furu Wei. LayoutLMv3 is one of the strongest models in multimodal document understanding.

### Training detail:

Use Hugging Face Trainer to finetune this model.

### Result:

1. Token classification result on test set: (saved as output.csv)

2. Inference Visualization:

![image](https://github.com/fjljlzy/Fine-tune-Layoutlmv3-on-SROIE/blob/master/sroie_inference_data/X00016469670.jpg)

Compare to ground truth:
{
    "company": "OJC MARKETING SDN BHD",
    "date": "15/01/2019",
    "address": "NO 2 & 4, JALAN BAYU 4, BANDAR SERI ALAM, B1750 MASAI, JOHOR",
    "total": "193.00"
}


