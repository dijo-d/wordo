
# 🦙 WordO – The Word Generator

**WordO** is a fine-tuned version of Meta’s [LLaMA 3](https://huggingface.co/meta-llama), specifically trained to generate **precise English words** in response to given statements or definitions. It is designed to assist in tasks like vocabulary building, word retrieval, educational exercises, and language enrichment.

- 📦 **Model on Hugging Face**: [dijodaiju/llama-3-wordo-wordgen](https://huggingface.co/dijodaiju/llama-3-wordo-wordgen)  
- 🧾 **Notebook on GitHub**: [dijo-d/wordo](https://github.com/dijo-d/wordo)

---

## 🧠 Model Objective

WordO focuses on **accurately predicting real English words** based on:

- 🔹 Word definitions
- 🔹 Example usage
- 🔹 Descriptive prompts

Trained using a custom dataset that includes **words, meanings, and usage examples**, the model is optimized for understanding context and suggesting appropriate, real-world vocabulary.

---

## ✨ Key Features

- 🎯 **Precision-first word generation**
- 📘 Trained on a curated English vocabulary dataset
- 🧠 Based on `Meta-Llama-3-8B-Instruct`
- 📚 Ideal for educational use, vocabulary training, or linguistic projects

---

## 🚀 Quick Start (Inference)

You can load and use the model directly from Hugging Face:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model_id = "dijodaiju/llama-3-wordo-wordgen"

tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(model_id)

prompt = "A word meaning 'the fear of being forgotten'"
inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(**inputs, max_new_tokens=5)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

---

## 🗂️ Repository Contents

This GitHub repository contains:

- 📓 `wordgen_demo.ipynb` – A simple notebook demonstrating model usage
- 📁 Example prompts and outputs
- 📝 Notes on fine-tuning, data format, and limitations

> 🔧 The model is not yet deployed as an API or UI – currently accessible via notebook and Hugging Face.

---

## 📊 Training Dataset

The model was fine-tuned on a custom English vocabulary dataset with the following format:

```json
{
  "word": "ephemeral",
  "meaning": "lasting for a very short time",
  "example": "The beauty of the cherry blossoms is ephemeral."
}
```

This format was converted into structured prompts to guide the LLaMA 3 model toward accurate word prediction.

---

## 🧪 Example Prompt

```
Definition: "the practice of looking inward to examine one's own thoughts and feelings"
Example usage: "Through meditation, she developed a strong sense of ________."
→ introspection
```

---

## 📍 Future Plans

- [ ] FastAPI/Gradio interface for interactive use
- [ ] Hugging Face Space deployment
- [ ] Multilingual support and translation integration
- [ ] Flashcard generator for learners

---

## 📄 License

This project is open-sourced under the [MIT License](LICENSE).

---

## 👤 Author

**Dijo Daiju**  
🔗 [GitHub](https://github.com/dijo-d) | 🤗 [Hugging Face](https://huggingface.co/dijodaiju)
