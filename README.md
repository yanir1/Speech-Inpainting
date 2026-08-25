# Listening to the Slides: Multimodal LLM Speech Inpainting with Acoustic-Aware-Loss

For the best interactive experience, please visit our official demo page: **[speech-inpainting.netlify.app](https://speech-inpainting.netlify.app/)**

---

## 📖 Abstract
**Speech inpainting** reconstructs missing or corrupted speech segments, enabling restoration of damaged virtual lectures and online presentations. While existing audio-only approaches perform well for short gaps, their performance degrades significantly for long-duration missing regions.

In this work, we introduce a novel **multimodal speech inpainting framework** that leverages accompanying presentation slides as semantic grounding for reconstructing both short and long missing speech segments **(10 ms–1500 ms)**.

Our approach reformulates speech inpainting from a local signal-reconstruction problem into a contextual speech generation task using a **Large Audio-Language Model (LALM)**.

To improve acoustic flexibility during generation, we propose **Acoustic Similarity Groups (ASG)**, a token-grouping strategy that relaxes conventional hard-label training.

In addition, we incorporate an auxiliary **Connectionist Temporal Classification (CTC)** objective to improve alignment between generated speech and target lexical content.

Experiments on the M3AV-CHI benchmark demonstrate that the proposed multimodal framework substantially outperforms an audio-only baseline and consistently improves intelligibility and reconstruction quality across challenging long-duration gaps.

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
