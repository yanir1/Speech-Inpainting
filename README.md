# Listening to the Slides: Multimodal LLM Speech Inpainting with Acoustic-Aware-Loss

For the best interactive experience, please visit our official demo page: **[speech-inpainting.netlify.app](https://speech-inpainting.netlify.app/)**

## 🚀 Upcoming Updates

Stay tuned! We are actively preparing the following for release:

* **Full Source Code:** The complete codebase for the project.
* **Environment Setup:** Step-by-step instructions to properly configure your local environment.
* **Pre-trained Weights:** Links and instructions for downloading our pre-trained model weights.
* **Inference Guide:** Scripts and examples for running inferences on your own audio samples.
* **Model Building Guide:** A comprehensive tutorial on how to train your own speech inpainting model.
* **Dataset & Utilities:** Open-source tools and documentation detailing how to build, adjust, and leverage the dataset.

## 📖 Abstract
**Speech inpainting** reconstructs missing or corrupted speech segments, enabling restoration of damaged virtual lectures and online presentations. While existing audio-only approaches perform well for short gaps, their performance degrades significantly for long-duration missing regions.

In this work, we introduce a novel **multimodal speech inpainting framework** that leverages accompanying presentation slides as semantic grounding for reconstructing both short and long missing speech segments **(10 ms–1500 ms)**.

Our approach reformulates speech inpainting from a local signal-reconstruction problem into a contextual speech generation task using a **Large Audio-Language Model (LALM)**.

To improve acoustic flexibility during generation, we propose **Acoustic Similarity Groups (ASG)**, a token-grouping strategy that relaxes conventional hard-label training.

In addition, we incorporate an auxiliary **Connectionist Temporal Classification (CTC)** objective to improve alignment between generated speech and target lexical content.

Experiments on the M3AV-CHI benchmark demonstrate that the proposed multimodal framework substantially outperforms an audio-only baseline and consistently improves intelligibility and reconstruction quality across challenging long-duration gaps.

## ⚙️ Architecture
![Overview of the proposed multimodal framework](./assets/architecture.jpeg)

**Figure 1:** Overview of the proposed multimodal framework. The system integrates Slide-OCR text tokens and masked latent audio features, followed with an instruction prompt to an LLM decoder. Training is enhanced by an ASG module that modify the CE loss term. During training, the framework makes use of a CTC loss as an auxiliary task. The network outputs discrete audio tokens, which are decoded to generate the inpainted audio and reconstructing the complete recovered audio waveform.

