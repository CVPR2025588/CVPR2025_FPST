# Formulated Diffusion with Transferred Attributes for Face Synthesis and Recognition
![workflow.png](workflow6.jpg)
> **Abstract:** We propose the Formulated Diffusion with Transferred Attributes (FDTA) framework to synthesize faces of user-specified attributes and apply the synthesized faces to train face recognition models. Our work addresses several important issues associated with models trained on real faces, including attribute imbalance, privacy concerns, and the complexities of data annotation. The proposed FDTA framework comprises two synergistic modules: the Attribute Controllable Generator (ACG) and the Style Transfer Generator (STG). The ACG aims to create unique face images with user-specified attributes including gender, race, age, facial shape, and others. It integrates ChatGPT in the design of formulated prompts that drive a Stable Diffusion model coupled with ControlNet to generate unique face images with desired attributes. The formulated prompts are designed based on learning from interactions with ChatGPT. Given an ACG-generated face and a reference face, the STG generates a target face of the same identity as the ACG-generated face but in the style of the reference face. Our approach enables users to specify attributes and diversify styles when making synthetic data for different applications. To evaluate the effectiveness of our approach, we generated four synthetic datasets, namely Syn-MPIE, Syn-MS1M, Syn-VGGFace2 and Syn-CASIA, and compared them with their real-life counterparts. We also benchmark our approach against other state-of-the-art methods that use synthetic data for face recognition.
>
> 
## Getting Started
- Clone the repo:
    ```
    git clone https://github.com/CVPR2025588/CVPR2025_FPST.git
    ```
## Installation
```python
conda create --name FPST python=3.9
cd FPST
conda activate FPST
pip install -r requirements.txt
```

## Training Datasets
- Syn-MS1M (10K ids/0.5M images)
  - [Google Drive]()

- Syn-MPIE (2K ids/0.36M images)
  - [Google Drive](https://drive.google.com/drive/folders/1NQgHm_CM7zgnXtq_Vs5K6Y3s3zmEu8ZT?usp=sharing)
