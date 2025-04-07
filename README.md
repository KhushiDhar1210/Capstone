**HexFit: Personalized Outfit Recommendations Based on Unique HEX Color Palette**

**- Khushi Dhar**

This project seeks to re-define Seasonal Colour Analysis by leveraging HEX codes and LLMs to determine optimal color palettes for individuals and their outfit recommendations. The model will primarily take face dataset as input, processes it for emotion detection and HEX codes and then recommends the person’s season and which outfit colours would look good on them. Key components include:

• CNN-based supervised learning for Emotion Detection.

• K-means unsupervised learning supported by HSV mask for Skin Tone Extraction and Analy sis and further converting the RGB distribution to HEX codes.

• LLM-based color Interpretation of seasonal palettes and suggestions for colors aligning with the user’s emotions as well. 

• Extraction of colour recommendations from LLM’s response and keyword matching to dataset for finding best outfits.

The architecture of the model is defined in the image below:

![alt text](<Figure/Architecture.png>)



In this project, we are 
[40 pts] The completeness of source codes for baselines and the core implementation, including datasets (samples if too large), utils (if any), eval, and source codes for training/testing. A clear dir hierarchy is highly recommended. 
[10 pts] A meaningful project figure (e.g., the framework of the method, key exp results visualization, etc) provided in ReadMe.md
[20 pts] Clear instructions for running the project, including, yet not limited to,  1) environment/dependency installation, 2) data preparation (e.g., how to download data, data cleaning, pre-processing, etc.), and 3) training/testing demo scripts. 
[15 pts] Key project results provided in tables/figures/charts. 
[5pts] Reference info and acknowledgment (e.g., if your code is built on another repo, you should cite and thank their work here). 



Great! Based on the filenames you’ve provided, I’ll help you structure the **README.md** so it’s clear and easy to follow. Here's a **draft** that you can use and customize:

---

# **HexFit: Personalized Outfit Recommendations Based on Unique HEX Color Palette**

**By Khushi Dhar**

HexFit redefines **Seasonal Color Analysis** by integrating **HEX color codes**, **emotion detection**, and **LLMs** to recommend personalized outfit color palettes. The system uses facial inputs to detect **emotions**, extract **skin tones**, and determine the user’s **seasonal color type**, ultimately suggesting **outfit colors** that align with both **personal coloring** and **current mood**.

---

## **Project Structure**

```
HexFit/
│
├── notebooks/                # Jupyter notebooks with code and analysis
│   ├── Preprocess_Data.ipynb  # Data preprocessing, including face detection & image cleaning
│   ├── Emotion_Detection.ipynb # Emotion detection from facial expressions
│   ├── Hex_Detection.ipynb    # Skin tone extraction and HEX color generation
│
├── data/                     # Sample input data (e.g., images, CSVs)
│
├── Figure/
│   └── Architecture.png       # Visual representation of model architecture
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
- `opencv-python` (for face detection)
- `tensorflow` (for emotion detection CNN)
- `numpy`, `matplotlib` (for image processing and visualization)
- `sklearn` (for K-means clustering)
- `transformers` (for LLM-related tasks)
  
*If you do not have a specific environment or setup, feel free to reach out for further setup instructions.*

---

## **Key Steps in the Project**

### **1. Emotion Detection**  
Facial emotion detection is performed using a pre-trained **CNN model**, which analyzes facial expressions to infer emotional states (e.g., happy, sad, neutral).

### **2. Skin Tone Detection**  
Using **HSV masking**, the skin region is isolated, and **K-means clustering** is applied on the RGB values to detect the **dominant skin color**. This color is then converted into a **HEX code**, suitable for matching to seasonal palettes.

### **3. Color Palette Generation**  
The **HEX code** for the skin tone is passed to an **LLM** (Large Language Model), which interprets the color based on seasonal color analysis, helping determine which **outfit colors** will complement the individual’s skin tone and current emotional state.

---

## **Results & Visualizations**

In each notebook, the results of emotion detection and skin tone analysis are visualized using:
- **Bar charts** for emotion classification accuracy
- **RGB/HEX color swatches** for detected skin tone

Here’s an example output:
- **Input Image:** Facial image for emotion and skin detection
- **Detected Emotion:** e.g., "Happy"
- **Dominant Skin Tone:** HEX Code (e.g., #F1D0A9)

---

## **How to Contribute**

If you'd like to contribute to the project or improve any of the existing components:
1. Fork the repository
2. Create a branch for your changes
3. Make your changes and submit a pull request

---

## **Acknowledgments**

- **Emotion Detection Model:** Based on the pre-trained **FER+ model** for emotion detection.
- **Skin Tone Dataset:** Leveraged from publicly available skin tone datasets.
- **Color Theory Reference:** Seasonal color analysis and its influence on fashion.

---

### Notes:
1. **Model Training:** Currently, the project relies on pre-trained models for both emotion detection and face extraction. Future work will involve training these models for enhanced accuracy.

2. **HEX Code Matching:** The color matching with outfits is still under development. Current demonstrations match HEX codes with sample clothing datasets.

---

### **Example Visuals for the Project**

Make sure your results are visible:
- Show **before-and-after** color detection visuals in each notebook.
- Show **outfit recommendation examples** based on the identified skin tone and emotion.

---

### Final Thoughts

This README serves as a guide to understand the structure of the project, how to run it, and what to expect from each notebook. Once your project is organized this way, you'll have a **clean, easy-to-follow workflow** that anyone can pick up and replicate.

---

### 📈 **Do you need help with any specific notebook or implementation?**
I can guide you through specific parts of the code (e.g., emotion detection model setup or K-means implementation) if needed!
