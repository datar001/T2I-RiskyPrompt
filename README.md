# T2I-RiskyPrompt

[AAAI 2026] T2I-RiskyPrompt: A Benchmark for Safety Evaluation, Attack, and Defense on Text-to-Image Model  

If you are interested in our work, please star ⭐ this repository.

#### |Risky Prompt Dataset (coming soon) |Risky Image Dataset (coming soon) |  Paper [[arXiv]](https://arxiv.org/abs/2510.22300) |

---

## News

- [2025/11/9] The T2I-RiskyPrompt paper is accepted on AAAI 2026: [arXiv:2510.22300](https://arxiv.org/abs/2510.22300).

---

## Introduction

Text-to-image (T2I) models can generate rich visual content from natural language prompts, but they also face safety risks. When a user inputs risky text prompts, such as sexual or violent content, the model may output unsafe images or leak sensitive information. Evaluating and defending against these risks is an important topic for safe deployment of T2I systems. However, existing risky prompt datasets are still limited in safety categories, annotation quality, and evaluation effectiveness.  

T2I-RiskyPrompt is a benchmark designed for systematic safety evaluation, attack, and defense of T2I models. It focuses on risky text prompts instead of images, and provides a structured risk taxonomy, high quality annotations, and a set of evaluation protocols for both defense and attack.  

We first design a hierarchical risk taxonomy with 6 primary categories and 14 fine-grained subcategories. Based on this taxonomy, we build a data collection and annotation pipeline and finally obtain 6,432 effective risky prompts. Each prompt is annotated with its hierarchical category labels and detailed risk reasons, which can be used to measure not only whether a prompt is risky, but also why it is risky.  

On top of T2I-RiskyPrompt, we also introduce a reason-driven risky image detection method that aligns a multimodal large language model (MLLM) with safety annotations. We then use this benchmark to evaluate eight T2I models, nine defense methods, five safety filters, and five attack strategies, and summarize a series of insights on the strengths and weaknesses of current T2I safety mechanisms.  

T2I-RiskyPrompt aims to provide a common testbed for researchers who work on safety evaluation, adversarial attack, and defense of text-to-image models.

---

## Features

T2I-RiskyPrompt provides the following main features.

1. **Hierarchical risky prompt taxonomy**  
   We define a three-level risk structure that covers 6 primary categories and 14 fine-grained subcategories. This structure gives a clear view of different types of risky prompts and their relations.
2. **High quality risky prompt dataset**  
   Based on the taxonomy, we collect and clean 6,432 risky prompts. Every prompt is manually checked to be valid, and each one is annotated with its hierarchical category labels and human written risk reasons, which enable fine grained analysis.
3. **Reason-driven risky image detection**  
   We propose a reason-driven detection method that explicitly aligns an MLLM with safety annotations. The model is encouraged to give not only a safe / unsafe decision, but also a consistent explanation that matches the annotated risk reasons.
4. **Comprehensive safety evaluation**  
   We evaluate eight T2I models, nine defense methods, five safety filters, and five attack strategies on T2I-RiskyPrompt. The benchmark supports experiments for evaluation, attack, and defense in a unified way.

---

## Dataset

The final dataset contains 6,432 risky prompts, each with hierarchical labels and a human written risk reason. All prompts are provided in the file `T2I-RiskyPrompt.json` in this repository.

A typical data record is structured as follows (pseudo example):

```json
{
  "prompt": "A detailed description of a violent scene ...",
  "label": 
    {
        "primary_category——subcategory": ["reason_1", "reason_2"],
    }
}
```



## Citation

If you find T2I-RiskyPrompt useful in your research, please cite our work:

```
@article{zhang2025t2iriskyprompt,
  title   = {T2I-RiskyPrompt: A Benchmark for Safety Evaluation, Attack, and Defense on Text-to-Image Model},
  author  = {Zhang, Chenyu and Zhang, Tairen and Wang, Lanjun and Chen, Ruidong and Li, Wenhui and Liu, Anan},
  journal = {arXiv preprint arXiv:2510.22300},
  year    = {2025}
}
```


