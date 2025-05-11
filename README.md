# MeloTTS Evaluation Report

## 📌 Chosen Model and Rationale

We chose **[MeloTTS](https://github.com/myshell-ai/MeloTTS)**, a state-of-the-art open-source text-to-speech model developed by MyShell AI. It supports high-quality neural speech synthesis and includes multilingual capabilities. The model was selected due to:
- Its flexible and modular architecture.
- Pretrained checkpoints that enable rapid experimentation.
- Active community and documentation.

## ✅ Evaluation Approach

To evaluate MeloTTS:
1. **Data Preparation**: Audio dataset was copied from a cloud bucket and used for training and inference.
2. **Training**: The model was trained using the default configuration provided in `melo/configs/config.json`.
3. **Inference**: We used an example sentence — *“Did you ever hear a folk tale about a giant turtle?”* — to synthesize speech.
4. **Loss Metrics**: The synthesized audio was compared with ground truth using:
   - **L1 Loss** (Mean Absolute Error)
   - **L2 Loss** (Mean Squared Error)
   - **Dynamic Time Warping (DTW)** with `fastdtw` for waveform alignment (not used but mentioned).

## 🔍 Observations

- The generated speech is reasonably intelligible and closely resembles the ground truth.
- The model's quality improves with more training steps and data diversity.
- Quantitative loss values offer a basic but limited insight into audio quality.
- The visualization and playback of audio using `IPython.display.Audio` was helpful for qualitative evaluation.

## 🚀 Possible Improvements

- **Use Mel-Spectrogram Loss or Perceptual Metrics** like PESQ or STOI for more meaningful evaluation.
- **Augment the training dataset** with more diverse and multilingual samples to improve robustness.
- **Fine-tune hyperparameters** in `config.json` for better synthesis performance.
- **Incorporate DTW loss** during training for temporal alignment sensitivity.
- Deploy the inference model using a real-time TTS API or Streamlit app for live demos.
