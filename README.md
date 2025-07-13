**Voice Activity Detection (VAD) Basic**

A simple Python-based Voice Activity Detection (VAD) tool that segments an audio file into speech and silence regions using short-term energy thresholding. This project helps you understand the fundamentals of audio processing and real-time speech detection without relying on complex deep-learning models.

---

## 🚀 Features

* **Mono & 16 kHz conversion**: Standardizes input audio for speech processing.
* **Frame-level energy computation**: Splits audio into overlapping frames and computes short-term energy.
* **Automatic thresholding**: Determines speech/silence threshold using mean and standard deviation of energy values.
* **Speech segment extraction**: Detects contiguous speech regions longer than a configurable duration.
* **Visualization**: Plots waveform, energy curve, and highlights detected speech segments.

---

## 📁 Project Structure

```
vad-basic-v1/
├── sample.wav            # Example input audio (not included)
├── VAD.ipynb          # Main VAD implementation script
└──  README.md             # Project documentation (this file)
```

---

## 🎯 Prerequisites

* Python **3.7+**
* **ffmpeg** installed and in your PATH

List of Python packages in `requirements.txt`:

```plain
pydub
numpy
matplotlib
```

Install dependencies via:

```bash
pip install pydub matplotlib numpy
```

---

## 🔧 Installation & Setup

1. **Clone the repository**:

   ```bash
   https://github.com/Ariashakoo/VAD_Basic
   ```

git clone [https://github.com/YOUR\_USERNAME/vad-basic-v1.git](https://github.com/Ariashakoo/VAD_Basic)
cd vad-basic-v1

````

2. **Install dependencies**:

   ```bash
   pip install pydub matplotlib numpy
  ````

3. **Verify `ffmpeg`**:

   ```bash
   ```

ffmpeg -version

````


---

## 🛠️ Usage

### 1. Prepare your audio file

Place your `.wav` or `.mp3` file in the project root and rename it to `sample.wav` (or modify the filename in the script).

### 2. Run the VAD script

```bash
python vad_basic.py
````

The script will:

* Load and convert the audio to mono, 16 kHz
* Compute and plot the waveform
* Compute frame-level energy and plot the energy curve
* Determine an energy threshold and detect speech frames
* Print the start/end times of each detected speech segment
* Plot energy with speech regions highlighted

### 3. Output Example

```text
Energy Threshold: -20.35 dB

Detected Speech Segments:
  - 0.50s to 1.80s
  - 2.10s to 3.45s
```

Plots will appear in separate windows using Matplotlib.

---

## ⚙️ Configuration

You can adjust parameters at the top of `vad_basic.py`:

| Parameter        | Description                                       | Default |
| ---------------- | ------------------------------------------------- | ------- |
| `FRAME_SIZE_MS`  | Frame length in milliseconds                      | 30 ms   |
| `FRAME_STEP_MS`  | Frame step (hop) length in milliseconds           | 15 ms   |
| `MIN_SPEECH_SEC` | Minimum speech segment duration to keep (seconds) | 0.20 s  |
| Threshold factor | Portion of standard deviation above mean energy   | 0.5 × σ |

Feel free to tweak these values to suit different types of audio or noise conditions.

---

## 🧪 Testing

* Use the provided `sample.wav` or any clean speech recording.
* Validate detection visually via plots and printed timestamps.
* Try with noisy recordings to test threshold robustness.

---

## 📖 Further Improvements

* **Adaptive thresholding**: Use dynamic thresholds per frame or use noise estimation.
* **Advanced features**: Replace energy-based VAD with spectral features (e.g., ZCR, MFCC).
* **Machine Learning**: Integrate pretrained VAD models like WebRTC VAD or neural VAD.
* **Export segments**: Save detected speech portions as separate audio files.
* **GUI/CLI**: Build an interactive interface for real-time VAD.

---

## 🤝 Contributing

Contributions welcome! Please open an issue or submit a pull request.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📬 Contact

Open an issue or reach out to \[[ariashakoo1@gmail.com](mailto:ariashakoo1@gmail.com)]. Feel free to follow me on GitHub: [Ariashakoo](https://github.com/Ariashakoo)
