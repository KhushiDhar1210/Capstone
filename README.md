**HexFit: Personalized Outfit Recommendations Based on Unique HEX Color Palette**

**- Khushi Dhar**

This project seeks to re-define Seasonal Colour Analysis by leveraging HEX codes and LLMs to determine optimal color palettes for individuals and their outfit recommendations. The model will primarily take face dataset as input, processes it for emotion detection and HEX codes and then recommends the person’s season and which outfit colours would look good on them. Key components include:

• CNN-based supervised learning for Emotion Detection.

• K-means unsupervised learning supported by HSV mask for Skin Tone Extraction and Analy sis and further converting the RGB distribution to HEX codes.

• LLM-based color Interpretation of seasonal palettes and suggestions for colors aligning with the user’s emotions as well. 

• Extraction of colour recommendations from LLM’s response and keyword matching to dataset for finding best outfits.



In this project, we are 
[40 pts] The completeness of source codes for baselines and the core implementation, including datasets (samples if too large), utils (if any), eval, and source codes for training/testing. A clear dir hierarchy is highly recommended. 
[10 pts] A meaningful project figure (e.g., the framework of the method, key exp results visualization, etc) provided in ReadMe.md
[20 pts] Clear instructions for running the project, including, yet not limited to,  1) environment/dependency installation, 2) data preparation (e.g., how to download data, data cleaning, pre-processing, etc.), and 3) training/testing demo scripts. 
[15 pts] Key project results provided in tables/figures/charts. 
[5pts] Reference info and acknowledgment (e.g., if your code is built on another repo, you should cite and thank their work here). 
