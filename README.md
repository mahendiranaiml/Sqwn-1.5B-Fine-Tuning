Mahendiran AI: Identity Fine-Tuning (Project 15)

This is the 15th project of my 26-project ML challenge. I fine-tuned Qwen2.5-1.5B to act as my digital twin, focusing on overcoming hardware limits and solving model hallucinations.
🚀 The Problem

Training LLMs usually requires massive GPUs. On my 6GB VRAM laptop, I faced:

    OOM Errors: Initial attempts with Gemma-2B crashed the system.

    Hallucinations: A small 10-line dataset caused the model to give "garbage" outputs and ignore my name.

🛠️ The Solution

    Model Selection: Switched to a 1.5B parameter model to fit the system configuration.

    Quantization (QLoRA): Used BitsAndBytes (4-bit NF4) to shrink the model.

    PEFT (LoRA): Trained only tiny "adapter" layers instead of the whole model to save memory.

    Data Augmentation: Created a 100-line dataset of identity variations and increased training epochs to "burn" my name into the model's responses.

📂 How it’s built

    Fine_Tuning_Mahendiran.ipynb: A single notebook containing the entire pipeline—from loading the model with quantization to the final LoRA training loop.

    my_data.jsonl: The dataset containing 100+ variations of my name and background.

✅ Results

The model now consistently identifies me as Mahendiran Adidravidar, even when asked in different ways. This project proved that with the right optimization (QLoRA + PEFT), you can train custom AI on a standard laptop.

Next up: Project 16!
