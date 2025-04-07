# **HexFit: Personalized Outfit Recommendations Based on Unique HEX Color Palette**

**By Khushi Dhar**

HexFit redefines **Seasonal Color Analysis** by integrating **HEX color codes**, **emotion detection**, and **LLMs** to recommend personalized outfit color palettes. The system uses facial inputs to detect **emotions**, extract **skin tones**, and determine the user’s **seasonal color type**, ultimately suggesting **outfit colors** that align with both **personal coloring** and **current mood**.

The architecture of the model is defined in the image below:


![alt text](<Figure/Architecture.png>)

---

## **Project Structure**

```
Capstone/
│
├── Code/                      # Jupyter notebooks with code and analysis
│   ├── Preprocess_Data.ipynb  # Data preprocessing
│   ├── Emotion_Detection.ipynb # Emotion detection from facial expressions
│   ├── Hex_Detection.ipynb    # Skin tone extraction and HEX color generation
│
├── Data/                     # Sample input data consisting of Angry, Happy, Surprise, Sad and Neutral image 
│
├── Figure/                
│   ├── Architecture.png         # Model architecture
│   ├── Mask.png                  # Image differences after RGB and HSV mask
│   ├── Davies Bouldin Index.png   # Davies Bouldin Index of RGB and HSV
│
├── README.md                 # Project description and instructions
├── requirements.txt          # Python dependencies
```

---

## **Steps to Run the Project**

1. **Clone the repo and install dependencies:**

   ```bash
   git clone <https://github.com/KhushiDhar1210/Capstone>
   cd HexFit
   pip install -r requirements.txt
   ```

2. **Run the notebooks in order:**

   - **`Preprocess_Data.ipynb`**  
     This notebook handles the major preprocessing steps. It reduces additional data, does augmentation to increase lower represented classes and organizes the images in a proper structure.
   
   - **`Emotion_Detection.ipynb`**  
     This notebook uses a CNN-based model to detect emotions from facial expressions. The output helps incorporate **emotional context** for the upcoming color suggestions.

   - **`Hex_Detection.ipynb`**  
     This notebook uses **HSV filtering** and **K-means clustering** to detect the dominant skin tone from the face region. It converts the extracted RGB distribution to **HEX codes** for use in **seasonal color analysis**.

3. **Understand the output:**
   - Each notebook will display the results in cells, showing emotion analysis, and skin tone extraction in terms of HEX code.
   - In the final step of `Hex_Detection.ipynb`, you will get the **HEX color palette** that aligns with the detected skin tone, which can be used for **personalized outfit recommendations**.

---

## **Required Dependencies**

Create a Python environment and install the necessary packages using the `requirements.txt`:

```bash
pip install -r requirements.txt
```

`requirements.txt` includes key dependencies such as:
- `torch` (For deep learning tasks)
- `tensorflow` (for emotion detection CNN)
- `numpy`, `matplotlib`, `seaborn` (for image processing and visualization)
- `scikit-learn` (for K-means clustering)
- `opencv-python` (For deep learning models)
  
---

## **Key Steps in the Project**

### **1. Emotion Detection**  
Facial emotion detection is performed using a pre-trained **CNN model**, which analyzes facial expressions to infer emotional states (e.g., happy, sad, neutral).

### **2. Skin Tone Detection**  
Using **HSV masking**, the skin region is isolated, and **K-means clustering** is applied on the RGB values to detect the **dominant skin color**. This color is then converted into a **HEX code**, suitable for matching to seasonal palettes.

### **3. Color Palette Generation**  
The **HEX code** for the skin tone is passed to an **LLM** (Large Language Model), which interprets the color based on seasonal color analysis, helping determine which **outfit colors** will complement the individual’s skin tone and current emotional state.

---

## **Results and Visualizations**

1. RGB vs HSV Masking of image

   ![alt text](<Figure/Mask.png>)

   As can be seen, RGB doesn't consider majority of the skin area as important which is overcome by HSV masking.

3. Davies Bouldin Index of k-means clustering for RGB vs HSV masked images

   ![alt text](<Figure/Davies Bouldin Index.png>)

   The DB Index of k-means for HSV masked images are lower which shows better level of clustering at the k points. 

---

## **Acknowledgments**

- **Emotion Detection Model:** Leveraged from publicly available Kaggle datasets.
- **Skin Tone Dataset:** Leveraged from publicly available Kaggle datasets.

---

### Notes:
The color matching with outfits is still under development. 

---
