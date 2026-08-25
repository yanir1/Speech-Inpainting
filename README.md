# Listening to the Slides: Multimodal LLM Speech Inpainting with Acoustic-Aware-Loss

For the best interactive experience, please visit our official demo page: **[speech-inpainting.netlify.app](https://speech-inpainting.netlify.app/)**

---

## 📖 Abstract
*(Insert your paper's abstract here. Briefly explain how you use contextual grounding from slides/OCR to reconstruct missing speech segments.)*

## 🎧 Audio Samples

Below is a subset of our audio demonstrations. 

### 1. Words Present in OCR
Samples where the masked audio corresponds to a complete word that appears in the given context slide ($w \in \mathbf{c}$).

| Transcript / Context | Original Speech | Masked Input | Proposed Model ($\mathcal{M}_{\text{full}}$) |
| :--- | :--- | :--- | :--- |
| *"...text from the slide..."* | [🔊 Play](./samples/orig_1.wav) | [🔊 Play](./samples/masked_1.wav) | [🔊 Play](./samples/pred_1.wav) |
| *"...text from the slide..."* | [🔊 Play](./samples/orig_2.wav) | [🔊 Play](./samples/masked_2.wav) | [🔊 Play](./samples/pred_2.wav) |

### 2. Words Not in OCR
Samples testing the model's performance when the missing word is absent from the visual context.

| Transcript / Context | Original Speech | Masked Input | Proposed Model ($\mathcal{M}_{\text{full}}$) |
| :--- | :--- | :--- | :--- |
| *"...text not on slide..."* | [🔊 Play](./samples/orig_3.wav) | [🔊 Play](./samples/masked_3.wav) | [🔊 Play](./samples/pred_3.wav) |

### 3. Partial-Word Masking
Demonstrating the reconstruction of sub-word segments (10 ms -- 1500 ms).

| Transcript / Context | Original Speech | Masked Input | Proposed Model ($\mathcal{M}_{\text{Partial-Words}}$) |
| :--- | :--- | :--- | :--- |
| *"...text from the slide..."* | [🔊 Play](./samples/orig_4.wav) | [🔊 Play](./samples/masked_4.wav) | [🔊 Play](./samples/pred_4.wav) |

---

## ⚙️ Getting Started (Optional)
*(If you plan to release the code, add instructions for environment setup, downloading weights, and running inference here).*

```bash
git clone [https://github.com/your-username/your-repo.git](https://github.com/your-username/your-repo.git)
cd your-repo
pip install -r requirements.txt
python inference.py --input audio.wav --context slide.txt
