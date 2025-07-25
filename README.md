---
base_model: microsoft/phi-2
library_name: transformers
model_name: phi2-alpaca-lora-4bit
tags: 'generated_from_trainer'
datasets: yahma/alpaca-cleaned
---

# Model Card for phi2-alpaca-lora-4bit

- This model is a fine-tuned version of [microsoft/phi-2](https://huggingface.co/microsoft/phi-2).
- It has been trained using [TRL](https://github.com/huggingface/trl).

![image](https://github.com/user-attachments/assets/375447f6-face-49c1-a3ee-3d3dfd8643f4)

## Quick start

```python
from transformers import pipeline
question = "If you had a time machine, but could only go to the past or the future once and never return, which would you choose and why?"
generator = pipeline("text-generation", model="gauri-sharan/phi2-alpaca-lora-4bit", device="cuda")
output = generator([{"role": "user", "content": question}], max_new_tokens=128, return_full_text=False)[0]
print(output["generated_text"])
```

## Training procedure

 


This model was trained with SFT.

### Framework versions

- TRL: 0.19.0
- Transformers: 4.52.4
- Pytorch: 2.6.0+cu124
- Datasets: 3.6.0
- Tokenizers: 0.21.1

## Citations



Cite TRL as:
    
```bibtex
@misc{vonwerra2022trl,
	title        = {{TRL: Transformer Reinforcement Learning}},
	author       = {Leandro von Werra and Younes Belkada and Lewis Tunstall and Edward Beeching and Tristan Thrush and Nathan Lambert and Shengyi Huang and Kashif Rasul and Quentin Gallou{\'e}dec},
	year         = 2020,
	journal      = {GitHub repository},
	publisher    = {GitHub},
	howpublished = {\url{https://github.com/huggingface/trl}}
}
```
