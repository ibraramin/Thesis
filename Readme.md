# Thesis (A Hybrid Pruning and Distillation Framework for Reducing Hallucinations in Small Language Models)

Clone this repo using

> git clone https://github.com/ibraramin/Thesis 

## Requirements

Install all the necessary language features and packages

>Python > = 3.13

Install the necessary packages from requirements.txt

> pip install -r requirements.txt

Then from either run this from the terminal

```lm_eval --model hf \
    --model_args pretrained=TinyLlama/TinyLlama-1.1B-Chat-v1.0 \
    --tasks mmlu,truthfulqa_mc2,wikitext \
    --device cuda:0 \
    --batch_size auto \
    --output_path ./results.json
```

Or make a new .py or .ipynb file and use this

```import json
import pandas as pd
from lm_eval import simple_evaluate

model = "TinyLlama/TinyLlama-1.1B-Chat-v1.0"
tasks = ["mmlu", "truthfulqa_mc2", "wikitext"]

results = simple_evaluate(
    model="hf",
    model_args=f"pretrained={model}",
    tasks=tasks,
    device="cuda:0",
    batch_size="auto"
)
with open("results.json", "w") as f:
    json.dump(results, f, indent=2)
print(f"Results saved to {"results.json"}")
```


