# 👁️ Generation of Synthetic Images of AMD Using GAN

Welcome! 👋
This project explores the use of **Generative Adversarial Networks (GANs)** to create synthetic retinal images for **Age-related Macular Degeneration (AMD)** diagnosis. It's a hands-on experiment aimed at combining **deep learning** with **medical imaging**, with the hope of augmenting limited datasets for better AI models in healthcare.

🔗 **GitHub Repo:** [Saketh35/Generation-of-synthetic-images-of-AMD-using-GAN](https://github.com/Saketh35/Generation-of-synthetic-images-of-AMD-using-GAN)

---

## 📌 What This Project Does

* Loads real retinal scans from two AMD categories: **CNVM** and **Drusen**
* Applies **Spatial Attention Maps (SAMs)** to emphasize disease-affected regions
* Trains a custom **GAN model** to learn from these enhanced images
* Generates new, synthetic AMD images that mimic the originals in visual structure
* Saves and exports model-generated images and the trained generator for reuse

---

## ✨ Features

* 🧠 **Hybrid Loss Function** combining adversarial loss, anomaly loss, and SSIM loss
* 🎯 **Attention-enhanced preprocessing** using label masks
* 🧪 Generation of new AMD samples for research and data augmentation
* 💾 Trained model gets saved as `generator_SAM.h5` for future inference
* 🖼️ Auto-saves visual outputs to the `gan_images/` directory

---

## 🧰 Tech Stack

* **Language**: Python
* **Libraries**: TensorFlow, Keras, NumPy, OpenCV, PIL, scikit-image, Matplotlib
* **Tools**: Google Colab (used for development and training)

---

## 📁 Repo Structure

```plaintext
.
├── Generation_of_Synthetic_Images_of_AMD_diagnosis_using_GAN.ipynb
├── Dataset/
│   ├── CNVM/
│   ├── CNVM Labels/
│   ├── Drusen/
│   └── Drusen Labels/
└── gan_images/         # Contains generated images from the trained GAN
```

---

## ⚙️ Getting Started

### 🔧 Installation (Local)

> If you're using [Google Colab](https://colab.research.google.com/), you can skip installation.

1. Clone this repo:

   ```bash
   git clone https://github.com/Saketh35/Generation-of-synthetic-images-of-AMD-using-GAN.git
   cd Generation-of-synthetic-images-of-AMD-using-GAN
   ```

2. Install required packages:

   ```bash
   pip install tensorflow tensorflow-addons numpy opencv-python scikit-image matplotlib pillow
   ```

3. Make sure your dataset folders match the following:

   ```
   Dataset/
   ├── CNVM/
   ├── CNVM Labels/
   ├── Drusen/
   └── Drusen Labels/
   ```

---

## 🚀 How to Use

1. Open the notebook:
   `Generation_of_Synthetic_Images_of_AMD_diagnosis_using_GAN.ipynb`

2. Run through the following steps:

   * Apply **Spatial Attention Maps** to highlight pathology areas
   * Train the **GAN model** on the preprocessed dataset
   * Generate new synthetic images
   * View or save outputs to `gan_images/`

3. The trained generator model is saved as:

   ```
   generator_SAM.h5
   ```

4. Want to generate new samples later? Just load the model and run:

   ```python
   generator = tf.keras.models.load_model('generator_SAM.h5')
   noise = np.random.randn(1, 128)
   generated_img = generator.predict(noise)
   ```

---

## 🧠 Known Issues & Future Work

* Currently focused on CNVM images—Drusen is prepped but not yet integrated into training
* Hybrid loss works, but can likely be fine-tuned or optimized further
* Would be interesting to scale up image size (currently 32x32) for better detail
* Model performance is best visualized qualitatively—quantitative evaluation still pending

---

## 🙌 A Quick Note

This project was built out of pure curiosity and a love for the intersection of **AI and healthcare**. It's still a work in progress, and I'm super open to suggestions, ideas, or even just chatting about the approach!

---

## 🤝 Contributions & Feedback

If you find this interesting or useful:

* ⭐ Star the repo to show support
* 🐞 Open an issue if you notice a bug
* 📬 Drop feedback or open a PR if you have improvements to suggest

Let’s collaborate and learn together!

---

Thanks for stopping by!
— *Saketh*
