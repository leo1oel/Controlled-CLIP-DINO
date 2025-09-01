# Controlled-CLIP-DINO

This repository contains the models and resources for our paper, "Data or Language Supervision: What Makes CLIP Better than DINO?"

CLIP outperforms self-supervised models like DINO as vision encoders for vision-language models (VLMs), but it remains unclear whether this advantage stems from CLIP’s language supervision or its much larger training data. To disentangle these factors, we pre-train CLIP and DINO under controlled settings—using the same architecture, dataset, and training configuration—achieving similar ImageNet accuracy. Embedding analysis shows that CLIP captures high-level semantics (e.g., object categories, text), while DINO is more responsive to low-level features like colors and styles. When integrated into VLMs and evaluated on 20 VQA benchmarks, CLIP excels at text-intensive tasks and is comparable to DINO on others. Variants of language supervision (e.g., sigmoid loss, pre-trained language encoders) yield limited gains. Our findings provide scientific insights into vision encoder design and its impact on VLM performance.
## Models

These encoders were trained from scratch on a 10M subset of the DataComp dataset.

| Model | Architecture | Hugging Face Link |
| :--- | :--- | :--- |
| DINO DataComp 12M | `ViT-B/16` | [Leonardo6/dino-datacomp-12m-16](https://huggingface.co/Leonardo6/dino-datacomp-12m-16) |
| CLIP RoBERTa-10 DataComp 12M | `ViT-B/16` | [Leonardo6/clip-roberta10-datacomp-12m-16](https://huggingface.co/Leonardo6/clip-roberta10-datacomp-12m-16) |
| CLIP RoBERTa-4 DataComp 12M | `ViT-B/16` | [Leonardo6/clip-roberta4-datacomp-12m-16](https://huggingface.co/Leonardo6/clip-roberta4-datacomp-12m-16) |
| SigLIP DataComp 12M | `ViT-B/16` | [Leonardo6/siglip-datacomp-12m-16](https://huggingface.co/Leonardo6/siglip-datacomp-12m-16) |
| CLIP DataComp 12M (16) | `ViT-B/16` | [Leonardo6/clip-datacomp-12m-16](https://huggingface.co/Leonardo6/clip-datacomp-12m-16) |
| CLIP DataComp 12M (32) | `ViT-B/32` | [Leonardo6/clip-datacomp-12m-32](https://huggingface.co/Leonardo6/clip-datacomp-12m-32) |
| CLIP Vicuna | `ViT-B/16` | [Leonardo6/clip-vicuna](https://huggingface.co/Leonardo6/clip-vicuna) |

To replicate our experiments, please refer to the following official repositories and datasets.

  * **Vision Encoder Training:**
      * CLIP: [mlfoundations/open\_clip](https://github.com/mlfoundations/open_clip)
      * DINO: [facebookresearch/dino](https://github.com/facebookresearch/dino)
  * **Linear Probing Evaluation:**
      * [leo1oel/ViT-linear-probing](https://www.google.com/search?q=https://github.com/leo1oel/ViT-linear-probing)
  * **VLM Training & Evaluation:**
      * Framework: [haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA)
      * Benchmark: [suyc21/VMCBench](https://huggingface.co/datasets/suyc21/VMCBench)
