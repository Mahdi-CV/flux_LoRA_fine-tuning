# flux_LoRA_fine-tuning# 🐾 Fine-Tuning FLUX.1 to Learn Mochicat

This project showcases how I fine-tuned the `FLUX.1-dev` image generation model using the [ai-toolkit](https://github.com/ostris/ai-toolkit) to teach it a new character: **Mochicat**, a cute cartoon cat that the original model was unfamiliar with.

### 🎯 Goal

To inject a visually consistent and stylized character into the model, enabling prompts like "Mochicat baking cookies" or "Mochicat as an astronaut" to produce faithful and creative outputs.

---

## 📁 Dataset

I curated a dataset of **20 Mochicat images** and wrote detailed captions using a language model. Each caption described the pose, emotion, and unique visual traits of Mochicat.
![](assets/training.png) 

Examples of a caption describing the first image is provided below.
> *"A plump, adorable white cartoon Mochicat with soft pink ears and rosy cheeks happily hugging and nibbling on a golden-brown, round cookie decorated with a smiling face. Mochicat's eyes sparkle joyfully, showing satisfaction and delight."*

All images were paired with `.txt` files named identically to the image files, following ai-toolkit's training requirements.

---

## 🧪 Training Setup

- **Base Model:** [`black-forest-labs/FLUX.1-dev`](https://huggingface.co/black-forest-labs/FLUX.1-dev)
- **Trigger Word:** `[trigger]` (set to `mochicat_style` in config)
- **Steps:** 1500
- **Resolution Buckets:** 512, 768, 1024
- **Device:** AMD MI300X

Training was done using [ai-toolkit](https://github.com/ostris/ai-toolkit), leveraging LoRA and multi-resolution support for efficient fine-tuning.

---

## 🖼️ Before & After Examples

Each example uses the same prompt evaluated at different training steps.

### Prompt
**"Mochicat happily baking cookies in a cozy kitchen, flour flying everywhere"**

<div style="display: flex; gap: 10px;"> <div> <img src="assets/1744400750300__000000000_0.jpg" width="256"/> <p align="center">Step 0<br><sub>Before training</sub></p> </div> <div> <img src="assets/1744401192020__000000250_0.jpg" width="256"/> <p align="center">Step 250<br><sub>Early character learning</sub></p> </div> <div> <img src="assets/1744403393259__000001500_0.jpg" width="256"/> <p align="center">Step 1500<br><sub>Identity established</sub></p> </div> </div>


### Prompt
**"Mochicat dressed as a detective, investigating mysterious paw prints at night"**

<div style="display: flex; gap: 10px;"> <div> <img src="assets/1744400788779__000000000_4.jpg" width="256"/> <p align="center">Step 0<br><sub>Before training</sub></p> </div> <div> <img src="assets/1744401230744__000000250_4.jpg" width="256"/> <p align="center">Step 250<br><sub>Early character learning</sub></p> </div> <div> <img src="assets/1744403431994__000001500_4.jpg" width="256"/> <p align="center">Step 1500<br><sub>Identity established</sub></p> </div> </div>


### Prompt
**"Mochicat as an astronaut, floating peacefully outside a colorful spaceship"**

<div style="display: flex; gap: 10px;"> <div> <img src="assets/1744400769417__000000000_2.jpg" width="256"/> <p align="center">Step 0<br><sub>Before training</sub></p> </div> <div> <img src="assets/1744401211355__000000250_2.jpg" width="256"/> <p align="center">Step 250<br><sub>Early character learning</sub></p> </div> <div> <img src="assets/1744403412586__000001500_2.jpg" width="256"/> <p align="center">Step 1500<br><sub>Identity established</sub></p> </div> </div>

### Prompt
**"Mochicat excitedly riding a skateboard through a lively park"**

<div style="display: flex; gap: 10px;"> <div> <img src="assets/1744400837263__000000000_9.jpg" width="256"/> <p align="center">Step 0<br><sub>Before training</sub></p> </div> <div> <img src="assets/1744401279333__000000250_9.jpg" width="256"/> <p align="center">Step 250<br><sub>Early character learning</sub></p> </div> <div> <img src="assets/1744403480719__000001500_9.jpg" width="256"/> <p align="center">Step 1500<br><sub>Identity established</sub></p> </div> </div>
---

## 🛠️ Tools Used

- [ai-toolkit](https://github.com/ostris/ai-toolkit)
- AMD MI300X 

---

## 📍 Try It Yourself

Installation steps on MI300X coming soo. 

