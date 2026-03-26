# 🤖 Llama-Agentic-Finetune: 24-Hour Sprint

A high-efficiency fine-tuning pipeline for **Llama-3.2-3B**, optimized for instruction-following and Agentic AI reasoning. This project demonstrates the ability to take a base model and adapt it to specific task structures using a minimal hardware footprint (Google Colab T4 GPU).

---
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/KumarSarthak-Official/llama-agentic-finetune/blob/main/Fine_Tuning_Llama_3.2-3B.ipynb)

## 🚀 Model Access
[![Hugging Face Model](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Model-yellow)][Demo Model Here] 

> **[Download my fine-tuned weights on Hugging Face here]https://huggingface.co/spaces/kumarsarthak98/agentic-llama-demo**

---

## 🧠 Technical Decisions ("The Why")

### 1. Model Choice: Llama-3.2-3B
I selected the **3B parameter version** over the larger 8B or 70B models for several strategic reasons:
* **Cost Efficiency:** It fits within the 16GB VRAM limit of free-tier cloud GPUs (T4), making it accessible for edge deployment.
* **Latency:** The 3B model offers significantly faster inference speeds, which is critical for **Agentic AI** loops where a model may need to "think" multiple times to solve a task.
* **Performance:** Llama-3.2-3B punches above its weight class, matching the reasoning capabilities of older, much larger models.

### 2. Framework: Unsloth
I utilized the **Unsloth** library to accelerate the training process. 
* **Speed:** Training was 2x faster than standard Hugging Face `SFTTrainer` implementations.
* **Memory:** Used 70% less VRAM, allowing for longer context lengths without OOM (Out of Memory) errors.

### 3. Methodology: QLoRA (4-bit)
To achieve "Mastery in a Day," I used **Quantized Low-Rank Adaptation (QLoRA)**. This allowed me to only train ~1-3% of the model's parameters (the adapters), preserving the base model's intelligence while teaching it new formatting behaviors.

---

## 🛠️ Installation & Usage
1. Open the provided `.ipynb` notebook in Google Colab.
2. Ensure the Runtime is set to **T4 GPU**.
3. Run the "Setup" cells to install dependencies.

---

## 📊 Results
* **Training Loss:** Started at ~1.8, finished at **0.808** (60 steps).
* **Format:** Strictly follows the Alpaca instruction template.# llama-agentic-finetune
Fine-tuning Llama-3.2-3B for Agentic AI reasoning using Unsloth and QLoRA.
